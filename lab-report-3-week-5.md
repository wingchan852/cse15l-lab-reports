# **Week 5 Lab Report 3**

### `grep`

### Command-line: `-n`

### Input:

```
grep -n "equipment" technical/911report/chapter-1.txt
```

### Output:

```
222:    Controllers track airliners such as the four aircraft hijacked on 9/11 primarily by watching the data from a signal emitted by each aircraft's transponder equipment. Those four planes, like all aircraft traveling above 10,000 feet, were required to emit a unique transponder signal while in flight.
328:    At 8:51, the controller noticed the transponder change from United 175 and tried to contact the aircraft. There was no response. Beginning at 8:52, the controller made repeated attempts to reach the crew of United 175. Still no response. The controller checked his radio equipment and contacted another controller at 8:53, saying that "we may have a hijack" and that he could not find the aircraft.
396:    The failure to find a primary radar return for American 77 led us to investigate this issue further. Radar reconstructions performed after 9/11 reveal that FAA radar equipment tracked the flight from the moment its transponder was turned off at 8:56. But for 8 minutes and 13 seconds, between 8:56 and 9:05, this primary radar information on American 77 was not displayed to controllers at Indianapolis Center.
594:    Operators worked feverishly to include the FAA, but they had equipment problems and difficulty finding secure phone numbers. NORAD asked three times before 10:03 to confirm the presence of the FAA in the teleconference. The FAA representative who finally joined the call at 10:17 had no familiarity with or responsibility for hijackings, no access to decisionmakers, and none of the information available to senior FAA officials.
```

> It shows the line number at the front. All texts will stick together without the line number and it is hard to read. But now you can clearly see each line is separated by the line number.

### Input:

```
grep -n "difficulty" technical/911report/*
```

### Output:

```
technical/911report/chapter-1.txt:594:    Operators worked feverishly to include the FAA, but they had equipment problems and difficulty finding secure phone numbers. NORAD asked three times before 10:03 to confirm the presence of the FAA in the teleconference. The FAA representative who finally joined the call at 10:17 had no familiarity with or responsibility for hijackings, no access to decisionmakers, and none of the information available to senior FAA officials.
technical/911report/chapter-12.txt:480:                Arabia. The Saudi government has difficulty acknowledging this. American military
technical/911report/chapter-12.txt:852:            The difficulty, understood later, was that even if the intelligence community might
technical/911report/chapter-12.txt:875:                    amount of money available to al Qaeda and has increased its costs and difficulty
technical/911report/chapter-3.txt:269:            Moreover, analysts had difficulty getting access to the FBI and intelligence
technical/911report/chapter-3.txt:912:            Security concerns also increased the difficulty of recruiting officers qualified for
technical/911report/chapter-3.txt:975:                difficulty assimilating new types of personnel, and accustomed to presenting
technical/911report/chapter-5.txt:291:                Nashiri, knew all the details of the operation. When Nashiri had difficulty finding
technical/911report/chapter-6.txt:837:                immediately sent to Yemen to investigate the attack. With difficulty, Barbara
technical/911report/chapter-7.txt:567:            Atta and Shehhi both encountered some difficulty reentering the United States, on
technical/911report/chapter-7.txt:1239:                the United States because Binalshibh's visa difficulty had prevented the two of them
technical/911report/chapter-9.txt:738:                injured people who had descended to the lobby but were having difficulty going on.
technical/911report/chapter-9.txt:1219:                experienced difficulty evacuating, were being helped by first responders on lower
```

> This command-line option shows the line number at the front. It is useful when you want to know the line number especially when it comes to many files. You don't need to go through and check each files. `-n` will display the target file follow by the line number.

### Input:

```
grep -n "difficulty" technical/*/chapter-1.txt technical/*/chapter-2.txt
```

### Output:

```
technical/911report/chapter-1.txt:594:    Operators worked feverishly to include the FAA, but they had equipment problems and difficulty finding secure phone numbers. NORAD asked three times before 10:03 to confirm the presence of the FAA in the teleconference. The FAA representative who finally joined the call at 10:17 had no familiarity with or responsibility for hijackings, no access to decisionmakers, and none of the information available to senior FAA officials.
```

> This command-line option shows the line number at the front. It is more convenient as it automatically display the line number in terminal so you don't need to open up the files and check.

### Command-line: `-c`

### Input:

```
grep -c "difficulty" technical/*/chapter-1.txt
```

### Output:

```
1
```

> This command-line option shows the number of time it of the target string display in the target file. It is useful if you want to count the number of time it repeats in a file.

### Input:

```
grep -c "difficulty" technical/911report/*
```

### Output:

```
technical/911report/chapter-1.txt:1
technical/911report/chapter-10.txt:0
technical/911report/chapter-11.txt:0
technical/911report/chapter-12.txt:3
technical/911report/chapter-13.1.txt:0
technical/911report/chapter-13.2.txt:0
technical/911report/chapter-13.3.txt:0
technical/911report/chapter-13.4.txt:0
technical/911report/chapter-13.5.txt:0
technical/911report/chapter-2.txt:0
technical/911report/chapter-3.txt:3
technical/911report/chapter-5.txt:1
technical/911report/chapter-6.txt:1
technical/911report/chapter-7.txt:2
technical/911report/chapter-8.txt:0
technical/911report/chapter-9.txt:2
technical/911report/preface.txt:0
```

> This command-line option shows the number of time it of the target string display in the target file. In this case, it can count for multiple files and list all the result.

### Input:

```
grep -c "difficulty" technical/*/chapter-1.txt */*/chapter-3.txt
```

### Output:

```
technical/911report/chapter-1.txt:1
technical/911report/chapter-3.txt:3
```

> This command-line option shows the number of time it of the target string display in the target file. It is useful if you only want to count for specific files.

### Command-line: `-l`

### Input:

```
grep -l "difficulty" technical/911report/*
```

### Output:

```
technical/911report/chapter-1.txt
technical/911report/chapter-12.txt
technical/911report/chapter-3.txt
technical/911report/chapter-5.txt
technical/911report/chapter-6.txt
technical/911report/chapter-7.txt
technical/911report/chapter-9.txt
```

> This command-line option will show all the file name that contain the target string. In this case, it shows all the file names that have "difficulty". It is useful when you want to search for a range like all files under a directory.

### Input:

```
grep -l "difficulty" technical/plos/*
```

### Output:

```
technical/plos/journal.pbio.0020010.txt
technical/plos/journal.pbio.0020043.txt
technical/plos/journal.pbio.0020140.txt
technical/plos/journal.pbio.0020146.txt
technical/plos/journal.pbio.0020164.txt
technical/plos/journal.pbio.0020297.txt
technical/plos/journal.pbio.0020337.txt
technical/plos/journal.pbio.0020394.txt
technical/plos/journal.pbio.0020406.txt
technical/plos/journal.pbio.0030024.txt
technical/plos/journal.pbio.0030051.txt
technical/plos/pmed.0010056.txt
technical/plos/pmed.0010058.txt
technical/plos/pmed.0010064.txt
technical/plos/pmed.0020005.txt
technical/plos/pmed.0020040.txt
technical/plos/pmed.0020075.txt
technical/plos/pmed.0020118.txt
technical/plos/pmed.0020123.txt
technical/plos/pmed.0020140.txt
technical/plos/pmed.0020181.txt
technical/plos/pmed.0020200.txt
technical/plos/pmed.0020216.txt
```

> Same as above example. It list out all the files names that contain the target string. It is useful when you want to do wide range search.

### Input:

```
grep -l "difficulty" technical/*/*.txt
```

### Output:

```
technical/911report/chapter-1.txt
technical/911report/chapter-12.txt
technical/911report/chapter-3.txt
technical/911report/chapter-5.txt
technical/911report/chapter-6.txt
technical/911report/chapter-7.txt
technical/911report/chapter-9.txt
technical/biomed/1471-2105-3-16.txt
technical/biomed/1471-2105-3-3.txt
technical/biomed/1471-2105-3-30.txt
technical/biomed/1471-2105-4-26.txt
technical/biomed/1471-2121-2-11.txt
technical/biomed/1471-2121-3-21.txt
technical/biomed/1471-2148-2-7.txt
technical/biomed/1471-2148-3-18.txt
technical/biomed/1471-2164-3-1.txt
technical/biomed/1471-2164-3-13.txt
technical/biomed/1471-2164-3-16.txt
technical/biomed/1471-2164-3-18.txt
technical/biomed/1471-2164-4-16.txt
technical/biomed/1471-2164-4-21.txt
technical/biomed/1471-2180-3-4.txt
technical/biomed/1471-2202-2-14.txt
technical/biomed/1471-2202-2-9.txt
technical/biomed/1471-2288-1-9.txt
technical/biomed/1471-2296-3-3.txt
technical/biomed/1471-2334-3-11.txt
technical/biomed/1471-2350-3-1.txt
technical/biomed/1471-2407-3-18.txt
technical/biomed/1471-2431-3-3.txt
technical/biomed/1471-244X-2-9.txt
technical/biomed/1471-2458-1-9.txt
technical/biomed/1471-2458-2-11.txt
technical/biomed/1471-2474-3-3.txt
technical/biomed/1472-6750-1-11.txt
technical/biomed/1472-6769-1-2.txt
technical/biomed/1472-6793-1-12.txt
technical/biomed/1472-6807-2-3.txt
technical/biomed/1472-684X-2-2.txt
technical/biomed/1472-6882-1-10.txt
technical/biomed/1472-6882-3-1.txt
technical/biomed/1472-6904-2-4.txt
technical/biomed/1472-6920-2-1.txt
technical/biomed/1472-6947-2-7.txt
technical/biomed/1472-6947-3-8.txt
technical/biomed/1472-6963-2-10.txt
technical/biomed/1472-6963-3-11.txt
technical/biomed/1472-6963-3-6.txt
technical/biomed/1475-2867-3-12.txt
technical/biomed/1475-2875-2-10.txt
technical/biomed/1475-925X-2-10.txt
technical/biomed/1475-9276-1-3.txt
technical/biomed/1476-0711-2-3.txt
technical/biomed/1476-0711-2-7.txt
technical/biomed/1477-7525-1-10.txt
technical/biomed/1477-7819-1-10.txt
technical/biomed/1477-7827-1-23.txt
technical/biomed/1477-7827-1-54.txt
technical/biomed/bcr570.txt
technical/biomed/cc1538.txt
technical/biomed/cc1882.txt
technical/biomed/cvm-2-4-180.txt
technical/biomed/cvm-2-4-187.txt
technical/biomed/gb-2001-2-10-research0042.txt
technical/biomed/gb-2001-2-11-research0046.txt
technical/biomed/gb-2001-2-6-research0020.txt
technical/biomed/gb-2001-2-7-research0025.txt
technical/biomed/gb-2002-3-12-research0077.txt
technical/biomed/gb-2002-3-2-research0009.txt
technical/biomed/gb-2002-3-6-research0029.txt
technical/biomed/gb-2002-3-6-software0001.txt
technical/biomed/gb-2002-3-8-research0038.txt
technical/biomed/gb-2003-4-1-r5.txt
technical/biomed/gb-2003-4-5-r34.txt
technical/biomed/rr37.txt
technical/plos/journal.pbio.0020010.txt
technical/plos/journal.pbio.0020043.txt
technical/plos/journal.pbio.0020140.txt
technical/plos/journal.pbio.0020146.txt
technical/plos/journal.pbio.0020164.txt
technical/plos/journal.pbio.0020297.txt
technical/plos/journal.pbio.0020337.txt
technical/plos/journal.pbio.0020394.txt
technical/plos/journal.pbio.0020406.txt
technical/plos/journal.pbio.0030024.txt
technical/plos/journal.pbio.0030051.txt
technical/plos/pmed.0010056.txt
technical/plos/pmed.0010058.txt
technical/plos/pmed.0010064.txt
technical/plos/pmed.0020005.txt
technical/plos/pmed.0020040.txt
technical/plos/pmed.0020075.txt
technical/plos/pmed.0020118.txt
technical/plos/pmed.0020123.txt
technical/plos/pmed.0020140.txt
technical/plos/pmed.0020181.txt
technical/plos/pmed.0020200.txt
technical/plos/pmed.0020216.txt
```

> This one shows all the files names that have the string "difficulty" under the directory "technical". It is very useful when you need to name of the file instead of the context.

[Return to the main page](index.md)
