
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
## Training a model


## Evaluating a model


## Visualizing the outcome of a model
