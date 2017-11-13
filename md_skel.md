---
title: "Main title goes here"
author: "Name of Author"
date: "2017-04-25 08:00:00"
meta: Tutorials
subtitle: "Subtitle goes here"
layout: post
tags: datavis modelling github 
---
<div class="block">
	<center>
		<img src="{{ site.baseurl }}/img/tutheader_tutname.png" alt="Img">
	</center>
</div>

### Tutorial Aims

#### <a href="#section1"> 1. The first section</a>

#### <a href="#section2"> 2. The second section</a>

#### <a href="#section3"> 3. The third section</a>

This is some introductory text for your tutorial. Explain the skills that will be learned and why they are important. Set the tutorial in context. In this example tutorial we will be learning how to generate some fake bivariate data in `R` and make a scatter plot.  Normally no more than 4 lines, nobody likes reading lots of text.

You can get all of the resources for this tutorial from <a href="<GITHUB_URL>" target="_blank">this github repository</a>. Clone and download the repo as a zip file, then unzip it.

<a name="section1"></a>

## 1. The first section

First, we need to ask the student to open `RStudio`, create a new script by clicking on `File/ New File/ R Script` set the working directory, and load some packages. The packages we will be using are `ggplot2` and `dplyr`. Specifically, from `dplyr` we will be using pipes `%>%` and the `filter()` function. Notice how I surrounded package names, software package names, actions ("File/ New..."), functions and operators in backticks (````) to define them as inline code blocks. This helps these important bits stand out to the reader. Enter the following into your script file to set the working directory and load some packages: 

```
# Set the working directory
setwd("~/coding_club/bes_2017")

# Load packages
library(ggplot2)
library(dplyr)
```

If `library()` returns an error it might be because you haven't installed the package before. To rectify this, run `install.packages("pkg_name")` first, then `library()`.

<a name="section2"></a>

## 2. The second section

Now that we have set everything up we can make some fake data, `rnorm()` generates samples from a normal distribution. `n` is the number of data points, `mean` is the mean value of the distribution, `sd` is the standard deviation:

```
# Create fake data
x_dat <- rnorm(n = 100, mean = 5, sd = 2)  # x data
y_dat <- rnorm(n = 100, mean = 10, sd = 0.2)  # y data
xy <- data.frame(x_dat, y_dat)  # combine into data frame
```

Now we can remove `x_dat` values greater than 7.5 using `filter()`:

```
xy_fil <- xy %>%  # Create object with the contents of `xy`
	filter(x_dat < 7.5)  # Keep rows where `x_dat` is less than 7.5
```

And finally, plot the data:

```
ggplot(data = xy_fil, aes(x = x_dat, y = y_dat)) +  # Select the data to use
	geom_point() +  # Draw scatter points
	geom_smooth(method = "loess")  # Draw a loess curve
```

At this point it would be a good idea to include an image of what the plot is meant to look like, so students can check they've done it right. Replace `IMAGE_NAME.png` with your own image file:

<center> <img src="{{ site.baseurl }}/img/IMAGE_NAME.png" alt="Img" style="width: 800px;"/> </center>

<a name="section1"></a>

## 3. The third section

If I'm making a tutorial on `ggplot2` I might want to include a brief table of different plot methods, so students can experiment:

<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg th{font-family:Arial;font-weight:normal;padding:10px 5px;border-style:solid;border-width:1px;word-break:normal;}
</style>
<table class="tg">
  <tr>
    <th>Name</th>
    <th>Code</th>
  </tr>
  <tr>
    <th>Scatter points</th>
    <th>`geom_point()`</th>
  </tr>
  <tr>
    <th>Smoothed curves</th>
    <th>`geom_smooth()`</th>
  </tr>
  <tr>
    <th>Observations connected by line</th>
    <th>`geom_line()`</th>
  </tr>
</table>

This is the end of the tutorial. Summarise what the student has learned, possibly even with a list of learning outcomes. In this tutorial we learned:

##### - how to generate fake bivariate data
##### - how to create a scatterplot in ggplot2
##### - some of the different plot methods in ggplot2

Lastly, I might give some useful links. For more on ggplot2, read the official <a href="https://www.rstudio.com/wp-content/uploads/2015/03/ggplot2-cheatsheet.pdf" target="_blank">ggplot2 cheatsheet</a>.

Everything below this is footer material.

<hr>
<hr>

#### Check out our <a href="https://ourcodingclub.github.io/links/" target="_blank">Useful links</a> page where you can find loads of guides and cheatsheets.

#### If you have any questions about completing this tutorial, please contact us on ourcodingclub@gmail.com

#### <a href="INSERT_SURVEY_LINK" target="_blank">We would love to hear your feedback on the tutorial, whether you did it in the classroom or online!</a>

<ul class="social-icons">
	<li>
		<h3>
			<a href="https://twitter.com/our_codingclub" target="_blank">&nbsp;Follow our coding adventures on Twitter! <i class="fa fa-twitter"></i></a>
		</h3>
	</li>
</ul>

### &nbsp;&nbsp;Subscribe to our mailing list:
<div class="container">
	<div class="block">
        <!-- subscribe form start -->
		<div class="form-group">
			<form action="https://getsimpleform.com/messages?form_api_token=de1ba2f2f947822946fb6e835437ec78" method="post">
			<div class="form-group">
				<input type='text' class="form-control" name='Email' placeholder="Email" required/>
			</div>
			<div>
                        	<button class="btn btn-default" type='submit'>Subscribe</button>
                    	</div>
                	</form>
		</div>
	</div>
</div>






