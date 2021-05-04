## Cleaning Messy Data with OpenRefine
### Citizen science dataset

In this activity set, we will be:

- Create a new project from the citizen science dataset and use the clustering feature
- Split and concatenate various columns in the dataset
- Restructure the dataset by removing columns and rows, and then work with Undo/Redo to roll those changes back
- Export a JSON script to perform the same process on another dataset
- Shutting down OpenRefine

##### Create a new project from the citizen science dataset 
1. **Start a new project:** Start up OpenRefine (if it isn’t running) or click on the OpenRefine logo on the top left to go to the main screen. Note: If you were working with another project, it has been automatically saved in OpenRefine and the files are stored locally on your computer. You can see your project listed here and can use Open Projects to go back to it later. 
2. **Import your dataset:** Click on Create Project and import the citizenscience.csv file. Maintain the default settings, rename your project and click Create Project. You should see that there are 1991 records in our dataset. Click on show 50 rows to show more rows displayed in the window.

##### Use the clustering feature to make your data consistent 

1. **Create a text facet:** Go to the species\_guess column (where our citizen scientists have made a guess as to what species they have observed). From the species_guess column pull down menu, select Facet->Text facet. 
2. **Examine your data:** You'll see that some of them are a bit unusual, and in those cases, you may want to edit them; however, in other cases, you'll see that there are two facets that look very similar, but just have different capitalization, such as American Pokeweed. When we have facets that look similar, we can use OpenRefine's clustering features to help improve the consistency of the values in that column. Click on the Cluster button at the top of the facet window.
3. **Set your clustering algorithm:** At the top of the screen, you'll see that there are different methods and keying functions you can choose from to find clusters. They roughly go from more strict/unforgiving to looser. Let's keep the default for now. Note: In this case, you should see that the column values are just variations in capitalization, but clustering can also catch typos, plural vs singular and other small differences as well.
4. **Cluster similar values:** You can see that it has found entries that it thinks are all referring to the same thing and suggests merging them under one recommended facet. You can put a check mark next to the ones you agree with, and edit the heading that you want to merge them into--or just click on the name you want to use. Go through and merge the entries found into new terms that have only the first word capitalized by adding a check mark under Merge? and adjusting the New Cell Value. When done, click on Merge Selected & Re-Cluster. You might've noticed that as you did a merge, it flashed at the top of the screen how many rows were affected/mass edited.

##### Activity 2: Try a different clustering algorithm and see if you can clean up the species\_guess column more. Try different clustering algorithms and see if you can clean up the species_guess column more. You can ‘Select All’ and quickly scan the suggestions to merge in bulk. After cleaning up the column, can you identify what the most common bird species is in the dataset?

##### Bonus activity: Find all of the blank cells in the common_name column and rename them to N/A. 
##### Bonus activity: In the coordinates_obscured column, change all 'false' values to '0' and all 'true' values to '1'.  

##### Split columns in the dataset
1. **Split the scienctific name colunm into two:** We have a column called scientific\_name. With scientific names, the first part is the genus name and the second part is the specific name. So let's split this column so we can see how many of a particular genus were identified. From the scientific\_name column pull down menu, select Edit column-->Split into several columns. For the separator, put a space, split into 2 columns at most, and uncheck Remove this column because we want to keep it. Then click on OK.
2. **Edit column names:** From each new column’s pull down menu, select Edit column-->Rename this column. For the first one, call it genus. For the second one, call it specific. You could use text facets on the genus column to see how many of each genus were identified. From the genus column pull down menu, select Facet-->Text facet In the facet window, click on Sort by count to sort the facets and see which genus comes out on top.

##### Concatenate columns in the dataset
1. **Add a new column based on an existing column:** You can concatenate (join) strings and/or values from two or more columns together. Let's say that we wanted to combine the information on the user id and login into one column with the format username (user id). For this example, we're going to create a new column to store this information using the *Add column based on this column* feature. From the user_id column pull down menu, select Edit column-->Add column based on this column. Give the new column the name User.

2. **Use GREL to define a format:** OpenRefine's scripting language is called GREL (Google Refine Expression Language). We can use it to define combinations of characters, strings, and numbers. In our expression to define a new column, value refers to the value of the current column. If we want to refer to another column in our expression we use the term **cells.** and then the name of a column then **.value** So for the expression in this case, type **cells.user_login.value + " (" + value + ")"**
The plus sign is used to join the different values or strings together into one long string. So we're creating a string that is the user login, a space, and then the user id in parentheses.

- You'll notice that when you type in the expression, the preview at the bottom changes to show you what the resulting value will be. This preview is extremely helpful when writing GREL expressions! For more help with regular expressions, see [http://www.rexegg.com/regex-quickstart.html](http://www.rexegg.com/regex-quickstart.html) and [https://regex101.com/](https://regex101.com/).

##### Actvity 3: Concatenate the scientific\_name column with the common\_name in parentheses into a new column called Descriptive Name. The format should be \<scientific\_name> (\<common_name>). 

##### Restructure the dataset by removing columns and rows, and then work with Undo/Redo to roll those changes back
1. **Delete columns in bulk:** Go to the special All column pull down menu on the far left. From the All column pull down menu, select Edit columns->Re-order / remove columns... From here you can drag columns from the left to the right to remove them – do this for private latitude and private longitude. We can also reorder columns. Move license, species\_guess and quality_grade columns to just under id to move those columns more to the left. Click on OK to make the changes.
2. **Flag or star rows:** Click on the flag symbol next to a row of interest – try flagging the first few rows of the dataset. 
3. **Use facets to define and flag a subset:** From the license column pull down menu, select Facet-->Customized facets-->Facet by blanks. Click on true to show only the rows where that column is blank (i.e., rows where no license has been specified). From the quality_grade column pull down menu, select Facet-->Text facet Select the casual facet. Now we have a subset of rows that have a blank for license and are casual observations. Let's say that these 18 rows were no good to use. We could flag them (or star them or remove them). From the All column pull down menu, select Edit rows->Flag rows
4. **Remove flagged rows:** Reset all facets by clicking on the Reset All button on the left above the facet windows. Now you should see all the rows in your dataset again, some are flagged and some are not. Later if you decide that you want to remove those flagged rows that you were unsure of, you can. From the All column pull down menu, select Facet-->Facet by flag and then select true from the facet window to show only your flagged rows. You can delete all of them. From the All column pull down menu, select Edit rows-->Remove all matching rows. All the flagged rows should now be removed from the dataset. Reset all facets again by clicking on the Reset All button on the left above the facet windows to see your remaining rows.
5. **Undo and redo actions:** Click on the Undo/Redo tab above where the facets show up. You'll see a number of steps that outlines everything we did to this dataset. It is a great way to keep track of what you've done. You can also roll back your changes to a previous version by clicking on the last step you were happy with. Then everything after that has been rolled back. You can go back and forth in time to take a look at the dataset at a particular point. For example, click on the item that says Reorder columns. You'll see that the steps after that have greyed out, which means they haven't happened yet. So for this example, those flagged rows have now not be deleted, and you should see them in your dataset.
 
- Note: If you go back to a previous step (like we’ve just done), and then start making new changes/transformations - all the subsequent steps will be deleted permanently.

> **Bonus: Removing Duplicates**
> A common clean up process is the removal of items that are duplicates based on one or more columns. For a step-by-step guide to using faceting for this purpose, see [https://guides.library.illinois.edu/openrefine/duplicates](https://guides.library.illinois.edu/openrefine/duplicates). 

##### Extract a JSON script to reproduce your steps with another data file
1. If you have a similarly structured dataset – perhaps for a different snapshot in time – and want to perform the same steps, we can extract a JSON script for future use. Click on the Undo/Redo tab and click on Extract. Choose the steps you want to repeat. Copy the code and save it in a text file to keep a copy of your steps. Later if you load up your new dataset, you could go back to the Undo/Redo tab and select Apply and paste in this code into the window to run those steps on the new dataset.

##### Activity 4: Start up a new project and load the citizen science dataset again. Apply the JSON code that we just copied by going to the Undo/Redo tab, clicking Apply and copying and pasting the code into the window. Click Perform Operations.

##### Shutting down OpenRefine
1. To ensure that all of your steps are saved, it is important to properly shut down OpenRefine.  
- On a PC, hit Control-C on your keyboard.
- On a Mac, go to the OpenRefine app in the doc and choose Quit.
