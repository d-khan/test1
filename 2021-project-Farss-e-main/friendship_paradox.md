# Q1 friendship paradox on arXiv data (40 marks)

---
## Background

In this task we will continue to work on the arXiv data we have been working on in PS5. This time, you are required to work on the original data from Kaggle. For simplicity, we only focus on authors that have published any Statistics paper together.

What we want to do this time is to find out whether the _friendship paradox_ is observed in the data. Friendship paradox states that "most people have fewer friends than their friends have, on average". It sounds counter-intuitive but it is generally observed in social network data including facebook "friend" data. Here, we want to find out if "most people have fewer collaborators than their collaborators have, on average".

---
## Description

0. Download the data from https://www.kaggle.com/Cornell-University/arxiv. Unzip the file and put the `arxiv-metadata-oai-snapshot.json` file under the folder `data/`. Please contact the lecturer if you have difficulties in downloading the data
1. Load the data and parse it using the module `json`. Each paper is represented as a `dict` like the following:
```
{'id': '0704.1074',
 'submitter': 'Satoshi Aoki',
 'authors': 'Satoshi Aoki, Takayuki Hibi, Hidefumi Ohsugi, Akimichi Takemura',
 'title': 'Markov basis and Groebner basis of Segre-Veronese configuration for\n  testing independence in group-wise selections',
 'comments': '25 pages, 5 figures',
 'journal-ref': 'Annals of the Institute of Statistical Mathematics (2010). Vol.\n  62, 299--321',
 'doi': '10.1007/s10463-008-0171-7',
 'report-no': None,
 'categories': 'math.ST math.AC stat.AP stat.TH',
 'license': None,
 'abstract': '  We consider testing independence in group-wise selections with some\nrestrictions on combinations of choices. We present models for frequency data\nof selections for which it is easy to perform conditional tests by Markov chain\nMonte Carlo (MCMC) methods. When the restrictions on the combinations can be\ndescribed in terms of a Segre-Veronese configuration, an explicit form of a\nGr\\"obner basis consisting of moves of degree two is readily available for\nperforming a Markov chain. We illustrate our setting with the National Center\nTest for university entrance examinations in Japan. We also apply our method to\ntesting independence hypotheses involving genotypes at more than one locus or\nhaplotypes of alleles on the same chromosome.\n',
 'versions': [{'version': 'v1', 'created': 'Mon, 9 Apr 2007 07:59:09 GMT'},
  {'version': 'v2', 'created': 'Wed, 6 Feb 2008 00:58:16 GMT'}],
 'update_date': '2010-02-18',
 'authors_parsed': [['Aoki', 'Satoshi', ''],
                    ['Hibi', 'Takayuki', ''],
                    ['Ohsugi', 'Hidefumi', ''],
                    ['Takemura', 'Akimichi', '']]}
```

For each Statistics paper, get the author pairs and create some data structure like a `dict` of `list` or `dict` of `set` to store a sequence of collaborators for each author that has any collaborators. Example:
```
{'Satoshi Aoki': set('Takayuki Hibi', 'Hidefumi Ohsugi', 'Akimichi Takemura', ...),
 ...,
 'Takayuki Hibi': set('Satoshi Aoki', 'Hidefumi Ohsugi', 'Akimichi Takemura'),
 ...}
```

Note:
* There are two places you can get the author information - `'authors'` or `'authors_parsed'`. Please make sure the author names you get are sensible regardless which one you use. Please state the assumptions you made about the author names. The name above is in the order "first_name last_name", but you can do "last_name first_name" if you want to.
* Your result may be different from what I have shown here due to:
  * The data is updated in a weekly basis - these authors may publish some more papers after this project is released!
  * Different assumptions about the author names

2. From (1), find out the number of collaborators for each author. You should have some data structure like a `dict`, with the names of the author as keys and the number of collaborators of the corresponding authors as the values. Example:
```
{'Satoshi Aoki': xx,
 ...,
 'Takayuki Hibi': 3,
 ...}
```

Again it is possible that you will get a different result.

3. From (2), for each author, find out the average number of collaborators of his/her collaborators. For example, if `'author_a'` has 2 collaborators `'author_b'` and `'author_c'`. `'author_b'` has 5 collaborators where as `'author_c'` has only 1 collaborator. Then the average number of collaborators of his/her collaborators is 3.

  From there, find out on average how likely we see an author has fewer collaborators than his/her collaborators have. For example, if there are 10,000 authors, 8,000 of them have fewer collaborators than their collaborators have, then it is 80%. Conclude whether the friendship paradox is observed.

4. Try to explain the result. Please do the following:
  * Plot the number of collaborators from (2) using histogram and/or boxplot. What do you observe?
  * For the author with the highest number of collaborators, search his name on [Google Scholar](https://scholar.google.com/schhp?hl=en). Have a look of some of the papers. What do you observe?

  Based on what you have found out in (4), are you convinced by your conclusion in (3)?

---
## Assumptions

* "Statistics paper": We define a paper is "Statistics paper" with `'stat.'` (e.g. stat.TH, stat.TH, etc) in `'categories'`. For example, there is `stat.AP` (and also `stat.TH`) for the example above and therefore we consider this as a Statistics paper
* "Collaborators": We assume two authors are collaborators if they have published any Statistics paper together based on the arXiv data. From the entry above we know that `Satoshi Aoki` and `Takayuki Hibi` are collaborators

---
## Coding description and additional requirements

* Use function for some part of the code, and test it by using `assert` with some test cases. For example, you can write a function to find the average number of collaborators for a given author name and the data structure in the same structure as the one from (2)
* Part 1:
  * You can use any functionality from the `json` module
  * Make sure relative path is used when loading in the data
  * Please do not submit the data! It is too large to upload it. Data will be added back from us when your submission is marked
  * Make sure you state clearly your assumptions about the author names
* Part 4:
  * You can use google and use any python libraries. You can for example use `matplotlib` for graph plotting

---
## Things to show in the report

* You may write all your code for this task in the report, but in the report you _must_ include:
  * Testing
  * Result and explanation for part 4
  * Assumptions, discussion of the limitations and possible improvement of your implementation and analysis
  * Any references you used for part 4

---
## Tips

* The data is very large! You may want to first work on subpart of the data, make sure your code is correct for part 1 - 2, before moving on to work with the whole data
