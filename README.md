# School_District_Analysis

## Overview of the school district analysis

The purpose of this analysis was to look analyze the reading and math scores for a district and the fourteen individual schools within it. Schools were ranked based on "overall passing percentage" (OPP), a calculation of the number of students that had an average score of 70% or better for both math and reading divided by the total student population. Schools were then grouped by three different categories: (1) amount of money spent per student on average, (2) school size, (3) type of school. Each category was then compared by OPP.

Initial comparative analysis showed:

1. Charter schools had a higher OPP in this district.
2. Small and medium schools had a higher OPP than large schools.
3. There is an inverse relationship between money spent per student and OPP for this district.

Following this analysis it was revealed that Thomas High School's (THS) 9th grade was involved in academic dishonesty. In response, the dataset was modified to change all THS 9th grader's scores to NaN ("not a number"). The previous analyses were re-run using only the values for 10th-12th grade at THS.

## Results after Thomas High School Adjustments

![Fig 1](./Resources/ths_cheaters.PNG)

*Fig. 1- Showing THS 9th Graders score before removal*

In Figure 1 above, the highlighted value for THS 9th graders was replaced with "NaN", then all further calculations were done only using the values for 10th-12th grade for THS. Since the 9th graders at THS performed similarly to the other grades at THS, ignoring 9th grade's average scores does not substantially change their passing percentages. If the "NaN" result is included in the data set, all of 9th grade for THS is de facto labeled as a "fail". This would strongly affect the comparison categories THS appears in, such as charter schools.

### District summary

![Fig 2a](Resources/old_district_summary.PNG)
*Fig. 1a- District Summary Original*

![Fig 2b](Resources/new_district_summary.PNG)
*Fig. 1b With Only 10th-12th grade for THS*

Shown in Figure 2b, once the 9th grade for THS has been completely removed, there is no substantive change for the district in terms of test scores. The only difference between the two summaries is the missing 461 students from the "total students" column in Figure 2b.

![Fig 2c](./Resources/ds_run_without_changing_student_count.PNG)
*Fig. 2c- District summary with THS 9th grade NaN results included*

If the NaNs for THS 9th grade were included (i.e. by not fixing the student count), the percentage passing math, reading, and overall would all drop as shown in Figure 2c above. For instance, the overall passing percent for the whole district dropped eight tenths of a percent when including THS 9th grades NaN results.

### How is the school summary affected?

![Fig 3a](./Resources/new_per_school_summary.PNG)
*Fig. 3a- School Summary only including THS 10th-12th grade*

![Fig 3b](./Resources/old_per_school_summary.PNG)
*Fig. 3b- THS "per school" results with 9th grade NaNs included*

THS was the only school shown in Figure 3a that was affected by academic dishonesty. THS's statistics including 9th grade's NaN results is shown in Figure 3b. The passing percentage for the school drops dramatically when these results are included. When the 9th grade's scores are excluded from the analysis, as in Figure 3a, we can see that THS's passing percentage is above 90%.

### How does replacing the ninth graders??? math and reading scores affect Thomas High School???s performance relative to the other schools?

![Fig 4a](./Resources/old_top_five_schools.PNG)
_Fig. 4a- Top Five Schools list with THS's NaN scores included_

![Fig 4b](./Resources/old_bottom_five_schools.PNG)
_Fig. 4b- Bottom Five Schools list with THS's 9th grade included_

![Fig 4c](./Resources/new_top_five_schools.PNG)
_Fig. 4c- Top Five Schools list with THS's 9th grade excluded_

When including THS's 9th grade NaN results, THS drops off of the Top Five Schools list entirely (Fig 4a), though not so far as to be shown on this district's Bottom Five Schools list (Fig 4b). When THS's 9th grade NaN results are excluded from the analysis, they return to their previous #2 ranking on the Top Five Schools list.

### How does replacing the ninth-grade scores affect the following:

### Math and reading scores by grade

![Fig 5](./Resources/new_math_scores_by_grade.PNG) ![Fig 5b](./Resources/new_reading_scores_by_grade.PNG)

_Fig 5- Math (left) and reading (right) scores grouped by school and grade level_

The only change to the math and reading scores by school and grade level is the "NaN" result listed for THS's 9th grade, showing that their scores have been replaced.
### Scores by school spending

![Fig 6a](./Resources/new_scores_by_spending.PNG)
![Fig 6b](./Resources/old_schools_by_spending.PNG)
*Fig 6- (top) Schools grouped by spending range excluding THS's 9th grade as "NaN", (bottom) including THS's 9th grade as "NaN"*

Comparing the result excluding and including THS's 9th grade "NaN" result, shows that the spending bucket "$630-644" has lower passing percentages. This is because THS spends an average of $638 per student. When we lower THS's passing percentages by including 9th grade as "NaN" we lower the passing percentage of the entire group containing THS.
### Scores by school size

![Fig 7a](./Resources/new_scores_by_size.PNG)
![Fig 7b](./Resources/old_scores_by_size.PNG)
*Fig 7- (top) Schools grouped by size excluding THS's 9th grade as "NaN", (bottom) including THS's 9th grade as "NaN"*

Comparing the result excluding and including THS's 9th grade "NaN" result, shows that medium size schools have lower passing percentages. This is because THS has 1638 students. When we lower THS's passing percentages by including 9th grade as "NaN" we lower the passing percentage of the entire group containing THS.
### Scores by school type

![Fig 8a](./Resources/new_scores_by_type.PNG)
![Fig 8b](./Resources/old_scores_by_type.PNG)

*Fig 8- (top) Schools grouped by type excluding THS's 9th grade as "NaN", (bottom) including THS's 9th grade as "NaN"*

Comparing the result excluding and including THS's 9th grade "NaN" result, shows that charter schools have lower passing percentages. This is because THS spends an average of $638 per student. When we lower THS's passing percentages by including 9th grade as "NaN" we lower the passing percentage of the entire group containing THS.

# Summary

THS's all school performance falls dramatically in terms of passing percentage when every 9th grader is given a failing grade ("NaN" amounts to a failure). When including this result for all statistics we can see that each of the categories THS belongs to are also affected.

1. Schools in spending bucket "$630-644" show a worse result
2. Medium size schools show a worse result.
3. Charter schools show a worse result
4. THS overall ranking goes from #2 to completely out of the top 5 schools.
   
When these results are removed by ignoring THS's 9th grade, the analysis looks nearly identical to previous analysis done including 9th grade's academically dishonest scores. This is because 9th grade's average score was similar to THS's 10th-12th grade's average score. Removing THS's 9th grade's average test scores did not skew their test averages or passing percentages in a substantive way.