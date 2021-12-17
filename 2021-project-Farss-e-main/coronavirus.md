# Q3 Coronavirus data (20 marks)

---
## Description

1. Go to https://github.com/owid/covid-19-data/tree/master/public/data to download the covid-19 data in csv and save the file under the [`data`](data/) folder. You may want to have a look [here](https://github.com/owid/covid-19-data/blob/master/public/data/owid-covid-codebook.csv) to see what each column is representing. Make sure you upload your data as well when you submit your work

2. Select the data for two countries for a particular variable (say `excess_mortality`) that you are interested in. Rearrange the data so that each row represents the data for a particular date, each column represents a country, and each cell represents the particular variable of interest

3. Compare differences between the two countries based on (2). You can do so with some plots or some statistics

4. Try to explain the differences with other data. For example, try to explain `excess_mortality` using `total_vaccinations_per_hundred`

Again, you are _not_ expected to use fancy, advanced, complex or sophisticated analysis. Simple analysis is enough _as long as_ it is specific, motivative and sensible with good interpretation. Follow up analysis is recommended.

---
## Coding description

* You need to use `Pandas` / `NumPy` functions or methods to do most (if not all) of the data manipulation and data analysis. Make use of vectorised operations and try not to use loop if possible
* You can use any functions, methods, types from `NumPy`, `datetime` and `Pandas`
* You can also google as much as you want to help you to find the right functions for this task. _However_:
  * If you are referencing other people's code / answer / logic, please state it in your report
  * The _analysis_ must be your own work - for example, you can Google "how to plot bar plot pandas", but you cannot Google "coronavirus vaccination effect analysis"

---
## Things to show in the report

* The whole part should be done in the report
* Please show your analysis in Jupyter Notebook _nicely_
  * Please make good use of the _markdown_ cells to:
    * Explain what you are doing (data manipulation or analysis)
    * Write the text to state your analysis and the interpretation on your analysis result - they should not be written as comments in the code block
  * Please display the output nicely in the jupyter notebook
    * e.g. Try not to print a large list or data in the jupyter notebook which takes up loads of space in your notebook (so that readers need to scroll say 10 seconds to see your next block of code)
