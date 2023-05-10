# Lab Report 3: Command-Line Options 

## **`find` - search for files in a directory hierarchy**

## `-not` 
Example 1:
```
government $ find Env_Prot_Agen -not -name "tech*"
Env_Prot_Agen
Env_Prot_Agen/multi102902.txt
Env_Prot_Agen/section-by-section_summary.txt
Env_Prot_Agen/jeffordslieberm.txt
Env_Prot_Agen/final.txt
Env_Prot_Agen/ctf7-10.txt
Env_Prot_Agen/ctf1-6.txt
Env_Prot_Agen/ro_clear_skies_book.txt
Env_Prot_Agen/ctm4-10.txt
Env_Prot_Agen/1-3_meth_901.txt
Env_Prot_Agen/atx1-6.txt
Env_Prot_Agen/bill.txt
Env_Prot_Agen/nov1.txt
```

The command line option of `-not` allows you to find all of the files without the given argument. In the demonstration above, `-not` and `-name` have been used together to find all the files that do not have "tech" in their file name. The output shows all the the files in the Env_Prot_Agen directory without the "tech" in the file name. 


Example 2:
```
government $ find Post_Rate_Comm -not -name "Mitchell*"
Post_Rate_Comm
Post_Rate_Comm/Gleiman_EMASpeech.txt
Post_Rate_Comm/Cohenetal_CreamSkimming.txt
Post_Rate_Comm/Cohenetal_DeliveryCost.txt
Post_Rate_Comm/Gleiman_gca2000.txt
Post_Rate_Comm/Cohenetal_Cost_Function.txt
Post_Rate_Comm/Redacted_Study.txt
Post_Rate_Comm/Cohenetal_comparison.txt
Post_Rate_Comm/Cohenetal_Scale.txt
Post_Rate_Comm/Cohenetal_RuralDelivery.txt
Post_Rate_Comm/ReportToCongress2002WEB.txt
Post_Rate_Comm/WolakSpeech_usps.txt
```

Similarly as the first demonstration, `-not` and `-name` have been used simultaneously. Instead, we have searched for all files without "Mitchell" in file name of the Post_Rate_Comm directory. 


## `-size`
Example 1:
#### `size +`
```
technical $ find plos -size +24k
plos/pmed.0020059.txt
plos/pmed.0020073.txt
plos/pmed.0020249.txt
plos/pmed.0020103.txt
plos/pmed.0010028.txt
plos/pmed.0010064.txt
plos/pmed.0020160.txt
plos/pmed.0010062.txt
plos/pmed.0020162.txt
plos/pmed.0020016.txt
plos/pmed.0020018.txt
plos/pmed.0010045.txt
plos/pmed.0020182.txt
plos/pmed.0020246.txt
plos/pmed.0020050.txt
plos/pmed.0020045.txt
plos/journal.pbio.0020439.txt
plos/pmed.0010036.txt
plos/pmed.0020123.txt
plos/pmed.0010008.txt
```

The command option `-size` finds files using less than, more than or exactly n units of space rounding up. The suffix 'k' denotes kibibytes. The demonstration above uses a "+" to indicate to look for files with a size *greater* than 24 kibibytes and the output shows the only that are only greater than 24K.


#### `size -`
Example 2:
```
technical $ find plos -size -1k
plos/pmed.0020191.txt
plos/pmed.0020226.txt
```

Conversely, example 2 uses size similarly except with a "-" before the specified units of space. This demonstrates the implementation of `-size` to find files with a size strictly less than 1 kibibyes. 


## `-regex`
Example 1:
```
bash-3.2$ find Env_Prot_Agen/ -regex '.*[ctf].*'
Env_Prot_Agen/
Env_Prot_Agen//multi102902.txt
Env_Prot_Agen//section-by-section_summary.txt
Env_Prot_Agen//jeffordslieberm.txt
Env_Prot_Agen//final.txt
Env_Prot_Agen//ctf7-10.txt
Env_Prot_Agen//ctf1-6.txt
Env_Prot_Agen//ro_clear_skies_book.txt
Env_Prot_Agen//ctm4-10.txt
Env_Prot_Agen//1-3_meth_901.txt
Env_Prot_Agen//atx1-6.txt
Env_Prot_Agen//tech_sectiong.txt
Env_Prot_Agen//bill.txt
Env_Prot_Agen//nov1.txt
Env_Prot_Agen//tech_adden.txt
```

The command line option used is `-regex`. This command option uses a pattern to find files with names that match the 'regular expression' pattern specified to the *whole path*. As demonstrated, The argument used to match the file name includes brackets. Strings enclosed by square brackets will be matched by anything. As you can see in example 2, the pattern is the exact same besides the square brackets. 


Example 2:
```
bash-3.2$ find Env_Prot_Agen/ -regex '.*ctf.*'
Env_Prot_Agen//ctf7-10.txt
Env_Prot_Agen//ctf1-6.txt
```
Excluding the square brackets will match the exact given argument, therefore only showing 2 files, `Env_Prot_Agen//ctf7-10.txt` & `Env_Prot_Agen//ctf1-6.txt` and they are the only files that match the given argument exactly. 

## `-iname`

Example 1:
```
bash-3.2$ find Media -iname 'high*'
Media/highlight_Senior_Day.txt
Media/Higher_Registration_Fees.txt
Media/highlight_Senior_Day 2.txt
Media/Higher_court.txt
```

Similar to `-name`, `-iname` performs the same command, however the match is case insensitive. Hence, example 1 demonstrates the use of `-iname` and provides an output that includes files with the names "highlight*" and "Higher*". 


Example 2:
```
bash-3.2$ find Media -iname 'the*'
Media/The_Columbian.txt
Media/The_State_of_Pro_Bono.txt
Media/The_Bend_Bulletin.txt
```

Example 2 above demonstrates the same use of `-iname` however, using a different pattern. Since there are no file names that include the lowercase of "the", it only provides an output that contain the specified string, case insensitive. 




After googling "find command line options," I found a Stack Exchange thread and a user commented the [man7 URL](https://man7.org/linux/man-pages/man1/find.1.html) for the find command. I was able to use the command options that were listed on the webpage. 





