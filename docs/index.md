--- 
title: "A Compact Guide to Classical Inference"
author: "Daniel Kaplan"
date: "2019-11-01"
site: bookdown::bookdown_site
documentclass: book
bibliography: [book.bib]
biblio-style: apalike
link-citations: yes
description: ""
---

# What is classical inference?

Statistical inference is the logic and methods for creating statistical claims that are justified by data. A *statistical claim* is a statement like this: My data show that taking aspirin is associated with a reduction in fever. Or this: My data show that for every year of age, middle-aged runners slow down, on average, by 20-40 seconds per mile.

Statistical inference was invented to guard against spurious claims. For instance, suppose you had these data on age and running times (in minutes) in a 10-mile road race:

Person | Age | Running Time
-------|-----|--------------
John   | 48  | 105
Abigail| 40  | 101

Just comparing the ages and running times of John and Abigail, you can see that John is 4 minutes (that is, 240 seconds) slower than Abigail in completing the 10 mile run. Their age difference is 8 years. This amounts to and additional 30 seconds of running time per year of age difference. (240 / 8 = 30.) Since you are uncertain -- this is only one race, this is only two people, etc. -- you decide to frame your findings this way: My data show that middle-aged runners slow down by 20-40 seconds/mile for every year additional age. That is a statistical claim.

There are many problems with this statistical claim. First, it's comparing people with more differences than 8 years of age. To judge from the names, John is a man and Abigail a woman. A different statistical statement prompted by the data is that women are faster than men by 30 seconds per mile. Or, it might be that Abigail is an experience runner and John is a formerly lethargic man who has been trying to build up to being able to run 10 miles. (Congratulations, John! A ten-mile time of 105 minutes is a pretty impressive accomplishment.)

Common sense -- and good statistical practice -- tells you to compare like with like. Wouldn't it be better to compare men of different ages who are both running their first 10-mile race? Or, how about looking at Abigail's past records from when she was younger? The failure to do things like this is reason enough to be skeptical about the 20-40 seconds/mile per year claim. But this is a flaw in study design and the collection of data. That is not the kind of flaw that statistical inference deals with.

Statistical inference deals with one, and only one, source of uncertainty: that produced by the size of the sample, in this case 2 people. Again, common sense tells you that two is not a lot of data. So, how much would be enough? 10? 100? 1000? Or, put another way, how should you frame the uncertainty in your claim due to limited data? In the example, the 20-40 seconds/mile per year interval was made up to create an impression of scientific precision. Statistical inference techniques create a meaningful interval that stems from the data itself, rather than the imagination of the researcher. 

The need for statistical inference became important when it was realized, around 1900, that there was not yet a reliable way of knowing how much data -- that is, how many rows of data -- is sufficient. The founders of statistical inference found ways to frame the problem in terms of the mathematics of probability, and used algebra and other mathematical techniques to solve the problem. They summarized the process of statistical inference using formulas and tables of probabilities. This is *classical* inference.

Algeba and other mathematical arguments can be difficult and subtle. In the early days of classical inference there were disagreements about what formulas would be best. To develop ideas and confirm that their formulas gave reasonable results, some of the founders of classical inference used *simulations*. One simulation, for instance, involved writing down data for 3000 individual people on index cards, shuffling the cards, then dealing out hands of 4 cards each. With 1000 such events, it was straightforward -- but extremely tedious -- to see what results were likely and which not.

The algebraic techniques were pretty much the only way to conduct statistical inference until the 1970s. Then, as computing became available at research institutions, the simulation technique became easy enough to be practical for routine problems in statistical inference. Simulation on computers became a potential substitute for algebra. 

Perhaps many students would agree that anything that reduces the amount of algebra needed to solve a problem is worthwhile. But this is not the fundamental reason why simulation is an important technique. Yes, simulation is easy, but because it's easy it can be applied to situations which were too complicated to handle reliably with algebra, even by the best of mathematicians. The simulation approach to statistical inference has been called *computer-age statistical inference* to distinguish it from *classical statistical inference*.

## ... and why should I read this book? {-}

We live in the computer age, so you might suppose that statistics courses would use computer-age statistical inference. By and large they do not. Why not? There is one good reason and several bad reasons for this. And these reasons -- good and bad -- determine whether you should read this book.

Classical inference is the only way to conduct statistical inference for very small data, say with 10 or fewer rows of data. So if you are working with small data, you need to learn classical inference.

And even if you don't need to work with such small data, there may be reasons for you to learn something about classical inference. One is that, if you are taking an introductory course, chances are a substantial part of the course is about classical inference. This is more or less a "because I said so" justification for studying a topic. 

Putting aside the matter of small data, instructors use classical inference because that is what they were taught. They don't use simulation for a variety of reasons: they may not know about the computer-age techniques, they may not be comfortable teaching how to use a computer, they may see algebra as prestigious and computing as low-class, they may think their students don't have access to computing (and in some places, this might be right), they may have been forced to use the n^th^ edition of a textbook originally written before computer-age inference was accessible and which continues to use classical inference because it's hard for an instructor to change textbooks. 

My personal view is that everyone studying statistics should learn computer-age statistical inference. First, most students find it much easier, so they can spend their mental energy to understand the purpose of statistical inference rather than the mechanics of it. Second, it makes it straightforward to move away from the classical settings (e.g. the difference in two proportions, straight-line models) and toward settings that are more important today (e.g. risk ratios, machine learning models). Third, learning to use a computer is itself a valuable objective. In my view, it's only worthwhile to learn classical inference when you are confronted with small-data situations or when your interest in statistics is deep.

But if you *have to* study classical inference, you might as well study it in a concise way. The traditional classical inference curriculum uses a large amount of confusing terminology and splits the subject into several different topics even though they are all very much the same thing. Also, if you are studying statistical inference you are learning how to express uncertainty. Ironically, the textbook description of classical inference involves detailed calculations of great precision. That precision is unjustified. The needless precision is in the textbooks because that's what happens when you translate a real-world problem into deterministic mathematics and because the culture of mathematics education is that of exactitude and proof. Exactitude and proof are valuable things in the proper setting. But in statistical inference, rough answers are good enough. Indeed, the leading professional organization of statisticians, the American Statistical Association, has explicitly called for practitioners of statistical inference to *stop* suggesting that the precision of classical textbook answers is meaningful. 

In order to write a compact guide to statistical inference, I've translated the classical texts into a modern statistical language and computer oriented notation. We'll be using models and effect sizes. All the different settings of textbook classical inference can be expressed in the same way, so we'll work with this one way rather than the six or seven found in textbooks. We'll dispense with unnecessary intermediates such as the "standard error" and dodge the doubtful digressions into misleading exactitude that unnecessarily increases the difficulty of learning and understanding classical inference.
