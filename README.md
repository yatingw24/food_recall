# Unspecified Labeling led the Most FDA Food Recalls in 2024
A responsive data-driven visualization project, supported by a 500-word narrative, informative charts and ai2html, about leading reasons of FDA food recalls in the past year. 

Here is the shortcut to my [article:](https://yatingw24.github.io/food_recall)

A great thank to my data sources:
- [FDA Food Recalls](https://datadashboard.fda.gov/ora/cd/recalls.htm) for its weekly updates on recalls of all classes and types of products.


## Key Takeaways 
Food recall has never been this violent with **labeling issues** leading Class I food recalls, data from the US Food and Drug Administration reveals. 

Undeclared gluten ingredients, such as soy or wheat are found to be the most frequent labeling errors, while 28 percent of food recalls due to a lack of clarity of dairy ingredients such as milk and butter.


## What I Did:
### Tech Stack sed:
 - `python - pandas`
 - `ai2html`
 - `R`
 - `Illustrator`
 - `regex`
 - `csv`

### A Break Down of Files:
Folders:
- `ai2html-output`: the entire output package containing the laptop and mobile versions of my charts. You will see the same tile plot in different sizes, which ensures the readibility on any device. 
- `doc`: the index of my story page and the ai2html scripts. 

Inidvidual files:
 - `food_recall.xlsx`: the original data file which contains weekly update by FDA on recalls.
 - `tile_graph.ipynb`: the jupyter notebook using R console to generate the tile chart.
  - `Analysis.ipynb`: the jupyter notebook where I did my data analysis. 
 - `specifics.csv`: the curated dataset on the frequency of each reason for food recall in 2024. 
 - `yearly.csv`: a breakdown of total recalls by product in the past ten years. 
  - `2024.csv`: a breakdown of recalls by type in 2024. 
 
### Pre-Analysis: Why I chose FDA not USDA?
While USDA offers the recall and public health alert data in the API format, it is no longer retrievable on individual server. 

### Data Cleaning and Analysis
1. By grouping data by type of product, I found that food, compared to other products such as drugs or biologics, composed 40 percent of recalls. 
2. Because reasons for recall are logged and curated in inconsistent structure and format, I need to extract the keyword, such as "unspecified", "undeclared", "listeria", "salmonella", "contamination", "toxic"...., and clustering them into multiple primary categories. Given that cases related to salmonella and listeria are already pervasive, they stood as two individual categories. 
3. Within the category of 'Labeling Issue', I used regular expression to further differentiate what speicifc labeling error is.


### Data Vizs & Graphics
#### 1st - A Tile Chart showing the high proportion of food recalls compared to other product types
1. Used `geom_tile()` to  represent the total number of recalls by product types. Here, I combined product types except Food/Cosmetics together to highlight the overwhelming number of food recall cases. 
![Chart](static_imgs/boxplot.png)
2. Exported it as a `.tile.svg' file to be ready for customization in Illustrator. 


#### 2nd - A Horizontal Bar Chart Comparing the Frequency of Reasons for Food Recalls
1. Loaded the data, `debt.csv` and went straight to making ggplot using `geom_bar`.



### Skills Newly Acquired
1. ai2html 
2. Illustrator: 
3. Practiced advanced data analysis in R such as convertion of characters to numerics, changing fonts, effective annotations, etc. 

## Limitations & Things I'd Like to Improve
1. An analysis of food recalls by region/state or whether there is a correlation between the number of food films and food recalls in a certain area could add an extra layer to my story.
2. More examples of the seriousness of food recall by type could be further provided to give a detailed look into how that affect people's health. 
3. At this point, the project provides a thumbnail of food recalls in 2024. It could go back to previous years and make comparisons, or dive into other products types as well. 
 

 
