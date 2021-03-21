# Challenge - School District Analysis

## Challenge - Overview

We are tasked with preparing standardised test data for analysis, reporting, and presentation to provide insights about performance trends and patterns. We were given a dataset of schools in the district as well as a dataset of students at those schools and their corresponding math and reading test scores. We had to aggregate the data and look for trends in school performance based on a variety of categories.

We want to look at the math and reading scores and the passing rates, and look for trends based on school type, budget, size, and grades (schooling years). We would take the data and sort it into the chosen categories and group by our chosen ranges.

For the challenge part of the analysis we looked at how removing Thomas High School's 9th Grade math and reading scores would affect the analysis. We compare the same categories mentioned above after removing the scores, and look to see where the biggest changes are.

## Challenge - Results

### How is the district summary affected?

The district summary from the module work is shown below:

|    |   Total Schools | Total Students   | Total Budget    |   Average Math Score |   Average Reading Score | % Passing Math   | % Passing Reading   | % Overall Passing   |
|---:|----------------:|:-----------------|:----------------|---------------------:|------------------------:|:-----------------|:--------------------|:--------------------|
|  0 |              15 | 39,170           | ＄24,649,428.00 |                 79.0 |                    81.9 | 75%              | 86%                 | 65%                 |

And the district summary from the challenge:

|    |   Total Schools | Total Students   | Total Budget    |   Average Math Score |   Average Reading Score |   % Passing Math |   % Passing Reading |   % Overall Passing |
|---:|----------------:|:-----------------|:----------------|---------------------:|------------------------:|-----------------:|--------------------:|--------------------:|
|  0 |              15 | 39,170           | ＄24,649,428.00 |                 78.9 |                    81.9 |             74.8 |                85.7 |                64.9 |

As you can see from the two summaries, removing one school's reading and math scores from only one grade has little effect. This is because we're dealing with a huge number of students (39,170) from 15 schools - one grade just cannot have a large impact. However, there are some minor changes, for example the **Average Math Score** has decreased by one tenth.

### How is the school summary affected?

The school summary from the original module also tells a similar story as the district summary - that there wasn't a great change. However, the interesting part of the analysis comes from the percentage of passing students before and after removing the scores. Here is the school summary after the 9th Grade students of THS have their scores removed (changed to `NaN`):

|                       | School Type   |   Total Students | Total School Budget   | Per Student Budget   |   Average Math Score |   Average Reading Score |   % Passing Math |   % Passing Reading |   % Overall Passing |
|:----------------------|:--------------|-----------------:|:----------------------|:---------------------|---------------------:|------------------------:|-----------------:|--------------------:|--------------------:|
| Bailey High School    | District      |             4976 | ＄3,124,928.00        | ＄628.00             |              77.0484 |                 81.034  |          66.6801 |             81.9333 |             54.6423 |
| Cabrera High School   | Charter       |             1858 | ＄1,081,356.00        | ＄582.00             |              83.0619 |                 83.9758 |          94.1335 |             97.0398 |             91.3348 |
| Figueroa High School  | District      |             2949 | ＄1,884,411.00        | ＄639.00             |              76.7118 |                 81.158  |          65.9885 |             80.7392 |             53.2045 |
| Ford High School      | District      |             2739 | ＄1,763,916.00        | ＄644.00             |              77.1026 |                 80.7463 |          68.3096 |             79.299  |             54.2899 |
| Griffin High School   | Charter       |             1468 | ＄917,500.00          | ＄625.00             |              83.3515 |                 83.8168 |          93.3924 |             97.139  |             90.5995 |
| Hernandez High School | District      |             4635 | ＄3,022,020.00        | ＄652.00             |              77.2898 |                 80.9344 |          66.753  |             80.863  |             53.5275 |
| Holden High School    | Charter       |              427 | ＄248,087.00          | ＄581.00             |              83.8033 |                 83.815  |          92.5059 |             96.2529 |             89.2272 |
| Huang High School     | District      |             2917 | ＄1,910,635.00        | ＄655.00             |              76.6294 |                 81.1827 |          65.6839 |             81.3164 |             53.5139 |
| Johnson High School   | District      |             4761 | ＄3,094,650.00        | ＄650.00             |              77.0725 |                 80.9664 |          66.0576 |             81.2224 |             53.5392 |
| Pena High School      | Charter       |              962 | ＄585,858.00          | ＄609.00             |              83.8399 |                 84.0447 |          94.5946 |             95.9459 |             90.5405 |
| Rodriguez High School | District      |             3999 | ＄2,547,363.00        | ＄637.00             |              76.8427 |                 80.7447 |          66.3666 |             80.2201 |             52.9882 |
| Shelton High School   | Charter       |             1761 | ＄1,056,600.00        | ＄600.00             |              83.3595 |                 83.7257 |          93.8671 |             95.8546 |             89.8921 |
| Thomas High School    | Charter       |             1635 | ＄1,043,130.00        | ＄638.00             |              83.3509 |                 83.8961 |          66.9113 |             69.6636 |             65.0765 |
| Wilson High School    | Charter       |             2283 | ＄1,319,574.00        | ＄578.00             |              83.2742 |                 83.9895 |          93.8677 |             96.5396 |             90.5826 |
| Wright High School    | Charter       |             1800 | ＄1,049,400.00        | ＄583.00             |              83.6822 |                 83.955  |          93.3333 |             96.6111 |             90.3333 |

And here is the summary of THS after we correct the student count and take into account that we removed scores:

|                       | School Type   |   Total Students | Total School Budget   | Per Student Budget   |   Average Math Score |   Average Reading Score |   % Passing Math |   % Passing Reading |   % Overall Passing |
|:----------------------|:--------------|-----------------:|:----------------------|:---------------------|---------------------:|------------------------:|-----------------:|--------------------:|--------------------:|
| Thomas High School    | Charter       |             1635 | ＄1,043,130.00        | ＄638.00             |              83.3509 |                 83.8961 |          93.1857 |             97.0187 |             90.6303 |

Here we can plainly see that after changing the 9th grader's scores to `NaN` without correcting the legitimate student count, Thomas High Score performs poorly in the passing percentage of math and reading. This is important to note, as without changing this we belittle the achievements of the rest of THS - we aren't taking into account that the other students are producing good passing percentages. These are by far the most noticeable changes, and something one would be well suited to keep in mind when cleaning data in the future.

### How does replacing the ninth graders’ math and reading scores affect Thomas High School’s performance relative to the other schools?

Before removing the scores, we can see that THS was the second best performing school:

|                     | School Type   |   Total Students | Total School Budget   | Per Student Budget   |   Average Math Score |   Average Reading Score |   % Passing Math |   % Passing Reading |   % Overall Passing |
|:--------------------|:--------------|-----------------:|:----------------------|:---------------------|---------------------:|------------------------:|-----------------:|--------------------:|--------------------:|
| Cabrera High School | Charter       |             1858 | $1,081,356.00         | $582.00              |              83.0619 |                 83.9758 |          94.1335 |             97.0398 |             91.3348 |
| Thomas High School  | Charter       |             1635 | $1,043,130.00         | $638.00              |              83.4183 |                 83.8489 |          93.2722 |             97.3089 |             90.948  |

And after we removed the scores and corrected for school size, we can see that THS is still the second best performing school:

|                     | School Type   |   Total Students | Total School Budget   | Per Student Budget   |   Average Math Score |   Average Reading Score |   % Passing Math |   % Passing Reading |   % Overall Passing |
|:--------------------|:--------------|-----------------:|:----------------------|:---------------------|---------------------:|------------------------:|-----------------:|--------------------:|--------------------:|
| Cabrera High School | Charter       |             1858 | ＄1,081,356.00        | ＄582.00             |              83.0619 |                 83.9758 |          94.1335 |             97.0398 |             91.3348 |
| Thomas High School  | Charter       |             1635 | ＄1,043,130.00        | ＄638.00             |              83.3509 |                 83.8961 |          93.1857 |             97.0187 |             90.6303 |

There is a slight decrease in the passing percentages but not enough to bump them out of first place. We can quickly conclude here that the rest of THS performs well, even if the legitimacy of the ninth grade is called into question.

### How does replacing the ninth-grade scores affect the following:

**Math and Reading Scores by Grade:**

Here we can see first the math scores by grade and then the reading scores by grade, from the original module and then the challenge, for Thomas High School:

|                       |   9th |   10th |   11th |   12th |
|:----------------------|------:|-------:|-------:|-------:|
| Thomas High School    |  83.6 |   83.1 |   83.5 |   83.5 |
| Thomas High School    | nan   |   83.1 |   83.5 |   83.5 |
|                       |       |        |        |        |
| Thomas High School    |  83.7 |   84.3 |   83.6 |   83.8 |
| Thomas High School    | nan   |   84.3 |   83.6 |   83.8 |

The major change is the missing data. (Obviously the tenth, eleventh, and twelfth grade scores would be unaffected by the removal of the ninth grade scores.) The missing data is the result of us choosing to simply remove the scores rather than try to change them to more accurate scores, or handling this data cleaning in a different way. We could have chosen to take the averages of the other schools falling in similar categories and substituted that data in rather than removing it, but that's a point for a different analysis.

**Scores by School Spending:**

The schools and scores sorted by spending from the module:

| Spending Ranges (Per Student)   |   Average Math Score |   Average Reading Score |   % Passing Math |   % Passing Reading |   % Overall Passing |
|:--------------------------------|---------------------:|------------------------:|-----------------:|--------------------:|--------------------:|
| <$584                           |                 83.5 |                    83.9 |               93 |                  97 |                  90 |
| $585-629                        |                 81.9 |                    83.2 |               87 |                  93 |                  81 |
| $630-644                        |                 78.5 |                    81.6 |               73 |                  84 |                  63 |
| $645-675                        |                 77   |                    81   |               66 |                  81 |                  54 |

And the schools and scores sorted after removing THS ninth graders scores:

| Spending Ranges (Per Student)   |   Average Math Score |   Average Reading Score | % Passing Math   | % Passing Reading   | % Overall Passing   |
|:--------------------------------|---------------------:|------------------------:|:-----------------|:--------------------|:--------------------|
| < ＄585                         |                 83.5 |                    83.9 | 93%              | 97%                 | 90%                 |
| ＄585-630                       |                 81.9 |                    83.2 | 87%              | 93%                 | 81%                 |
| ＄630-644                       |                 78.5 |                    81.6 | 73%              | 84%                 | 63%                 |
| ＄645-675                       |                 77   |                    81   | 66%              | 81%                 | 54%                 |

As we can see there is no change.

**Scores by School Size:**

From the module, by school size:

| School Size        |   Average Math Score |   Average Reading Score |   % Passing Math |   % Passing Reading |   % Overall Passing |
|:-------------------|---------------------:|------------------------:|-----------------:|--------------------:|--------------------:|
| Small (<1000)      |              83.8216 |                 83.9298 |          93.5502 |             96.0994 |             89.8839 |
| Medium (1000-2000) |              83.3747 |                 83.8644 |          93.5997 |             96.7907 |             90.6215 |
| Large (2000-5000)  |              77.7464 |                 81.3445 |          69.9634 |             82.7666 |             58.286  |

From the challenge, by school size:

| School Size        |   Average Math Score |   Average Reading Score | % Passing Math   | % Passing Reading   | % Overall Passing   |
|:-------------------|---------------------:|------------------------:|:-----------------|:--------------------|:--------------------|
| Small (<1000)      |                 83.8 |                    83.9 | 94%              | 96%                 | 90%                 |
| Medium (1000-2000) |                 83.4 |                    83.9 | 94%              | 97%                 | 91%                 |
| Large (2000-5000)  |                 77.7 |                    81.3 | 70%              | 83%                 | 58%                 |

Again, there is no change.

- Scores by school type

From the module, by school type:

| School Type   |   Average Math Score |   Average Reading Score |   % Passing Math |   % Passing Reading |   % Overall Passing |
|:--------------|---------------------:|------------------------:|-----------------:|--------------------:|--------------------:|
| Charter       |                 83.5 |                    83.9 |               94 |                  97 |                  90 |
| District      |                 77   |                    81   |               67 |                  81 |                  54 |

From the challenge, by school type:

| School Type   |   Average Math Score |   Average Reading Score | % Passing Math   | % Passing Reading   | % Overall Passing   |
|:--------------|---------------------:|------------------------:|:-----------------|:--------------------|:--------------------|
| Charter       |                 83.5 |                    83.9 | 94%              | 97%                 | 90%                 |
| District      |                 77   |                    81   | 67%              | 81%                 | 54%                 |

And once again, there is no change.

The lack of changes in these categories suffer from the same issues broached in the district school summary above: removing one grade's scores from one school of the 15 in the district just simply won't have as grand an effect. This is unfortunate as it means we aren't able to analyse the true meaning of removing the scores. The next step would be looking into the individual school, or seeing how a whole school's scores being nullified would effect this analysis.

## Challenge - Summary

We really only saw **four** major changes during this analysis after the cheating changes:
- Per School Summary - % Passing Math
- Per School Summary - % Passing Reading
- Per School Summary - % Overall Passing
    - We had to take into account the real number of student scores before we could get an accurate analysis.
- Math and Reading Scores by Grade
    - Here we saw what the lack of data would do to our set, when missing a whole cell of the summary.

## Context

This is the result of Module 4 of the University of Toronto School of Continuing Studies Data Analysis Bootcamp Course. Following the guidance of the module we end up pushing this selection of files to GitHub.

_I was personally surprised there weren't more easy to see changes in this analysis - perhaps I missed something and ended up not seeing the actual major changes though. Any feedback that points me in the correct direction (if I'm not there) would be greatly appreciated._
