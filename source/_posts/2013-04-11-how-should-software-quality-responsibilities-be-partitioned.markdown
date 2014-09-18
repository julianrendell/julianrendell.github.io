---
layout: post
title: "How should Software Quality Responsibilities by Partitioned?"
date: 2013-04-11
comments: true
categories: [career, quality]
---

Recently I've been thinking about different partitions of responsibility for software quality assurance to ensure the delivery of great software. 

I'm basing this on my experiences thus far, which includes working for mid-sized, privately owned companies, through to publicly traded multinationals. I've seen some data points on the continuum from quality groups completely divorced from development teams, through to embedded quality specialists in development teams with shared quality responsibilities.

I've noticed that separate quality groups tend to allow deeper specialization (finer grained divisions of responsibility) for the quality team members. In contrast, quality "specialists" embedded in development teams are often expected to be generalists.

And I believe the three prime factors for an organizations place on this continuum is size, development methodology, and management (organizational) norms.

But what are the typical software quality responsibilities for delivering great software? 

In general there are two broad themes in software quality management:

* Quality Assurance
    * Which has a [dictionary] definition of  _"the maintenance of a desired level of quality in a service or product, esp. by means of attention to every stage of the process of delivery or production."_
* Quality Control
    * Defined in the [dictionary] as: _"a system of maintaining standards in manufactured products by testing a sample of the output against the specification."_
  
Let's list out some specific tasks for delivering software mapped to these two vectors.

For Quality Assurance:

* design
    * Is the product testable? What could be added to ease testing?
    * How will integration points be handled- Mocked? Stubbed? Live dependencies?
    * test infrastructure, from tools and frameworks to managing data for testing
* process
    * at what points in the creation process should these topics be raised
* means of communication. For example, how should requirements be documented?
* project management
    * dealing with specific times for deliveries
* implementation
    * creating manual and/or automated test cases 

For Quality Control:

* determining what is the appropriate statistical sampling of test cases to execute for a given release
    * e.g. "Brute Force" (execute all available tests) vs analyzing past test coverage, code delta, estimating risk, and executing a targeted set of tests
* reporting the measured results against the requirements

Quality Assurance is promissory, Quality control is a (statistical) measurement of the product as it is, right now.

The breadth of skills required for delivering quality assurance and control has lead to several splits between job titles and responsibilities.

Here is my understanding of the common titles and responsibilities used in the industry:

*Manual QA* - (QA & QC) covers the gamut, and is the most general of roles, expected to do with the day-to-day execution of delivering all aspects of quality. Needs good communicators that can juggle multiple tasks. Interruptions the norm.

From here there is a split in common titles. Microsoft has an all encompassing [SDET (Software Engineer in Test)][MS_SDET] role, where as Google uses two roles, a [Software Engineer in Test (SET)][Ggl_SET] and a [Test Engineer][Ggl_TE].

A (Microsoft) *SDET* covers the gamut of test infrastructure (tools and systems) and creating tests for product features. They are responsible for both the QA and QC axes.

In contrast, a Google *SET* creates (central) tools that are used across products. Their work is more along the QA axis.

At the same time Google *TE*s are expected to be (specific) product experts. They need to know what it should do, how, and what integrations are required. They implement the automated testing (beyond developer created unit testing) for integration and acceptance testing.

Looking at these two 'traditional' demarkations of responsibilities and expectations, I wonder if there is a different split, which maybe more viable for smaller organizations. This would split the work between two roles, "QA-TE" and "SET".

A *QA-TE* would have a QC focus, which touches on PM and process. Responsibilities for determining what to run to achieve required quality gates, and reporting.
Test specification, manual test execution, and test implementation and execution (both manual and automated.)

*SET* - QA focus. Responsibilities to test frameworks, infrastructure, product design. But also expected to do a lot of automated test implementation and help with manual QA when needed.

In terms of career progression, the stereotype for a QA-TE would probably be more like a traditional manual QA expert: individual contributor, team lead, QA manager. More focused process and measurement than technical.

For a SET, career progression would be similar to a traditional developer: individual contributor, to senior developer, to architect, or towards team management. That is more of a technical focus than process or reporting. 

You may argue that the split is arbitrary and not necessary. I'd probably agree as to where the dividing line is, but I do think there is one.  The two areas often appeal to people with very different inclinations and personal motivations. This should be taken into account, and respected, when hiring candidates for [SQA] positions.

In writing these thoughts out I've come to an even more important realization. A product management team should set out their quality (assurance and control) expectations as clearly as all other deliverables. Responsibilities (tool creation or purchase, test creation, test execution, etc) should be identified, clearly partitioned out, and scheduled appropriately from the first day of development, and preferably, before.

How does your organization balance needs, roles, expectations, and individuals aptitudes and career progression?

Do you think QA-TE/SET is a reasonable (better?) split for small-to-medium sized teams?
(Assuming you haven't found the perfect all-round QA/QC guru who does it all. And if you have, how did you find this individual?!)

Bonus: here are a couple of extra links that are on my "one-day" reading list-

* [How Google Tests Software](http://my.safaribooksonline.com/book/software-engineering-and-development/software-testing/9780132851572)
* [The difference between QA, QC, and Test Engineering](http://googletesting.blogspot.com/2007/03/difference-between-qa-qc-and-test.html)
* [What are QA, QC, and Test Engineering](http://www.brokenbuild.com/blog/2007/03/06/what-are-qa-qc-and-test-engineering/)

[MS_SDET]: http://www.brokenbuild.com/blog/2006/06/14/software-development-engineer-in-test-the-chilling-truth-behind-the-sdet-acronym/
[Ggl_SET]: http://googletesting.blogspot.ca/2010/03/google-is-hiring-sets.html
[Ggl_TE]: http://googletesting.blogspot.ca/2013/01/test-engineers-google.html
[dictionary]: http://www.apple.com/accessibility/macosx/literacylearning.html
[SQA]: http://en.wikipedia.org/wiki/Software_quality_assurance
