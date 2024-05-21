### IMPORTANT FOR NEW VERSIONS OF PYTHON - TO AVOID ERROR

Today Tuesday 21 May I decided to update my whole Anaconda. After that, I went to check the code I submitted to you on the technical test day (only my personal copy in my laptop) 
and it wasn't working anymore. It was throwing an error in the jupyter notebook cell below the title "Calculating Procentage of Families for Each Collection". After working on it 
I realized the new version I got after the update requires an extra instruction after the *groupby*: 'group_keys=False'. When I submitted my code to you - with the previous 
version - it was throwing only a warning but the code was producing the correct output (results).

I attached a screenshot of the original version of my code I submitted the day of the test so you can confirm my code was working properly without the 'group_keys=False'. 
I took this screenshot from the github repo which includes the code and the output exactly as they were in my work submitted on the test day. Please check the 
screenshoot here in this repo.

So, if you have a new version of Python and my code is throwing an error in that section, be aware this is because the code is missing the 'group_keys=False'. To run properly, here is 
an updated code in that section including the additional instruction mentioned required in the new Python version:


`Fams = pd.DataFrame(df.groupby(['CollectionCode', 'Family']).size())`\
`Fams['Porcentage'] = (Fams.groupby(level=0,` **`group_keys=False`** `).apply(lambda x:  100*x / x.sum())).round(3)`\
`Fams.columns.values[0] = "Num_Records" `\
`Fams.reset_index(inplace = True)`\
`Fams`


I hope you understand this inconveniences are common with different versions.
