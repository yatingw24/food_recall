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
2. Given that I'd like to represent the percentage, I need to have the bar background go to 100%. As a result, I required `library(scales)` and set my my x-axis' scale from 0 to 1.
3. Colored each major accordingly to the disciple each belongs to and made sure the title matches the color-coding as well. 
4. a breakdown of chart elements:
- x-axis: the percentage of debted students;
- y-axis: The major.
5. In case you are curious why I chose percentage as the scale - it would be unfair to represent the number here since the amount of enrollments in STEM almost tripled over that of Non-Science majors.



### Skills Newly Acquired
1. Data analysis is not only done in Python/Pandas, but also in R using a variety of graphing functions such as `geom_bar()`, `geom_treemap()`.
2. Widened both **my data sources** AND **my choices of chart types** to better convey the message with the most effective type.
3. Practiced advanced data analysis in R such as convertion of characters to numerics, changing fonts, effective annotations, etc. 

## Limitations & Things I'd Like to Improve
1. This is a data-driven project done with a limited amount of time - I would interview PhD candidates from public universities to understand their stipend and how they support themselves financially;
2. While this analysis compares stipends to the U.S. median cost of living ($3,851/month in 2024), the actual living costs vary widely by location. Future work could involve curating a new dataset on regional stipend differences and visualizing geographic disparities in financial support for PhD students. 
3. While I applied a stipend range filter (15,000–90,000), I could have used more systematic outlier detection methods, such as boxplots or IQR filtering to assess the impact of extreme values.
 

 
