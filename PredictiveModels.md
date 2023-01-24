
# Predictive analytics

## Selecting a model
Voor het selecteren van een model is het eerst belangrijk om te bepalen of je een regressie of classificatie probleem heb. Een website welke helpt met het duidelijk maken welk type probleem je heb is [Springboard](https://www.springboard.com/blog/data-science/regression-vs-classification/#:~:text=Regression%20vs%20Classification%20in%20Machine%20Learning%3A%20Understanding%20the%20Difference,classification%20predicts%20discrete%20class%20labels.). Voor het project wat met de foodboost dataset is uitgevoerd viel dit onder een classificatie probleem. Binnen het project wilde wij bepalen of een machine learning model op basis van de ingrediënten van een de recepten die een persoon lekker vind konden bepalen wat hun favoriete keuken is. Aangezien wij willen catagoriseren is dit een classificatie probleem.

Voor het model is er gekozen voor een Naive Bayes model. Volgens de website [Towardsdatascience](https://towardsdatascience.com/top-machine-learning-algorithms-for-classification-2197870ff501) is dit model namelijk geschikt om te werken met relatief weinig data. In de dataset bevind zich de ingrediënten van de recepten die een persoon lekker vind en daarbij ook hun favoriete keuken. In totaal zijn er 7 verschillende keukens in de dataset. In de dataset zit data van 1400 gesimuleerde mensen. Voor de dataset is het volgende bestand gebruikt: [Foodboost](https://github.com/BrianWolvers/ADS/blob/main/final_userdata_min_40.csv) De code voor het genereren van deze dataset is geschreven door Bram ten Cate.

## Configuring a model
Als eerste wordt de dataset ingeladen in het script. 
```
df_userdata = pd.read_csv('final_userdata_min_40.csv')                
df_userdata = df_userdata.drop(df_userdata.columns[0:11],axis =1)
df_userdata = df_userdata.drop('liked_recipes',axis =1)
```
Vervolgens worden de y waardes omgezet van de verschillende keukens naar cijfers zodat het model dit kan voorspellen.
```
for keuken in range(len(df_userdata)):
    
    if df_userdata['kitchen'].iloc[keuken] == 'aziatisch':
        df_userdata['kitchen'].iloc[keuken] = 0
    elif df_userdata['kitchen'].iloc[keuken] == 'frans':
        df_userdata['kitchen'].iloc[keuken] = 1
    elif df_userdata['kitchen'].iloc[keuken] == 'hollands':
        df_userdata['kitchen'].iloc[keuken] = 2
    elif df_userdata['kitchen'].iloc[keuken] == 'italiaans':
        df_userdata['kitchen'].iloc[keuken] = 3
    elif df_userdata['kitchen'].iloc[keuken] == 'mexicaans':
        df_userdata['kitchen'].iloc[keuken] = 4
    elif df_userdata['kitchen'].iloc[keuken] == 'mediterraan':
        df_userdata['kitchen'].iloc[keuken] = 5
    elif df_userdata['kitchen'].iloc[keuken] == 'amerikaans':
        df_userdata['kitchen'].iloc[keuken] = 6
``` 
Vervolgens wordt er een train, test en validatie split gemaakt.
```
y= df_userdata['kitchen']
X = df_userdata.drop('kitchen', axis = 1)

y=y.astype('int')

X_main, X_test, y_main, y_test = train_test_split(X, y, test_size = 0.2, random_state=42, stratify=y)
X_train, X_val, y_train, y_val = train_test_split(X_main, y_main, test_size = 0.25, random_state=42, stratify=y_main)
X_test
``` 
De code hierboven is door Milan van Oeveren en Ilias Hazali alle code hieronder beschreven is door mijzelf opgesteld.

## Naive Bayes
Vervolgens kiezen is er aangegeven welk model er gebruikt gaat worden voor het classifiseren van de data. Deze wordt meteen ook gefit op de data en wordt er een voorspelling gedaan over de data.
```
model = MultinomialNB()
model.fit(X_train,y_train)
y_proba = model.predict(X_val)
```
Op basis van de fit is er gekeken naar de precision, recall en accuracy score.
![image](https://user-images.githubusercontent.com/121485743/214257973-501765dc-1692-40e1-abcb-f95f924313ca.png)

Ook op de testset behaald het model een hoge score
![image](https://user-images.githubusercontent.com/121485743/214258255-55ede299-eaf2-43a2-98a0-ac157a1bc314.png)

Op basis van de resultaten is er een confusion matrix gemaakt waarin weergegeven wordt welke catagorieën het model voorspeld. Hierin is te zien dat het model heel veel van de voorspellingen goed heeft gedaan. Het model heeft bij twee personen de verkeerde favoriete keuken voorspeld. 

![image](https://user-images.githubusercontent.com/121485743/214258718-dfca971e-6d09-44ec-b9d5-2839e897a41b.png)

Vervolgens is dit model vergeleken met andere classificatie modellen om te controleren of dit model wel degelijk het juiste model is voor het voorspellen van de Y waarde.

## KNearest Neighbors

als eerste is er een vergelijking gemaakt met een K nearest Neighbors model. 
```
model = KNeighborsClassifier()
model.fit(X_train,y_train)
y_proba = model.predict(X_val)
```

Bij de KNearestNeighbor is te zien dat standaard deze een lagere score haalt op de foto hieronder. 

![image](https://user-images.githubusercontent.com/121485743/214269746-d5762bf9-1091-4806-83f7-7bc95a97a751.png)

Bij Naives bayes is het niet mogelijk om hyperparameter tuning uit te voeren aangezien deze geen hyperparameters heeft om te tunen. KNearestNeighbor heeft dit wel en daarom is er ook gekeken of het model betere resultaten haalt als de hyperparameters getuned worden.

Op de foto is te zien welke Hyperparameters random search aanraad voor het model

![image](https://user-images.githubusercontent.com/121485743/214273220-dd6017df-b2bf-41ee-9e26-138ef7bd0278.png)

Op basis van de ingestelde hyperparameters is te zien dat de accuracy, recall en precision score is gestegen.

![image](https://user-images.githubusercontent.com/121485743/214273350-95dd58ad-dfc8-4976-a915-60dd45231852.png)

Ondanks dat de precision accuracy en recall gestegen is dit nog steeds niet zo goed of beter als het Naive Bayes. Op de foto hieronder is te zien welke voorspellingen het model heeft gedaan op het KNearest Neighbor model. Hier is te zien dat het model inderdaad meer verkeerde voorspellingen heeft gemaakt.

![image](https://user-images.githubusercontent.com/121485743/214273896-b1f31542-c918-4ab5-b302-c79589cf71a7.png)

## DecisionTree

Hetzelfde is uitgevoerd voor een DecisionTree classifier en een RandomForest classifier.

Bij de Decisiontree is te zien dat de accuracy, recall en precision het laagste tot nu toe is.

![image](https://user-images.githubusercontent.com/121485743/214274489-de74561d-5ce7-4bfe-a9ad-7372f52926b9.png)


bij het tunen zijn de volgende mogelijkheden meegegeven en komt random search terug met de volgende hyperparameters.

![image](https://user-images.githubusercontent.com/121485743/214277289-6cac0fe1-b66a-44cb-ad97-d7d8172a7d3f.png)

![image](https://user-images.githubusercontent.com/121485743/214277372-c0840940-436a-4246-b306-a95f57dcd293.png)

Wat opvalt is dat hij bij de random search niet alle hyperparameters meeneemt bij het bepalen van de optimale hyperparameters. Bij meerdere pogingen nam hij deze telkens niet mee. Na het tunen is te zien dat er weinig tot geen verbeteringen zijn. Hierbij is dus te zien dat de DecisionTree geen geschikt model voor het voorspellen van de favoriete keuken.

![image](https://user-images.githubusercontent.com/121485743/214277721-28f2a5cd-6a06-44ef-bcbc-657c883933ec.png)


## Random Forest

De RandomForest toont al betere resultaten en kan mogelijk nog beter zijn dan het Naive Bayes model na hyperparameter tuning.

![image](https://user-images.githubusercontent.com/121485743/214274762-8be18966-bbde-48d4-b647-a2a0f1c2a1cf.png)

Voor het tunen van de hyperparameters zijn de volgende mogelijkheden meegegeven en is het volgende resultaat uit gekomen.

![image](https://user-images.githubusercontent.com/121485743/214280144-58e5236c-0fae-4ccd-8111-f4b1bdf53cb5.png)

Het tunen van de hyperparameters gaf een verbetering aan de scores, maar het kwam nog niet dicht bij genoeg aan de Naive Bayes. Dit is te zien op de volgende foto.

![image](https://user-images.githubusercontent.com/121485743/214280328-e4bf0e01-84b2-4ae3-99ce-f156c5ee0251.png)


## Conclusion

Op basis van de resultaten van de verschillende modellen is te zien dat het Naive Bayes model de beste scores behaald. Dit zijn namelijk de volgende scores:

![image](https://user-images.githubusercontent.com/121485743/214280626-22f9910e-766b-470b-a53f-6e7fd1768b95.png)

De hoogte van de accuracy recall en precision is terug te zien in de confusion matrix. Hierin is te zien dat het model namelijk maar 2 voorspellingen fout had van de 200.

![image](https://user-images.githubusercontent.com/121485743/214280874-0dfa225f-5a6f-4d7a-b161-462693e09793.png)


## Notebook

Mocht u de notebook willen bekijken welke gebruikt is voor het onderzoeken van het best passende model dan kunt u deze [hier]() downloaden.









