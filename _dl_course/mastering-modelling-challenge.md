---
layout: course
title: "Data analysis and modelling challenge: Seabird population dynamics" 
---

This challenge will require the use of data manipulation, visualisation and analysis skills, and is the culmination of the [MASTERING MODELLING]({{ site.baseurl }}/dl_course/mastering-modelling/index.html) course stream. You will find here all the instructions you need to complete the challenge. 

## Challenge outline and objectives

The Isle of May, located on the east coast of Scotland, is a nature reserve home to large colonies of seabirds. A long-term monitoring programme is in place, and every year, scientists and volunteers record information about the abundance, breeding success, and diet of seabirds such as puffins, fulmars, kittiwakes, shags, guillemots, and razorbills. There is concern that with changing climate, the abundance of sandeels (and the plankton upon which they depend), a favourite food resource for birds, will decrease or shift temporally so that the availability will be reduced at the critical time of breeding and chick rearing. 

Your mission will be to analyse the breeding success and other behaviours of seabirds compiled and summarised by the [Centre for Ecology and Hydrology](http://ceh.ac.uk/) to assess the health of these seabird populations. You will look for temporal trends, but also for environmental factors which may influence the breeding of the birds.

## Data overview 

You will use the following datasets, available to download from the [Challenge repository](https://github.com/ourcodingclub/CC_course_challenge3) on GitHub. To be able to answer the quiz questions properly, it is important that you use these datasets and not potentially updated versions available through the original providers. 

### CEH's Isle of May Long-Term Study data__

* __Breeding success of sea birds (IMLOTSBSDataset1982-2016.csv)__: compiled as the number of chicks fledged per nest. Original data link [here](https://catalogue.ceh.ac.uk/documents/02c98a4f-8e20-4c48-8167-1cd5044c4afe).
* __Dive times and depths of auks (IoM_AukDiving.csv)__: from the Isle of May outside the breeding season, obtained by fitting birds with data loggers. Original data link [here](https://catalogue.ceh.ac.uk/documents/6ab0ee70-96f8-41e6-a3e3-6f4c31fa5372).

### Climate data from the Met Office

* __clim_east_Scotland.csv__ For the East of Scotland, extracted and compiled by us. It contains: 
	* minimum, mean and maximum monthly temperatures (°C)
	* monthly sunshine (hours)
	* monthly rainfall (mm)

The dataset also contains seasonal averages of these variables. Winter: Dec-Feb, Spring: Mar-May, Summer: June-Aug, Autumn: Sept-Nov. (For winter, year refers to Jan/Feb). Original data link [here](https://www.metoffice.gov.uk/climate/uk/summaries/datasets).

## Specific tasks 

Here is a detailed list of the tasks you should achieve within this challenge. Remember that a challenge is meant to be, well, challenging, and therefore we are setting you goals but the choice of workflow and functions to achieve them is up to you! We also list the questions that will be asked in the quiz at the end to confirm your successful completion - we suggest you take note of your answers as you go.

### 1. Temporal trends in breeding success

You will import the breeding success data, and plot the time series and a line of best fit for each species. __Specifically, you should:__ 

* Reshape the data for analysis, with a “species” column. 
* Create a faceted plot showing the time series and a line of best fit for each species. 
* Run a linear regression for each species and extract slopes, confidence intervals and goodness of fit information for these models. (Look at the [Help & Hints](#hints) section if you cannot find a way to automate this – you should not copy and paste your code six times!).
* Create a visualisation of your choice showing the slope estimate and confidence intervals for each species, so that is clear which slopes differ from zero.

__Be prepared to answer the questions:__ 

* From looking at the plot, which species (2) seem to have the greatest inter-annual variability in breeding success?
* From the model, which species has/have experienced a significant increase?
* From the model, Which species has/have experienced the strongest decrease?
* For which species did you get the best goodness of fit? 

### 2. Does climate affect breeding success?

There is growing evidence that climate change affects the dynamics of seabird populations, for instance by disrupting the timing and availability of food resources such as sandeels (and the plankton upon which eels depend).

You will design a hierarchical model to test for the influence of climate on breeding success. First, you may assume that species might show similar responses and therefore want to predict seabird breeding success as a function of climate only, with other factors perhaps introducing some non-independence in the data. 

__Specifically, you should:__

* Subset your breeding success dataset to exclude shags (if you’ve completed the first section, you probably saw that they’re not following the same trends as other species)
* Design a random-intercept mixed-model approach to answer the question. Use June max temperature (when chicks hatch and are reared) as the explanatory variable – but feel free to experiment with other possibly meaningful climate variables. 
* Extract and plot the predicted values from the model using the ggeffects package, and overlay the raw data on the graph. 

__Be prepared to answer the questions:__

* What are your random effects? 
* Does June temperature affect the breeding success of seabirds? 

_Remember that we are working with summarised data rather than the raw data, which limits our modelling options._ If we had access to the raw dataset, it would contain counts (integer) of actual fledglings per nest, with a row for each of the hundreds of nests surveyed. __With this in mind, have a think about:__

* What data distribution would you use to answer the same question as above?
* What random effect structure would you choose? 

### 3. Dive deeper! (Optional)

The _Dive times and depths_ dataset contains information about the diving behaviour of monitored seabirds. It is a fairly large dataset with some interesting features, and is therefore ideal to test your data manipulation skills. So if you feel like going further in your data wrangling and modelling journey, try to answer the following questions: 

* Does dive depth vary among species, and between males and females of the same species? 
* Does dive duration also vary? 

The dataset contains the logged start and end time of each dive – to get you started, you’ll need to convert these to POSIXct format and calculate the duration of the interval. Don’t forget to remove the obvious outliers of impossible dive times (very long or negative), probably indicative of logger failure!

For __an extra challenge__, why don’t you try answering those same questions using a Bayesian framework?

## Getting started

Download the [challenge repository](https://github.com/ourcodingclub/CC_course_challenge3), which contains all the data you need, and create a new script for your challenge. Refer to this page to make sure you are answering all the questions. 

There is no script or code provided for this challenge: how you go about solving the tasks is entirely up to you! You may want to refer to the tutorials listed below (and other online resources). 

## Finished? Take the test! 

Once you have a fully working script and have completed the specific tasks, take the test. 

{% capture link %} INSERT LINK {% endcapture %}
{% include link-button.html url=link button="Coming soon" %}

## Help & hints 
{: #hints}

Here is a list of tutorials that might help you: 

* [Intro to model design]({{ site.baseurl }}/tutorials/model-design/index.html)
* [Efficient data manipulation]({{ site.baseurl }}/tutorials/data-manip-efficient/index.html)
* [Intro to linear mixed models]({{ site.baseurl }}/tutorials/mixed-models/index.html)
* [Working efficiently with large datasets]({{ site.baseurl }}/tutorials/data-manip-efficient/index.html): this one was not part of the stream but has some _very useful_ snippets that might help you run multiple linear models and extract their outputs ( _wink wink_ ).

### Need a hint? Just click on a question to expand. 

{% capture reveal %}
There is a handy package in the `tidyverse` called `broom`. We suggest you take a look at the `tidy` and `glance` functions. Combined to some of our favourite `dplyr` functions for grouping, you'll be unstoppable!
{% endcapture %}
{% include reveal.html content=reveal button="How do I avoid running copying my linear model code for the six different species?" %}

{% capture reveal %}
The first thing you probably want to do is to subset the climate data to the period and variables of interest: the `filter` function will be your friend here.

Then, find a variable that is shared by both datasets (there's only one!) and `merge` or `join` them together.
{% endcapture %}
{% include reveal.html content=reveal button="How do I bring the climate data into all this?" %}
 
We love getting your feedback, and will add more hints to this section if you get in touch and tell us where you struggled in this challenge!

## Acknowledgements 

We thank all the organisations that provided open access data for this challenge. The datasets licences are as follow: 

* __Newell, M.; Harris, M.P.; Wanless, S.; Burthe, S.; Bogdanova, M.; Gunn, C.M.; Daunt, F. (2016).__ The Isle of May long-term study (IMLOTS) seabird annual breeding success 1982-2016. Available from the [NERC Environmental Information Data Centre](https://doi.org/10.5285/02c98a4f-8e20-4c48-8167-1cd5044c4afe) under an Open Government License.
* __ Dunn, R.E.; Wanless, S.; Green, J.A.; Harris, M.P.; Daunt, F. (2019).__ Dive times and depths of auks (Atlantic puffin, common guillemot and razorbill) from the Isle of May outside the seabird breeding season. Available from the [NERC Environmental Information Data Centre](https://catalogue.ceh.ac.uk/documents/6ab0ee70-96f8-41e6-a3e3-6f4c31fa5372) under an Open Government License.
* __Met Office (2019).__ Regional time series of monthly, seasonal and annual values. Available from the [Met Office Datasets page](https://www.metoffice.gov.uk/climate/uk/summaries/datasets) under an Open Government License. Crown Copyright.
