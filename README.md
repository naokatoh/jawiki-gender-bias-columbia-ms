# Data Analysis: Wikipedia's Hidden Gender Bias

Wikipedia has long been criticized for having a disproportionate number of male biographies. This project investigated whether there is a difference between male and female biographies in certain categories on the Japanese Wikipedia, which has a distinctively large number of users.

## Methodology 
- Using Python, I scraped female figures’ biographies from the Japanese Wikipedia dump data. To select articles from the particular categories (such as “female scientist” (女性の科学者)), I used PetScan to find the list of page IDs for these articles and extract it from the dump data. For further analysis, I used MeCab (an open-source, text segmentation library for the Japanese language) to analyze the text in these articles to find differences in the articles on females and the difference from the articles on males.
- A caveat of this methodology is that some biographies are categorized under the wrong gender on Wikipedia. This could happen because the wrong categorization was posted on Wikipedia or because of Wikipedia’s categorization method. PetScan is unable to completely avoid errors when separating articles by gender, as some figures in Wikipedia’s biographies have their category in addition to their occupational categories, and these often include other people’s biographies.



## Glossary

This repository uses the following definitions:

- category: Japanese Wikipedia’s category [Wikipedia:Contents/Categories \- Wikipedia](https://en.wikipedia.org/wiki/Wikipedia:Contents/Categories)
- [PetScan](https://en.wikipedia.org/wiki/Wikipedia:PetScan): an external online tool to search for Wikipedia articles by categories and subcategories for all the biographies for a professional category. For example, in order to find all the biographies in the category “female”, I used a query as follows:
`各国の女性|20　
人物|20　
生年|20`  
- `各国の女性` means “women by nationality”, `人物`means "humans", `生年` means “birth year”. There is a `女性`(women) category but it does include fictional and mythical female characters so I needed to add two other categories. 
wc: Wordcloud:  
All the results are in the `wc_results` repository

  



## Wikipedia categories used in the analysis
- `Female scientists `
- `Male scientists`
- `Japanese female idols`
- `Japanese male idols`
- `Princesses`
- `Princes`  
- `Female figure skaters`  
- `Male figure skaters`  
(Each category was identified with [PetScan](https://petscan.wmflabs.org/))  
## Notebook
### Extracting biographies under the targeted categories from Japanese Wikipedia

- `female_scientist.ipynb`
- `male_scientist.ipynb`

- `japaneseFemaleIdol.ipynb`
- `japaneseMaleIdol.ipynb`
- `princess.ipynb`
- `prince.ipynb`
- `femaleFighreSkater.ipynb`
- `maleFigureSkater.ipynb`


### MeCab Analysis
- `MeCabCleanForFemaleFigureSkater.ipynb`
- `MeCabCleanForFScientist.ipynb`
- `MeCabCleanForJapaneseFemaleIdol.ipynb`
- `MeCabCleanForjapaneseMaleIdol.ipynb`
- `MeCabCleanForMaleFigureSkater.ipynb`
- `MeCabCleanForMaleScientist.ipynb`
- `MeCabCleanForPrince.ipynb`
- `MeCabCleanForPrincess.ipynb`  
  
### Wordcloud 
- `wordcloud_femaleScientist.ipynb`
- `wordcloud_maleScientist.ipynb`
- `wordcloud_japaneseFemaleIdol.ipynb`
- `wordcloud_japaneseMaleIdol.ipynb`
- `wordcloud_princess.ipynb`
- `wordcloud_prince.ipynb`
- `wordcloud_maleFigureSkater.ipynb`
- `wordcloud_femaleFigureSkater.ipynb`

### Other Analysis
- `top20Allcombine.ipynb` : for a Datawrapper [table](https://datawrapper.dwcdn.net/kXhdq/8/)
- `overallAnalysisNew.ipynb`
- `top20analysis.ipynb`




## Data
### Japanese Wikipedia dump data 
-  as of June 1, 2022: download from [here](https://dumps.wikimedia.org/jawiki/20220601/), cf. the latest data can be downloaded from [here](https://dumps.wikimedia.org/jawiki/latest/))  
### petScanResult
-  to identify the page IDs of targeted categories 
- The csv files below show the list of page IDs for each targeted category
- `female_scientist.csv`
- `m_scientist.csv`
- `japaneseFemaleIdol.csv`
- `japaneseMaleIdol.csv`
- `princess.csv`
- `prince.csv`
- `femaleFigureSkater.csv`
- `maleFigureSkater.csv`  

### meCabResult
-  The csv files below are the results of MeCab analysis for each category:
- `f_scientist_text_overall.csv`
- `m_scientist_text_overall.csv`
- `japaneseFemaleIdol_text_overall.csv`
- `japaneseMaleIdol_text_overall.csv`
- `princess_text_overall.csv`
- `prince_text_overall.csv`
- `femaleFigureSkater_text_overall.csv`
- `maleFigureSkater_text_overall.csv`  



`stopwords.txt` : Stopwords lists for MeCab



## wc_result
-  The resultsof wordcloud
### wcResultPng
- All the results for each category

### wcResultHtml
- All the results for each category (interactive)
- Each word in the results is clickable for translation (link to [jisho.org](https://jisho.org/))

## Technical Notes

All of the analyses above are coded in Python 3, using the libraries listed below:
- pandas
-  numpy
 - os
- collections
-  glob
-  multidict
 - tqdm
-  MeCab
 - unidic
 - sys
-  re
-  Unicodedata
-  Matplotlib.pyplot
- japanize_matplotlib
- wordcloud





## Licensing

All code in this repository is available under the [MIT License](https://opensource.org/licenses/MIT). All data files are available under the [Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/) (CC BY 4.0) license.

## Questions / Feedback

Nao Hidaka Kato at [nk2970@columbia.edu](mailto:nk2970@columbia.edu).


