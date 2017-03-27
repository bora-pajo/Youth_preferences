# Youth_preferences
This statistical exploration is done on a dataset collected from young adults (ages 18-22) on various topics.

Almost everything that captures this group age is included from their weight, height, exercise patterns, sports, movie preferences, 
food preferences, fiction authors preferences. In addition information is collected about parents' education level and income.

The dataset includes over 100 variables and has 163 participants. 

The libraries used:

```python
import numpy as np
import pandas as pd
import matplolib.pyplot as plt
import csv
```

CODEBOOK

99 – always indicates a missing value

1) Birthyear – what year were you born?

99 – missing (the rest are years)

2) Weight – how much do you weigh in pounds

99 – missing

3) selfweight – Do you consider yourself to be?

Overweight – 5
Slightly overweight – 4
Just right – 3
Very Fit – 2
Slim - 1
I don’t think myself in these terms - 6
Other – 7

3) height – how tall are you in feet and inches
(note to self – find a different way to ask about this). Right now the variable is in inches. 

4) selfheight -  Do you consider yourself to be?
Too tall – 5
Tall – 4
Just right – 3
Slightly short – 2
Very short – 1
I don’t think about myself in these terms – 6
Other – 7

5) Gender
Female – 1
Male – 2

6) gradelevel – what year are you?

Freshmen – 1
Sophomore – 2
Junior – 3
Senior – 4

7) marital – marital status


Single – 1
In a relationship – 2
Married – 3
Engaged – 4

8) educationmother – what is the highest level of education of your mother?

Less than high school - 0
High school degree – 1
Some college classes – 2
College degree – 3
Graduate college – 4
Other – 5

9) motherprof – mother’s profession – open ended

10) educationfather – the highest education level of your father

Less than high school - 0
High school degree – 1
Some college classes – 2
College degree – 3
Graduate college – 4
Other – 5

11) fatherprof – father’s profession – open ended

12) income – family income

Less than $15,000 – 1
$15,001 to $30,000 – 2
$30,001 to $50,000 – 3
$50,001 to $70,000 – 4
$70,001 to $100,000 – 5
higher than $100,000 – 6

13) nrchild – number of children you have
(note to self – remove this question from future surveys)

14) nrsibling  - number of silbings

15) housing


on campus – 1
rent out of campus – 2
live with my parents and commute – 3
own my own house – 4


16) employment 

yes, full time – 1
yes, part time – 2
No – 3
Other – 4 (includes summer full time and work study)

(note for next time – work study need to be a question as well as summer work)

17) cooking – how often do you cook?

Every day – 1
A couple of times a week – 2
Whenever I can, but that is not very often – 3
I only help during holidays – 4
Never, I really do not know my way around a kitchen – 5
Other – 6


18) Exercise  - how often do you exercise

Everyday – 1
Twice or three times per week – 2
Once a week – 3
Sometimes – 4
Never – 5


19) sports – do you do any sporting activity?
 
Yes – 1
No – 2
99 – no answer

20) typesports – types of sports – open ended

21) crafting – do you engage in any crafting activity?



Yes- 1
No – 2
99 – no answer

22) typecraft – types of crafts – open ended

23) leisure – what is your favorite leisure time?  Open ended

24) favorshow – what are your three favorite shows? – open ended

25) favormovie – what are your three favorite movies – open ended

26) app – most used phone app? – open ended

27) collegereason – what is your reason for going to college?

Getting a job afterwards – 1
Going to graduate/law/medical school – 2
Learning new things – 3
Other – 4

28) brandcloth – favorite brand of clothing – open ended

29) shopping – shopping habits

In store – 1
Online – 2
Both online and in stores – 3

30) statediv1 - How likely are you to agree with the following statement: "Inclusion and diversity in the workplace is a human right issue"

scale 1 to 10 where 1 is very unlikely and 10 is very likely

31) statediv2 - How likely are you to agree with the following statement: "Inclusion and diversity in the workplace has an advantage in the economic system"

scale 1 to 10 where 1 is very unlikely and 10 is very likely


32) statediv3 - How likely are you to agree with the following statement: "Inclusion and diversity in the workplace allows for diversity of thinking which makes that workplace more competitive"
scale 1 to 10 where 1 is very unlikely and 10 is very likely


33) statediv4 - How likely are you to agree with the following statement: "Inclusion and diversity in the workplace takes the jobs away from Americans and harms our economy"

scale 1 to 10 where 1 is very unlikely and 10 is very likely


34) statedu1 - How likely are you to agree with the following statement: "Education system needs to be based on competition to create higher quality students"

scale 1 to 10 where 1 is very unlikely and 10 is very likely


35) statedu2 - How likely are you to agree with the following statement: "Education system needs to not be based on competition to allow students to flourish on areas they are interested on"

scale 1 to 10 where 1 is very unlikely and 10 is very likely


36) statedu3 - How likely are you to agree with the following statement: "US education system is killing creativity of our children and our future generations"

scale 1 to 10 where 1 is very unlikely and 10 is very likely


37) statedu4 - How likely are you to agree with the following statement: "US education system is biased towards high income families who can afford private and higher quality education for their children"

scale 1 to 10 where 1 is very unlikely and 10 is very likely

38) stategend1 - How likely are you to agree with the following statement: "Women should occupy themselves with household chores and childrearing mainly"

scale 1 to 10 where 1 is very unlikely and 10 is very likely


39) stategend2 - How likely are you to agree with the following statement: "Women's place is at home. If they work, they should be doing jobs like secretaries, teachers, nurses, and nannies"

scale 1 to 10 where 1 is very unlikely and 10 is very likely


40) statework1 - How likely are you to agree with the following statement: "The college education is just for getting the degree.  The real knowledge I will get in the job."

scale 1 to 10 where 1 is very unlikely and 10 is very likely

41) vangogh – Van Gogh

Van Gogh – 1
Other – 2

42) Pollock – Jackson Pollock

Pollock – 1
Other – 2

43) Warhol – Andy Warhol
Warhol – 1
Other - 2

44) Monet – Claude Monet
Monet – 1
Other – 2


45) Freud – Lucian Freud

Freud – 1
Other – 2

46) Favwriter – who is your favorite fiction writer – open ended

47) Favmusician - Who is your favorite musician? – open ended

48) Majorident – What is the major you identify with – even if not your major? – open ended

49) Idealjob - Can you describe in a few words your ideal job? – open ended 

50) Idealpartner - Can you describe in a few words your ideal partner? – open ended

51) Religinst - How often do you attend religious institutions such as churches, mosques, synagogues?
Every day  - 1
Weekly – 2
Monthly – 3
During holidays only – 4
Never – 5
Other – 6



52) Parentsrelig - Do you associate with the same religion as your parents?
Yes – 1
No – 2
Sometimes – 3
Other -4


53) Prayer - How often do you pray in a typical day? - numerical

0 – 0 times
1 – 1 time
2 – times
3 – 3 times
4 – 4 times
5 – 5 times
6 – rarely
7 – sometimes


54) Race

White – 1
Black – 2
Hispanics – 3
Asian – 4
Other/missing – 5

55) Econimmigr - Which statement comes closer to your own views: "Immigrants today strengthen our state because of their hard work and talents" or "Immigrants today are a burden of our state because they take our jobs, housing, and health care"

Immigrants strengthen our state – 1
Immigrants are a burden for our state – 2
Neither of these two statements – 3
Other -4


56) Viewimmigrants - What are your views on immigrants? – open ended

57) Muslim - Thinking about conversations you have had in the past 12 months, how often have you had a conversation with someone who, as far as you know is Muslim?

Daily – 1
Sometimes – 2
Rarely – 3
Never – 4
Other -5 


58) Notwhite - Thinking about conversations you have had in the past 12 months, how often have you had a conversation with someone who, as far as you know is not white?
Daily – 1
Sometimes – 2
Rarely – 3
Never – 4
Other -5 


59) Black - Thinking about conversations you have had in the past 12 months, how often have you had a conversation with someone who, as far as you know is black?

Daily – 1
Sometimes – 2
Rarely – 3
Never – 4
Other -5 


60) White - Thinking about conversations you have had in the past 12 months, how often have you had a conversation with someone who, as far as you know is white?

Daily – 1
Sometimes – 2
Rarely – 3
Never – 4
Other -5 


61) Blackspecial – Do you agree or disagree with the statement that you resent any special considerations blacks receive because it is unfair to other americans?

Strongly disagree – 5
Disagree – 4
Neutral – 3
Agree – 2
Strongly agree 1


62) Racismpast - Do you agree or disagree with the statement that blacks do not need any special consideration because racism is a thing of the past?
Strongly disagree – 5
Disagree – 4
Neutral – 3
Agree – 2
Strongly agree 1

63) Opportunblack - In general do you agree that black children have as good chance as white children in your community to get a good education?
Strongly disagree – 5
Disagree – 4
Neutral – 3
Agree – 2
Strongly agree 1


64) Perceptionblack – what are views of treatments of blacks in your community? – open ended

65) Mealsdinner - What are the top 3 meals  you would serve to a friend who is coming to dinner? – open ended

66) Generationimmi - What generation of immigrant are you?


1st – 1
2nd – 2
3rd – 3
4th or more – 4
no answer – 5
native american – 0 


67) Mealout - How much would you pay for a meal out?

up to $5.00 – 1
$5.01 to $10.00 – 2
$10.01 to $20.00 – 3
$20.01 to $30.00 – 4
$30.01 to $40.00 – 5
more than $40.01 – 6


68) Holidayfreq - How often do you go on holidays in a year?

I never go on holidays – 0

less than once a year – 1

1-2 times per year – 2
3-4 times – 3
more than 3 times – 4
other – 5
(note to self – this scale needs to be changed completely)


69) Leisurereading - How many hours do you spend for leisure reading in a typical day?
I do not read for pleasure – 0 
0-1 hours - 1
2-5 hours – 2
5 – 10 hours – 3
more than 10 hours – 4
other – 5
(not to self – the summer reading is 0 as other now but needs to be included in the scale)


70) Eatingout - How often do you eat out of a week? - if you eat in cafeteria 1, then answer how often do you eat out of cafeteria out of a week?
everyday - 1
1-2 times – 2
2-3 times – 3
3-5 times - 4
never – 5
(note to self – overlapping categories)


71) Clothepref - Do you prefer clothes that are

that reflect fashion and suit your personality – 1
affordable and fashionable – 2
comfortable – 3
chic and stylish – 4
second hand – 5
affordable and practical – 6
classically cut and good value for the money – 7
other – 8
daring and out of ordinary - 9
99 – missing


72) Genremovie - What are your favorite genres of film? Open ended

73) Featurefilm - What is the most important feature of a film?
plot – 1
actors – 2
cinematography – 3
action – 4
director – 5
all of them – 6
music – 7
other - 8

74) Communication -  What is the most common way you communicate socially?



text message – 1
face to face – 2
social media – 3
phone call – 4
other – 5


75) Socializelocation - Where do you go to socialize with your friends?

hangout places
home – 1
bar – 2
shopping mall – 3
restaurant – 4
pub – 5
cinema – 6
club – 7
school – 8
all of the above or missing – 99 


76) Travel – what is your most common mean of travel?

(note to self – this question need to re-phrased so it is clear that we are talking about daily travelling not long term travel)
this question need to be asked differently or create two question, one about how you commute and one about the long travel one.

car – 1
walk – 2
plane – 3
train – 4
bus – 5


77) Alcohol - What is your average alcohol consumption?
never – 0
on holidays and special occasions – 1
weekly – 2
daily – 3
missing – 99
(one answer was on occasions – coded as 1.  Another answer was once a week, coded as 2, the same for weekend – coded as 2. One was monthly – coded as 1; few drinks a month – coded as 2; every few weeks – put as 1)




78) Stairs - How often do you take the stairs instead of elevators?

stairs
never – 0
sometimes – 1
rarely – 2
often – 3
always – 4





79) Depress - How often have you felt very little interest in the things that you were doing in the last month?
never – 0
several days – 1
more than half the days – 2
nearly every day – 3

(all the sometimes, became 1)


80) Lackenergy - How often have you felt tired and with little energy during the last month?
never – 0
several days – 1
more than half the days – 2
nearly every day – 3


81) Failure - How often have you felt tired and with little energy during the last month?

never – 0
several days – 1
more than half the days – 2
nearly every day – 3


82) Rewardinglife - How likely are you agree with the following statement about yourself "I feel like life is very rewarding"

83) Amusing - How likely are you agree with the following statement about yourself "I find most things amusing"
never – 0
several days – 1
more than half the days – 2
nearly every day – 3


84) Cheerful - How likely are you agree with the following statement about yourself "I always have a cheerful effect on others"
never – 0
several days – 1
more than half the days – 2
nearly every day – 3


85) Healthy - How likely are you agree with the following statement about yourself "I feel very healthy"

never – 0
several days – 1
more than half the days – 2
nearly every day – 3

86) Lifecontrol - How likely are you agree with the following statement about yourself "I feel like I am much in control of my life"

never – 0
several days – 1
more than half the days – 2
nearly every day – 3


87) GPA - What is your current GPA?
Open ended

88) Sleephr - How many hours do you sleep in a typical day? – actual hrs



