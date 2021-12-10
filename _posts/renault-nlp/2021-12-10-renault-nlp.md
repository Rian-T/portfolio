---
layout: post
title: Google reviews insight extraction using NLP
date: 2021-11-29 01:00 +0700
description: This is my end of studies project. We have to scrap reviews about renault dealers in France from Google and use NLP to extract some insights about customer satisfaction.
tag:
  - NLP
  - deep learning
---

My end of studies project is in collaboration with Renault, a French car manufacturer. The project is about scraping reviews about renault dealers in France from Google and use NLP to extract some insights about customer satisfaction. The goal is to understand what are the satisfaction levers for customers when they buy a car.

![Full insight extraction pipeline](/assets/renault-nlp/pipeline.png)
*Fig.1 - Full insight extraction pipeline*

The goal is to build an automated pipeline so it can be reused for worldwide renault dealers or for other car manufacturers.

We extracted data from Google reviews using Selenium because the content is dynamically loaded while the user scroll the page. We are now going to analyze our dataset using techniques like data mining (TF-IDF, N-grams), and Sentiment analysis.

## Challenges

Most of the challenges about data extraction are related to the fact that the data is not available in a structured way. We have to extract the data from the HTML code. Sometimes the page where structured in a different way for some reason so our code had to adapt.

Scraping using selenium on hundred on dealers was very slow. We used parallelism to speed up the process.

Finally we have to deal with the fact that our dataset is more or less biased. Most of the reviews are positive, but
longer comments tends to be negative. So most of the text content of our dataset is negative.

## Technologies used

- [Selenium](https://seleniumhq.github.io/)
- [Spacy](https://spacy.io/)
- [NLTK](http://www.nltk.org/)
- [huggingface transformers](https://huggingface.co/transformers/)
