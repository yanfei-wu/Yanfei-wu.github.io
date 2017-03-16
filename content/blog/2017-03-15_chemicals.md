+++
draft = false
image = "blog/chemicals_file/beauty.jpg"
date = "2017-03-15"
title = "Toxic Beauty: Chemicals in Cosmetics"
type = "post"
author = "Yanfei Wu"
description = "This post shows some facts you should know about your beauty products. It focuses on data cleaning and visualization."
tags = [
"Python",
"data cleaning",
"data visualization"
]
+++



### [Introduction](#introduction)
### [Data Cleaning](#data-cleaning)
		#### [Missing Data](#missing-data)
### [Duplicates](#duplicates) 
### [Data Visualization](#data-visualization)
		#### [vis1]
		#### [vis2]
		#### [vis3]
### [Summary](#summary)


### Introduction

How many different beauty products do you apply onto your face and body everyday? How many chemical ingredients do they contain? And how many of those chemicals are toxic?   

I admit that I have been a little careless when it comes to the safety of my cosmetic products. Then one day I came across a [dataset](https://www.healthdata.gov/dataset/chemicals-cosmetics) from California Safe Cosmetics Program in California Department of Public Health. It appears that companies (manufacturer, packer, and/or distributor named on the product label) must submit a list of all products that contain any ingredients *known or suspected to cause cancer, birth defects, or other developmental or reproductive harm* if the company has annual aggregate sales of cosmetic products of one million dollars or more, and has sold cosmetic products in California on or after January 1, 2007. So I started to dig into this dataset because I was very curious about what exactly were reported. Let me walk you through what I did.  

### Data Cleaning 
#### Missing Data 
The dataset has 80,004 rows and 22 columns. We can visualize columns containing missing data using a heatmap.  

We can see that most rows in the `'DiscontinuedDate'` and `'ChemicalDateRemoved'` columns are missing. `'CSFId'` and `'CSF'` also contains a lot of missing data, followed by `'CASNumber'` and `'BrandName'`.  

We know that typical ways of dealing with missing data include deleting rows/columns with missing values and filling the missing values with some value. The first approach is the easist but caution needs to be taken because we can potentially lose some important information. In our case, the `'DiscontinuedDate'` and `'ChemicalDateRemoved'` columns give information about product discontinuation or reformulation. So the missing values can simply mean these products are still on sale and no reformulation has been done. 

`'CSFId'`, `'CSF'` and `'CASNumber'` are about 

`'BrandName'` is something I am interested in and the good news is that there are much less missing values. So let's see if we can fill in these values with the knowledge we gained from other columns. It turns out that `'CompanyName'` is helpful as shown in the plot below.

These products with a missing `'BrandName'` actually come from 6 companies and two of them are costematic companies. Based on a quick googling, they each carries one brand (brand name is the same as the company name). So we can simply fill in the brand names for products from these two companies.  


#### Duplicates 


### Data Visualization 

### Summary
*Note*: All products containing carcinogens or developmental or reproductive toxicants may not be included, due to companies failing to report. 