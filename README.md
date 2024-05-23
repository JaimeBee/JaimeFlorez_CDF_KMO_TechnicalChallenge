### IMPORTANT FOR NEW VERSIONS OF PYTHON - TO AVOID ERROR

Today Tuesday 21 May I decided to update my whole Anaconda (Python, etc). After that, I went to check the code I submitted to you on the technical test day (only my personal copy in my laptop) 
and it wasn't working anymore. It was throwing an error in the jupyter notebook cell below the title "Calculating Procentage of Families for Each Collection". I realized the new Python version 
I have now requires an extra instruction after the *groupby*: **'group_keys=False'**. When I submitted my code to you - with the previous Python version - it was throwing only 
a warning but the code was producing the correct output (results).

I'm including a screenshot of the original version of my code (and output) submitted the day of the test so you can confirm my code was working properly without the 'group_keys=False'. 
I took the screenshot from this github repo which represents the original code version submitted the test day. Please check the screenshoot also here in this repo.

In summary, if you have a new version of Python and my code is throwing an error, be aware this is because the code is missing the 'group_keys=False' that the older
version (the one I had the test day) didn't require. To run properly, below is an updated code for the section in question. The only difference (addition of 'group_keys=False') 
with the original version is highlighted in bold:


`Fams = pd.DataFrame(df.groupby(['CollectionCode', 'Family']).size())`\
`Fams['Porcentage'] = (Fams.groupby(level=0,` **`group_keys=False`** `).apply(lambda x:  100*x / x.sum())).round(3)`\
`Fams.columns.values[0] = "Num_Records" `\
`Fams.reset_index(inplace = True)`\
`Fams`


I hope you understand this inconveniences are common with different versions.


### ABOUT 2nd EXERCISE

2nd exercise was completed (and uploaded, together with required files) after submittion date. I wanted to have all together and finished.
