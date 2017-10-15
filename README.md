###### Steven Millett and Matt Pavlovich
###### 10/11/2017

# *Case Study Purpose*
#### To compare and contrast the different beers and breweries by state.  There are two key points - one is the understanding of the correlation between ABV and IBU, and the other is the analysis of where there might be good opportunities for investors in this market.

----------------------------------------------------------------------------------------------------------------------------
----------------------------------------------------------------------------------------------------------------------------

# SMU_6306_CaseStudy_1 Codebook
### sessionInfo()
```
## R version 3.4.1 (2017-06-30)
## Platform: x86_64-apple-darwin15.6.0 (64-bit)
## Running under: macOS Sierra 10.12.6
## 
## Matrix products: default
## BLAS: /Library/Frameworks/R.framework/Versions/3.4/Resources/lib/libRblas.0.dylib
## LAPACK: /Library/Frameworks/R.framework/Versions/3.4/Resources/lib/libRlapack.dylib
## 
## locale:
## [1] en_US.UTF-8/en_US.UTF-8/en_US.UTF-8/C/en_US.UTF-8/en_US.UTF-8
## 
## attached base packages:
## [1] stats     graphics  grDevices utils     datasets  methods   base     
## 
## other attached packages:
## [1] knitr_1.17    sqldf_0.4-11  RSQLite_2.0   gsubfn_0.6-6  proto_1.0.0  
## [6] ggplot2_2.2.1
## 
## loaded via a namespace (and not attached):
##  [1] Rcpp_0.12.13         magrittr_1.5         bit_1.1-12          
##  [4] munsell_0.4.3        colorspace_1.3-2     rlang_0.1.2         
##  [7] highr_0.6            blob_1.1.0           stringr_1.2.0       
## [10] plyr_1.8.4           tools_3.4.1          grid_3.4.1          
## [13] gtable_0.2.0         DBI_0.7              htmltools_0.3.6     
## [16] bit64_0.9-7          yaml_2.1.14          lazyeval_0.2.0      
## [19] rprojroot_1.2        digest_0.6.12        tibble_1.3.4        
## [22] memoise_1.1.0        evaluate_0.10.1      rmarkdown_1.6.0.9003
## [25] labeling_0.3         stringi_1.1.5        compiler_3.4.1      
## [28] scales_0.4.1         backports_1.1.0      chron_2.3-51        
## [31] pkgconfig_2.0.1
```
### Object List
#### breweryData -> data frame of breweries from csv
#### beerData -> data frame of beers from csv
#### frequencyOfBrewies -> data frame showing the number of breweries by state
#### populationData -> data frame created by merging breweryData and beerData
#### populationData.by.state -> data frame for the merged data, aggregated by state 
#### fetchMean -> Function: Takes a column from a data frame. Returns the mean of the given column after NA's have been removed.  
#### plotFlippedBarChart -> Function: Takes a data frame, column for x axis, column for y axis, a main title, and x and y labels.  Returns a 90 degree right-rotated GGPlot chart.
#### mean.IBU.by.state -> vector of the mean IBU by state
#### mean.ABV.by.state -> vector of mean ABV by state
#### states -> list of states sorted (ascending)
#### df.abv.by.state -> data frame of ABV by state
#### df.ibu.by.state -> data frame of IBU by state
#### linearABV -> linear model of IBU to ABV
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
#### most.popular.style.by.state -> vector of most popular styles by state
#### df.most.popular.style.by.state -> data frame with the most popular beer per state. Most popular beer is taken to mean the beer that is made the most in the state.  Contains an added column for displaying the beer most similar to the given state's most popular beer in terms of IBU and ABV.
#### finalAnalysis -> data frame with the state, most popular beer, and a good alternative given the current most popular ordered by number of breweries by state (descending).
