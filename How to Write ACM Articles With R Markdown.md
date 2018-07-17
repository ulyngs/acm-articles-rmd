# How to Write ACM Articles With R Markdown

I love [R Markdown] (https://bookdown.org/yihui/rmarkdown/). I use R for almost all my data analyses and visualisations these days, and R Markdown documents helps me keep a kind of interactive lab notebook that reminds me of the steps I took - and why - and makes it quick and easy to reproduce everything.

Like many others (e.g. [here] (https://rosannavanhespenresearch.wordpress.com/2016/02/03/writing-your-thesis-with-r-markdown-1-getting-started/), [here] (https://eddjberry.netlify.com/post/writing-your-thesis-with-bookdown/), and [here] (https://github.com/benmarwick/huskydown)), I too am planning to write my entire PhD thesis in R Markdown. The benefits are obvious, as other blog posts and online publications have already pointed out: First, you reduce the risk of mistakes by doing your academic write-up in the very same file as you use to produce the analysis outputs - when you update analysis code, the output plots are automatically updated too (this [wonderful YouTube video] (https://youtu.be/s3JldKoA0zw) will remind you that this is important and how awesome you will feel when you do things write). Second, you save yourself effort if you e.g. want to publish your thesis as an ebook or physical book afterwards, or if you usually write in LaTeX but collaborate with MS Word users: From the same R Markdown file, you can export to the format you need. 

So, like many others (this [blog post by Colin Bousige] (https://colinbousige.github.io/post/rmarkdown/) I found especially helpful!), I want to transition entirely to writing in R Markdown also when writing submissions to academic conferences and journals.

In my research group, one of the most important outlets for our work is ACM CHI (Conference on Human Factors in Computing Systems). However, I ended up spending several frustrated hours wrapping my head around how to use the ACM LaTeX template properly. RStudio has made the `rticles` package which is meant to include templates for writing R Markdown documents formatted to the submission standards of loads or academic journals and conferences, including a [generic ACM template] (https://github.com/rstudio/rticles/tree/master/inst/rmarkdown/templates/acm_article). However, it was not obvious to me how the exact templates were arrived at (many are crowd-contributed and does not seem to come with any documentation for the individual templates), and the outputted result didn't seem to correspond exactly to the usual official ACM LaTeX templates anyway!

Besides, for the next CHI conference, it turns out the ACM just updated the templates (at the time of writing, the last update to the master templates happened on July 17, 2018, i.e. today!). So the question remains: **What is the route of least effort for using R Markdown to write articles for CHI?**

Turns out the answer is very simple, but it took me way longer to figure out that it should have done, as I couldn't really find the right advice anywhere. **Here's how to do it:**

## Step 1. Understand how to use (the ACM) LaTeX template with R Markdown
So first things first. In order to use the ACM template, we'd download the latest version [from here] (https://www.acm.org/publications/proceedings-template) - but for the purposes of this tutorial, clone or download [this GitHub repo] (https://github.com/ulyngs/acm-articles-rmd). Then open the R Project file in the 'step1' folder.

![step 1 files](figures/step1-files.png "Step 1 files")

This folder contains the essential files to make the sigchi proceedings template work (it's just a subset of the files in the acmart-master folder that you can download on the ACM page linked to above):
- acmart.cls provides the LaTeX class for the new ACM master template
- ACM-Reference-Format.bst provides the bibliography formatting
- sample-sigchi.tex provides the LaTeX template for sigchi-proceedings (as you can read in the documentation in acmart.phf, you just change the article format in this LaTeX template in order to output a format for e.g. sigchi-extended abstracts rather than the proceedings format)
- all the other files are just there to provide the sample content that's shown by default in the template - images (files.eps, fly.eps, rosette.eps, and sampleteaser.pdf), bibliography (sample-bibliography.bib), and sample content (samplebody-conf.tex)

Now, as you will see if you open step1.Rmd, the only thing we need to include in the r markdown file to use the CHI template is the following YAML header:

```
---
output:
	pdf_document:
		template: sample-sigchi.tex
---
```

If you click 'Knit', the 

## Step 2. Adjust the LaTeX template to include the R Markdown as body text

## Step 3. Make sure citations are shown correctly

## Step 4. Handling figures and tables

## Step 5. Celebrate!

