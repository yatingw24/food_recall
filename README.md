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



### Making Ggplot!
#### 1st - A Line Chart showing the Growing Stipend Gap Between Disciplines 
1. Converted the `cleaned_output.csv` into a dataframe and make multiple boxplots to the distribution of **median stipend** by discipline and by time. As the statistical summary revealed, each discipline's stipend is more or less normally distributed. Either median and mean could be a fair representation of the overall stipend. 
![Chart](static_imgs/boxplot.png)
2. Named a new dataframe called `df_median` grouped by `Academic Year` and `Field`. `summarize()` is used to ensure all data entries are median stipend for a specific major in a specific academic year.
3. Made **a multi-line chart** using `geom_rect`, `geom_line` and `geom_point`. 
4. A breakdown of chart elements:
- each line: each line representing a discipline: Business, Social Science, STEM, and Humanities;
- x-axis: the academic year;
- y-axis: median stipend in $;
- highlighted area: academic years affected by the pandemic.

#### 2nd - A Vertical Bar Chart Comparing the Percentage of Debted Students in Each Major
1. Loaded the data, `debt.csv` and went straight to making ggplot using `geom_bar`.
2. Given that I'd like to represent the percentage, I need to have the bar background go to 100%. As a result, I required `library(scales)` and set my my x-axis' scale from 0 to 1.
3. Colored each major accordingly to the disciple each belongs to and made sure the title matches the color-coding as well. 
4. a breakdown of chart elements:
- x-axis: the percentage of debted students;
- y-axis: The major.
5. In case you are curious why I chose percentage as the scale - it would be unfair to represent the number here since the amount of enrollments in STEM almost tripled over that of Non-Science majors.

#### 3rd - A Treemap About the Amount of PhD Candidates by Discipline
1. Loaded the data, `cleaned_output.csv`, and required `library(treemapify)` to enable the treemap graphing function.
2. The area is a straightfoward representation of how many students are enrolled in which discipline. 
3. The purpose was to learn how to make a treemap in R, but it was less revelatory if it is put in the story, as I later realized. As a result, it served as an visual context, allowing readers to understand the proportion of PhD candidates in each discipline.

#### 4th - Two Density Plots for Showing the Financial Support by Types of Institutions
1. In Prof Weiskott's research, he made two separate spreadsheets in order to reveal the difference in stipend offered to English PhD at public universities and private universities. 
2. Since stipends are a continuous variable, using a distribution plot (density plot) is more effective for visualizing variations in financial support across institutions. This allows for an easier comparison of stipend ranges, central tendencies, and overall distribution patterns between public and private universities.
3. Distributions of English Stipend in public and private universities are plotted with `geom_density` and `facet_wrap` to show them at once. 
4. Last, I pointed out the median with dotted lines to directly visualize the gap between stipend offered by public and private institutions. 

### Skills Newly Acquired
1. Data analysis is not only done in Python/Pandas, but also in R using a variety of graphing functions such as `geom_bar()`, `geom_treemap()`.
2. Widened both **my data sources** AND **my choices of chart types** to better convey the message with the most effective type.
3. Practiced advanced data analysis in R such as convertion of characters to numerics, changing fonts, effective annotations, etc. 

## Limitations & Things I'd Like to Improve
1. This is a data-driven project done with a limited amount of time - I would interview PhD candidates from public universities to understand their stipend and how they support themselves financially;
2. While this analysis compares stipends to the U.S. median cost of living ($3,851/month in 2024), the actual living costs vary widely by location. Future work could involve curating a new dataset on regional stipend differences and visualizing geographic disparities in financial support for PhD students. 
3. While I applied a stipend range filter (15,000–90,000), I could have used more systematic outlier detection methods, such as boxplots or IQR filtering to assess the impact of extreme values.
 

 
