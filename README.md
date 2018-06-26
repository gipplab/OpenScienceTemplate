# How to "abuse" OpenSource tools for OpenScience ![OpenScience logo](img/OpenScienceSmall.png)

Open science gets increasing attention recently [[1]].
For instance, the OpenAIRE project supports the European vision for open access and open data [[2]].
Rather than discussing the theory, political and ethical implications, this guide outlines, how you can do open science right now.
To do this, we combine systems originating from the open source movement, the digital legal initiative, and first results of the open science movement itself.
The main idea is to have a service dedicated for each task
* document management --> [github](https://github.com)
* proof of originality --> [originstamp](https://originstamp.org)
* automation and objective execution --> [travis](https://travis.org)
* longtime archival --> [zenodo](https://zenodo.org)

In this 7 step guide, we describe how to collaboratively write a paper in LaTeX and obtain a DOI in the end.
In addition, we provide background information on the tasks and services.
Besides writing a paper, the same principles can be applied to plan a user study, run a computer experiment or develop a research prototype of a software.

## Step 1: Create a git repository

The first step is to create a git repository.
For GitHub navigate to

 http://github.com/new/

and create the repository
### Background information


* We understand the task of [__document management__](https://en.wikipedia.org/wiki/Document_management_system) as the management of all relevant documents that are required to follow the argumentation of a research project.
 From the document management system, it should be possible to reproduce the research.
 The gets more complex the more people are involved, the longer the project period lasts, and the more external information is relevant.  

* We use the __version control system__ git hosted on GitHub.com to manage our software, documentation, notes and the scientific text. GitHub.com has a large user base and excellent maintenance. However, any other git repository works as well as long as you can guarantee that the data is adequately backed up and that the service is available to you and your contributors. We recommend installing a mirror for essential git projects to ensure data integrity.

* If you want to start open science secretly, you might want to start with a private repository. Note, that GitHub provides free educational licenses [[3]].

* To prove that you are the author of your commits, we recommend that you [sign each commit with your private key.](https://help.github.com/articles/signing-commits-using-gpg/)

* Read [more]( https://help.github.com/) about all the features of git to improve your effectiveness when working in a team.

* A fancy way to backup your public GitHub projects is using the interplanetary filesystem IPFS. Here services such as [mango,](https://github.com/axic/mango) [github-ipfs,](https://github.com/airalab/github-ipfs) or [git-remote-ipfs](https://github.com/cryptix/git-remote-ipfs) provide a convenient interface.
* If you have more and more repositories chose a meaningful name.
I suggest following the naming convention Year (2 digits) Conference acronym (3-5 letters) Project name

## Step 2: Register the trusted timestamping service

Follow the instructions on [the developer section on originstamp.org](https://originstamp.org/dev/git).

### Background Information
* __Proof of originality__ means that the consortium of authors can prove that they had the research data at the time of writing the article.

* From the legal domain, we use the __trusted timestamping service__ opriginstamp.org to ensure the integrity of our data, software and to prove it's originality.

* The history of a git repository provides information on the authors of each change and also on the commit dates.
However, this information can be modified since Git allows to rewrite the history.
To prevent this from happening you can announce your change to a service that certifies that you authored it.

* Currently, GIT uses the [SHA-1](https://en.wikipedia.org/wiki/SHA-1) to which is no longer considered as secure.
However, this will be [fixed](https://github.com/git/git/blob/master/Documentation/technical/hash-function-transition.txt) in future versions of GIT.  

## Step 3: Register the continuous integration service

Follow the getting started instruction on [the travis website.](https://docs.travis-ci.com/user/getting-started)
### Background Information

* __Automation and objective execution__ means to us being able to execute automated document management or computation tasks independent of a researchers computer setup.
The goal is to avoid side effects that are caused by the individual setup of a research computer system.
While individually configured and installed computer systems are convenient, the results produced by those systems are hard to reproduce. 

* We use Travis to test our software run scientific experiments to compile our scientific texts.

* A problem with this approach is that centralized execution service Travis could be corrupted or stop functioning. As such, we advocate distributing the execution. For example, the Ethereum blockchain can execute code in the form of smart-contracts.

## Step 3: Write your paper

Write your paper as you would usually do.
Small commits, descriptive and GPG-signed commit messages help to understand your contribution to the paper, in the case of a dispute.

You can use the [VMEXT2 paper repo](https://github.com/ag-gipp/18CicmVmext2) as a template to get the configuration setting how to make Travis compile your LaTeX paper for you. 
### Background information

With the _blame_ feature of git, you can see who edited which lines of the file at last.
Using the same method you can also find out who did the second last edit to this line and so on.
Therefore, I recommend starting each sentence on a new line.

## Step 4: Make your preprint public

If you want to get a DOI for and have long time archival for your paper, your paper needs to be public.
On GitHub, you can change from private to public by in the repository settings.
You have to confirm this action by typing in the repository name.

## Step 5: Register the publication service

Register the publication service Zenodo, by following the advise on 
 https://zenodo.org/account/settings/github/

## Step 6: Release a version and get a DOI

After having integrated the Zenodo service create a new release on your GitHub repository and a DOI is assigned to your preprint.
Your document will be long time archived by a [project funded by the European Union and cern](http://about.zenodo.org/).

### Background information
* There is a high fluctuation in research.
Even though the aforementioned techniques for document management are the state of the art right now this might change in the future and services might diaper.
The task of __longtime archival__ deals about making the research results available to future generations of scientists.

* The longtime archival service __zenoodo__ was particularly designed for this purpose.
 At the time of writing we are not aware of any downsides with this service.  

## Step 7: (Optional) Link a TeX web editor
Since some of your colleagues might not be familiar with LaTeX and GitHub and others, it might be easier for them use an online editor for LaTeX.
Starting with [version 2](https://www.overleaf.com/blog/641-try-out-overleaf-v2#.WxpJGRyxWqM) overleaf provides the ability to work together on GitHub hosted projects.
Pull requests syncronize between GitHub and overleaf.




[1]: https://trends.google.com/trends/explore?date=2008-06-05%202018-06-05&q=%2Fm%2F025ttdm
[2]: https://www.openaire.eu/openaire2020-project-factsheet
[3]: https://help.github.com/articles/about-github-education-for-educators-and-researchers/
