# Lab Report 2, Week 3
## -maxdepth
---
```
shreyas@Shreyass-MacBook-Pro skill-demo1 % find technical -maxdepth 0
technical
```
The maxdepth command here has been set with a depth of zero, meaning that only the directory name itself is returned.
```
shreyas@Shreyass-MacBook-Pro skill-demo1 % find technical -maxdepth 1
technical
technical/government
technical/plos
technical/biomed
technical/911report
```
The maxdepth command here has been set with a depth of 1, meaning that only technical and the files immediately under it are returned. No files within technical's subdirectories are returned. This could be useful if you just want to find the main files in a directory without seeing everything in the subdirectory.
```
shreyas@Shreyass-MacBook-Pro skill-demo1 % find technical -maxdepth 2
... (lots of files)
technical/biomed/1475-2867-3-3.txt
technical/biomed/1471-2105-3-34.txt
technical/biomed/gb-2002-3-5-research0020.txt
technical/biomed/1471-2407-2-22.txt
technical/biomed/1471-2121-2-15.txt
technical/biomed/1471-2148-2-5.txt
technical/biomed/cc1044.txt
technical/biomed/1471-2091-4-5.txt
technical/biomed/1471-2288-1-9.txt
technical/biomed/rr37.txt
technical/biomed/gb-2001-3-1-research0001.txt
technical/biomed/1472-6963-3-1.txt
technical/biomed/1471-2172-2-9.txt
technical/biomed/1471-2458-2-18.txt
technical/biomed/1471-2180-3-5.txt
technical/biomed/1471-2288-2-10.txt
technical/biomed/1471-2164-3-4.txt
technical/biomed/1472-6793-3-3.txt
technical/biomed/gb-2002-3-12-research0075.txt
technical/biomed/1471-2164-3-27.txt
technical/biomed/1471-2164-3-33.txt
technical/biomed/1471-2091-3-15.txt
...
```
The maxdepth command here has been set with a depth of 2, meaning tat  technical, its immediate subfiles and subdirectories, and its subdirectories contents are returned. This could be useful if you want to find the main directory and subdirectories contents without seeing deeper into the subdirectories contents's contents. This could make command line output more readable when working with directories with lots of subdirectories since you can choose to only have some printed out.
## -mindepth
---
```
shreyas@Shreyass-MacBook-Pro skill-demo1 % find technical -mindepth 4
```
When the mindepth is set to 4, then only the files at a depth greater than 4 are returned, which is 0 files in this case. This could be useful if you want to judge the depth of the directory tree
```
shreyas@Shreyass-MacBook-Pro skill-demo1 % find technical -mindepth 3
... (lots of files)
technical/government/Media/Understanding.txt
technical/government/Media/Do-it-yourself_divorce.txt
technical/government/Media/Politician_Practices.txt
technical/government/Media/defend_yourself.txt
technical/government/Media/Towson_Attorney.txt
technical/government/Media/Pro-bono_road_show.txt
technical/government/Media/A_Perk_of_Age.txt
technical/government/Media/A_helping_hand.txt
technical/government/Media/pro_bono_efforts.txt
technical/government/Media/5_Legal_Groups.txt
technical/government/Media/Greedy_Generous.txt
technical/government/Media/Retirement_Has_Its_Appeal.txt
technical/government/Media/RoanokeTimes.txt
technical/government/Media/NJ_Legal_Services.txt
technical/government/Media/Bridging_legal_aid_gap.txt
technical/government/Media/Legal_Aid_campaign.txt
technical/government/Media/Aid_Gets_7_Million.txt
```
Here the mindepth is set to 3, returning all the files in the 3rd depth level of the directory. This could be useful if you only want to see the contents of a particular subdirectory and its subdirectories.
```
shreyas@Shreyass-MacBook-Pro skill-demo1 % find technical -mindepth 0
technical/
... (lots of files)
technical/911report/chapter-9.txt
technical/911report/chapter-8.txt
technical/911report/preface.txt
```
Here the mindepth is set to 0, which means that all of the files in the directory are returned.
## -type
---
```
shreyas@Shreyass-MacBook-Pro skill-demo1 % find technical -type d
technical
technical/government
technical/government/About_LSC
technical/government/Env_Prot_Agen
technical/government/Alcohol_Problems
technical/government/Gen_Account_Office
technical/government/Post_Rate_Comm
technical/government/Media
technical/plos
technical/biomed
technical/911report
```
The -type d command prints the names of all of the directories in technical. This could be useful if you want to count the number of directories.
```
shreyas@Shreyass-MacBook-Pro skill-demo1 % find technical -type f
... (lots of files)
technical/911report/chapter-12.txt
technical/911report/chapter-10.txt
technical/911report/chapter-11.txt
```
The -type f command prints the names of all the regular files in technical. This could be useful if you just want the names of the files w/o the directory names too
```
shreyas@Shreyass-MacBook-Pro skill-demo1 % find technical/911report -type d
technical/911report
```
The -type d command prints the names of all the directories. This example applies the command to technical's 911report subdirectory. This subdirectory has no subdirectories, so its name was the only thing printed. This command could be useful to see if a subdirectory has subdirectories as can be seen in this case.