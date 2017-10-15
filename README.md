###### Steven Millett and Matt Pavlovich
###### 10/11/2017

# *Case Study Purpose*
#### To compare and contrast the different beers and breweries by state.  There are two key points - one is the understanding of the correlation between ABV and IBU, and the other is the analysis of where there might be good opportunities for investors in this market.

----------------------------------------------------------------------------------------------------------------------------
----------------------------------------------------------------------------------------------------------------------------

# SMU_6306_CaseStudy_1 Codebook
</br>

## Object List
#### breweryData -> data frame of breweries from csv
#### beerData -> data frame of beers from csv
#### frequencyOfBrewies -> data frame showing number of breweries by state
#### populationData -> data frame created by merging breweryData and beerData
#### populationData.by.state -> data frame to showing the merged data, aggregated by state 
#### fetchMean -> Function: Takes a column from a data frame. Returns the mean of the  given column after NA's have been removed.  
#### plotFlippedBarChart -> Function: Takes a data frame, column for x axis, column for y axis, a main title, and x and y labels.  Returns a 90 degree right-rotated GGPlot chart.
#### mean.IBU.by.state -> vector of the mean IBU by state
#### mean.ABV.by.state -> vecotor of mean ABV by state
#### states -> list of states sorted (ascending)
#### df.abv.by.state -> data frame of abv by state
#### df.ibu.by.state -> data frame of ibu by state
#### linearABV -> linearn model of IBU to ABV
#### nearestNeighbor -> Function: Gets the closest vector from a data frame, given a set vector with coordinates(ABV,IBU) and returns a value with the name of the closest vector.
#### getmode -> Function:  Returns the mode of a given vector.
#### populationData.by.style -> data frame split on style from the merged data frame.
#### mean.IBU.by.style -> vector for mean IBU by style
#### mean.ABV.by.style -> vector for mean ABV by style
#### styles -> vector of beer styles in ascending order
#### df.style -> data frame of ABV and IBU by style
#### temp.df.style -> data frame that ignores invalid values
#### temp.linear -> linear model of IBU and IBV from the style data frame
#### temp.merge -> data frame that merges the values we received from the linear model and joins them where there is a value of 0 in the data frame with existing data.
#### most.popular.style.by.state -> vecotor of most populor styles by state
#### df.most.popular.style.by.state -> data frame with the most popular beer per state. Most popular beer is taken to mean the beer that is made the most in the state.  Contains an added column for displaying the beer most similar to the given state's most popular beer in terms of IBU and ABV.
#### finalAnalysis -> data frame with the state, most popular beer, and a good alternative given the current most popular ordered by number of breweries by state (descending).

