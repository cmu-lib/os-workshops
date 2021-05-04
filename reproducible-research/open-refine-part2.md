## Cleaning Messy Data with OpenRefine
### Personal consumption expeditures dataset

In this activity set, we will be:

- Importing a spreadsheet of data into OpenRefine 
- Performing basic clean-up functions like trimming whitespace and deleting columns
- Filtering and faceting data
- Transposing data from wide to long format
- Exporting a dataset from OpenRefine

##### Review the dataset and load it into OpenRefine
1. Open the file expenditures\_by_state.xlsx in Excel and take a look at it. This is a freely available dataset from the Bureau of Economic Analysis, which provides average expenditures on a wide range of goods and services. Notice the following:

	- The data file has been formatted for reading rather than analysis. It has a blank column A. It has some rows at the top containing descriptive information that is not part of the data table. We can also see that each state is only listed once, which is fine for viewing, but will mess things up if we try to sort the data in order to analyze it.
	- The “Expenditure” column has leading spaces in it.

2. Close the Excel file. Next, start up OpenRefine.
3. Ensure that Create Project is selected. Click on Choose Files. Browse to the file expenditures\_by_state.xlsx. Click Open. Then, click the Next button.
4. You are now viewing the dataset in Preview view. Here you can see what data will look like when loaded, and make some changes to the dataset. Notice the following:

	- The descriptive text at the top of the Excel worksheet is showing in the preview, and is messing up OpenRefine’s ability to identify the column headings. We can instruct OpenRefine to ignore these rows that aren’t part of the data table. **Select the check box beside Ignore first, and type 6 in the box to ignore the first 6 lines at the beginning of the file.**
	- Numbers are displayed in green--this means OpenRefine has recognized these columns as containing numeric data 

5. In the Project name box, give the project a name of your choice. Click Create Project.
6. Your data has now been loaded into OpenRefine. Note that it has stored a copy of this data with the OpenRefine installation files on your computer. When you make edits using OpenRefine, you are not editing the original data file you uploaded, all edits are made to the copy OpenRefine has created.

##### Perform some basic data cleanup 
1. In the top toolbar, select 50 in order to show more rows on the screen at once.
2. **Remove the blank columns:** Look for the pull down menu for the column named “Column”. From the pull down menu, select
Edit Column -> Remove this Column.
3. **Change a column name:** Click on the pull down menu for the column name "GeoName". Under Edit Column, choose Rename this Column. Rename the column to "State" and click OK.
3. **Fill down data:** We want to fill the entries down in the State column so that all rows have a state associated with them. From the State column pull down menu, select Edit Cells -> Fill Down. In the top toolbar, click next a few times in order to look at a few pages of results. Verify that the fill operation seems to have worked.
4. **Delete leading whitespace:** Hover your cursor over a cell in the Expenditure column and click edit. You’ll see that there are leading whitespaces that could cause problems down the road. Click 'Cancel' to close the Edit window. From the Expenditure column pull down menu, select Edit cells -> Common transforms -> Trim leading and trailing white space. Check a cell to verify that the leading spaces are gone.

##### Sort, filter and facet data
1. **Sort data on a row:** Rows of data are initially loaded in the order they appear in the original data file. In this case, they are grouped by state, with Alabama first. To change the sort, from the State column pull down menu, select Sort... In the Sort window, sort as text, ordered from z-a. Click OK.
2. **Add a secondary sort:** From the 2017 column pull down menu, select Sort..., and sort by numbers, from largest first. Notice the “sort by this column alone” option – that only appears when there is already one or more sorts in place. If you don’t check that option, it will keep the original sort and add this as a secondary sort. 
3. **Remove a sort:** You can remove a sort at any time by pulling down the column’s menu, and choosing Sort -> Remove sort. 
4. **Filter the data:** Filtering allows us to search for certain information within our dataset. Let’s say we want to display only the Pennsylvania data. From the State column pull down menu, choose Text filter. The text filter appears in the left-hand sidebar, under the “Facet/Filter” tab. Type 'pennsylvania' in the search box. OpenRefine automatically removes any rows from the display that don’t match, leaving a total of 24 rows remaining (out of 1227 total).
5. **Add a second filter:** We can have text filters on more than one column at a time. From the Expenditure column pull down menu, choose Text filter. Type 'food' in the search box for that filter. The two filters are combined, showing us all the food-related expenditure categories for Pennsylvania.
	* Note that any functions you perform on filtered data will only be performed on the filtered records, not the entire dataset. This is also true of exporting the file--if you have filters applied, only the filtered data will appear in the export.
6. **Remove filters:** You can remove a filter by clicking on the x in the top left-hand corner of the filter box. Remove both filters now. You should have all 1227 rows displayed again.
7. **Creating a facet:**  A facet summarizes all the values that appear in the column, and lets you select which data to view, as well as provides ways to edit the data. From the State column pull down menu, choose Facet -> Text facet. The facet appears in the left-hand sidebar, in the same area where the filters were previously. It shows you how many total values there are in this column (50), how many rows contain each value (for this dataset it is the same for each, 24), and allows you to sort the values by name or by count (count won’t be helpful in this case since they all have the same count).
8. **Filter data using facets:** Click on Pennsylvania in the value list. This has the same effect as using the text filter to search for Pennsylvania, leaving 24 matching rows. However, from there we can do more than the filter allowed. We can select a second value at the same time. Hover your cursor over West Virginia in the value list and choose include. You can then exclude one or both of the selections at any time. Hover your cursor over Pennsylvania in the value list and choose exclude. Now only West Virginia rows are shown.
9. **Working with numeric facets:** From the 2017 column pull down menu, expand Facet, and look at the options. There are some other types of facets available, including numeric facets. If we created a numeric facet now, it would only work for this column, so you would have to facet each year of data separately. Let’s manipulate the data a bit first, and then come back and work with numeric facets.

##### Activity 1: In addition to the text facet on State, add another text facet on the expenditure column. Using the facets, view the Pennsylvania, West Virginia and Ohio data for "Gasoline and other energy goods" expenditures.  Which state spent the most per capita in 2017?

> **Bonus Activity:** Remove the above facets. Apply a numeric facet to the 2017 columns and facet to only expenditures over \$30,000. Using an additional facet, determine the expenditure category with the most values over \$30000. 

##### Transpose the data from wide format to long format
1. **Wide vs. Long format:** The dataset is currently in “wide” format with years across as columns. We should convert it to “long” format to work with it using numeric facets. Converting to long format will put all the years into one column as a 'Year' variable, and all the numeric data values into a second column. 
2. **Transpose the data to long format:** Remove an facets you have in place. From the 2017 column pull down menu, select Transpose -> Transpose cells across columns into rows....The Transpose window appears. You are going to put the data from the 8 numeric data columns (named 2010 through 2017) into two columns, one containing the year, and one containing the numeric data value (representing an expenditure amount). For the *From column*, choose 2010. For the *To column* choose 2017 (or last column, either will work). In the Transpose into section, we will use the Two new columns option. The Key Column will be the years – call it Year. Give the Value Column the name Per\_capita_expenditure. Check the Fill down in other columns option. Click Transpose.

![Transpose set up image](/Users/sarahy/Desktop/transpose_setup_image_openrefine.jpg)

**Note:** For each state, for each expenditure type, we now have 8 separate rows, one for each year. Notice the dataset now has 9792 rows, compared to 1227 before transposing. It has fewer columns, but many more rows – this is why it is referred to as a “long” format. Long format can be useful for certain types of data analyses, where all your data measuring the same thing (e.g., per capita expenditures) need to be in one column instead of spread over many.

##### Explore more advanced uses of facets
1. **Work with numeric facets:** From the new Per\_capita_expenditure column pull down menu, choose Facet -> Numeric facet. Numeric facets provide a sliding scale where you can choose which values to include. Notice the blue areas indicate where the values fall – you can see where the bulk of your values lie, and where there are some outliers. Let’s try to remove the outliers by dragging the handles so the facet includes only the largest block of blue values. This removes a number of rows from the display.
2. **Clean up non-numeric cells:** At the bottom of the numeric facet, there are options to show Non-numeric values, Blanks, or Errors in this column. There are no blanks or errors in this data column, but there are non-numeric values. Uncheck Numeric to look only at the Non-numeric values. Most of these have values of “F” in them, but some of them are actually blank! Why are they included here rather than counted as blank cells by the facet? Hover your cursor over a blank cell and click Edit. There are spaces in this cell – remove them using Edit cells -> Common transforms -> Trim leading and trailing white space. Notice in the facet that there are now a number of cells recognized as blank. **Note: In OpenRefine, any actions you perform are only applied to the rows currently selected**, i.e., the above task was only applied to the non-numeric cells that are currently selected.
3. **Use facets to edit data in bulk:** What does the “F” value mean? This was included in the information at the top of the original spreadsheet, which we removed when we loaded it into OpenRefine. If you were to go back and look at the Excel file you’ll see that “F” means the data was too unreliable to be published. If you wanted to change the value of “F” to be something more descriptive, you can use facets to edit data in bulk. However, we can’t do it from a numeric facet, we need a text facet instead. From the Per\_capita_expenditure column pull down menu, select Facet -> Text facet. Notice that only the non-numeric values are listed – this is because you still have only non-numeric values selected (via the numeric facet). Hover your cursor over the value F and choose edit. Change F to something more descriptive, such as Not published. Click Apply. All values of F in the dataset are automatically changed to Not published.

> **In summary: filters are for free text searching; you can identify all matches of your search string in the column. Facets are for structured viewing and editing of unique values.**

##### Export data from OpenRefine
1. Remove any facets you have in place. In the top right-hand corner of the screen, pull down the Export menu and choose comma separated value (or Excel, or whatever format you would like to download).

	- Note that if you choose Export project, it will export as a zip file with the original and final versions of you data and various versions in between.  You could open the project again in OpenRefine to view your process.    
