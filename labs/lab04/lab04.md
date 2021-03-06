431 Lab 04
================
Last Edited 2020-10-04 15:39:14

# Instructions

Lab 04 includes 8 questions. Be sure to respond to each question by the
deadline posted on the [Course
Calendar](https://thomaselove.github.io/431/calendar.html).

You are welcome (encouraged, really) to discuss Lab 04 with Dr. Love,
the teaching assistants and even your colleagues, but your answer must
be prepared by you alone. Don’t be afraid to ask questions, either via
[Piazza](https://piazza.com/case/fall2020/pqhs431) (use the lab04
folder), at [TA office
hours](https://thomaselove.github.io/431/contact.html) or before/after
class.

Your response to **every** question, whether we explicitly ask for it or
not, should include a complete English sentence responding to the
question. Code alone is not a sufficient response, even if the code is
correct. Some questions, of course, don’t require any code.

We have not provided a template for this Lab. You are encouraged to
adapt one of the previous templates for this purpose.

## Submitting your Response

Build your entire response as an R Markdown file. Then knit the file to
create an HTML document. Submit both your R Markdown file and the HTML
output file to [Canvas in the Lab 04 section of the Assignments
folder](https://canvas.case.edu) by the deadline specified in [the
Course Calendar](https://thomaselove.github.io/431/calendar.html).

## Minimal Setup

The minimal setup for this assignment involves loading two relevant R
packages, as shown below. In our answer sketch we may add additional
packages, and you are welcome to do so in your response, as well.
Remember to load the tidyverse last.

``` r
library(palmerpenguins); library(tidyverse)
## make sure these libraries are installed in R
## always need tidyverse, also need palmerpenguins for Lab 04
```

# Setup for Questions 1-5

Find a headline from the internet related to health or medicine that
describes the findings of a study published on January 1, 2017 or later.
Then find the study being referred to in PUBMED. Use the [formula for
updating your opinions about health news developed by Jeff
Leek](http://fivethirtyeight.com/features/a-formula-for-decoding-health-news/),
along with the abstract and full contents of the published study to
complete Questions 1-5. While it won’t be necessary to prepare any R
code to respond to Questions 1-5, we think it will be good practice for
you to prepare your response in R Markdown anyway.

# Question 1 (5 points)

Specify the URL where we can see the headline and news story describing
the findings of the study. Feel free to use `bit.ly` or a related tool
online to produce a shortened URL for this purpose. Specify the
reference completely, including the names of the author(s) of the news
story, and its full title, and source.

# Question 2 (5 points)

Specify a URL where we can see at least the abstract of the complete
study. Again, shortened URLs are fine. Give the complete reference to
the study, as well, including the authors, full title, journal name and
so forth.

# Question 3 (10 points)

Describe, in a few sentences, your original opinion (gut feeling)
related to the conclusions of the study as summarized in the headline
and news article, first in terms of a probability statement, and then
calculate the appropriate odds, remembering to convert statements about
probabilities to statements about odds. Provide some motivation for your
internal prior probability, describing your relevant personal
experiences or other factors that drove your gut feeling.

Remember, if X is an event, and Pr(X) is the probability that X occurs,
and odds(X) are the odds that X occurs, then

**Pr(X) = odds(X) / \[1 + odds(X)\]**

and

**odds(X) = Pr(X) / (1 - Pr(X))**.

# Question 4 (20 points)

Evaluate the study in terms of the six specifications [proposed by
Leek](http://fivethirtyeight.com/features/a-formula-for-decoding-health-news/)
when evaluating study support. Be sure to specify your conclusion about
**each** of the six specifications, and provide direct quotes and
summarize the evidence from the abstract or paper to address the issues
raised and justify your conclusions.

# Question 5 (20 points)

Incorporate the study support assessment into a Bayes’ Rule calculation
to obtain the final odds you should now be willing to give to the
headline, and specify this value in terms of a probability statement, as
well. Then react to the final conclusion specified by this approach in a
few sentences. How does your subjective posterior probability that the
headline is true match up with the formula’s conclusions? Do you feel
that the formulaic approach has yielded an appropriate conclusion for
you in this case? Why or why not?

# Setup for Questions 6-8

We’ll be using the `penguins` data (note: use the `penguins` tibble, and
not the `penguins_raw` tibble for this Lab) contained in the
`palmerpenguins` package in R. The complete citation is …

Horst AM, Hill AP, Gorman KB (2020). palmerpenguins: Palmer Archipelago
(Antarctica) penguin data. R package version 0.1.0.
<https://allisonhorst.github.io/palmerpenguins/>. doi:
10.5281/zenodo.3960218.

Additional information on the data are provided:

  - by Allison Horst at the github site cited above. In particular,
    you’ll find a nice cartoon of [the three species of penguin
    contained in the
    data](https://github.com/allisonhorst/palmerpenguins#meet-the-palmer-penguins)
    and a detailed [description of the bill
    measurements](https://github.com/allisonhorst/palmerpenguins#bill-dimensions)
    that are worth your time, and
  - in [Chapter 2 of the Course
    Notes](https://thomaselove.github.io/431-notes/looking-at-the-palmer-penguins.html).

You’ll be building plots in Questions 6-8, and we want you to use the
tidyverse (specifically the ggplot2 package) to do so.

# Question 6 (10 points)

Suppose we are interested in which of the three species of penguin
(*Adelie*, *Chinstrap* or *Gentoo*) shows the strongest *linear*
relationship between bill length and body mass, now using all 342
penguins with complete data on the two variables we’re studying (bill
length and body mass.)

Draw an attractive and thoughtfully labeled plot (including a title) to
show the association of bill length (placed on the horizontal x axis)
and body mass (on the vertical y axis) for these 342 penguins, and facet
the plot by species (so that one facet shows the 151 Adelie, one shows
the 68 Chinstrap and one shows the 123 Gentoo.) Use `geom_smooth()` to
add an appropriate smooth curve (using `lm` or `loess` or both, as you
prefer) to each facet of the plot.

Then write a sentence or two describing what your plot reveals.

# Question 7 (15 points)

Build a linear model predicting body mass using bill length for the
species which has the largest body mass (on average) across the three
species.

Then use that equation to estimate the difference in the predicted body
mass for two new penguins of that species (named Pingu and Skipper),
where Pingu whom has a bill length at the 75th percentile of the
original data for that species, and Skipper has a bill length at the
25th percentile of the original data for that species? Maintain two
decimal places for any intermediate calculations, although your final
response should be provided in grams (as an integer.)

In a summary sentence or two describing your results, be sure to specify
which species you are studying and which of the two new penguins (Pingu
or Skipper) would be expected to have a larger body mass (and by how
much), according to your model.

# Question 8 (15 points)

Now, let’s focus just on our outcome, and how it is associated with
species and island. Build a plot that shows the distribution of body
mass (in grams) within each penguin species, and which also identifies
the three islands (through the use of facets) in an attractive way. Your
plot should have a meaningful title as well as useful axis and facet
labels. Please restrict the plot to the 342 penguins with complete body
mass information.

Then, in a sentence or two, describe the results from your plot, and any
reasonable conclusions you can draw from the plot about the
relationships between island and species, and between body mass and the
other two variables.

## On Grading

Note that Question 6 was graded out of 10 points, even though it was
originally intended to be graded out of 15 points. In computing your
final score on the Lab, you received 5 additional points if your R
Markdown and HTML files were in and readable, on time, so that the total
possible score on the Lab was actually 105.

Lab 04 will be graded on a 100 point scale, even though there are 105
available points, so that some people may score higher than 100. You
will receive some credit for making a reasonable effort to build a good
response to each question, and then additional credit if your response
is (essentially) correct, your code is clean (in the sense that it is
complete and can be run without modification to produce appropriate
results) and you’ve written using complete and grammatically correct
English sentences.

A more detailed grading rubric will accompany the answer sketch.
