# Repurposing Open Source Tools for Open Science ![OpenScience logo](img/OpenScienceSmall.png)

''Open science'' is receiving an increasing amount of attention recently [[1]].
For instance, the OpenAIRE project supports the European vision for open access and open data [[2]].
Instead of only discussing the theory, or the political and ethical implications of open science, this guide outlines how you can do open science right now!
In this practical guide, we propose the combination of existing tools and systems that originated from the open source movement, the digital legal initiative, or first results of the open science movement itself.

The main idea is to dedicate one existing open source service to each of the various tasks in the scientific research cycle. We define the following scientific tasks, for each of which we propose the use of a corresponding service: 
* document management --> [github](https://github.com)
* proof of originality --> [originstamp](https://originstamp.org)
* automation and objective execution --> [travis](https://travis.org)
* longtime archival --> [zenodo](https://zenodo.org)

In this 7-step guide, we will describe how to collaboratively write a research paper in LaTeX and subsequently obtain your own DOI (Digital Object Identifier) to securely verify your research contirbutions.  
In addition, we provide background information on the individual research tasks and the open source services we view as being the most suitable.
In addition to writing an academic research paper, the procedures we describe here can also be applied when planning a user study, running a computer experiment, or developing a research prototype of a software.

## Step 1: Create a git repository

The first step towards repurposing open source tools to participate in open science research is to create a git repository.
For GitHub navigate to:

 http://github.com/new/

and create the repository
### Background information


* We understand the task of [__document management__](https://en.wikipedia.org/wiki/Document_management_system) as the management of all relevant documents that are required to follow the argumentation of a research project.
 From the document management system, it should be possible to reproduce the research.
This gets more complex the more people are involved, the longer the project period lasts, and the more external information is required.  

* We use the __version control system__ git hosted on GitHub.com to manage our software, our documentation, our notes, and the scientific text. GitHub.com has a large user base and excellent maintenance. However, any other git repository works as well, as long as you can guarantee that the data is adequately backed up and that the service is available to you and your contributors. We recommend installing a mirror for essential git projects to ensure data integrity.

* If you want to start open science secretly, you might want to start with a private repository. GitHub provides free educational licenses [[3]].

* To prove that you are the author of your commits, we recommend that you [sign each commit with your private key.](https://help.github.com/articles/signing-commits-using-gpg/)

* Read [more]( https://help.github.com/) about all features of git to improve your effectiveness when working in a team.

* A fancy way to backup your public GitHub projects is by using the InterPlanetary File System (IPFS). For this, services such as [mango,](https://github.com/axic/mango) [github-ipfs,](https://github.com/airalab/github-ipfs) or [git-remote-ipfs](https://github.com/cryptix/git-remote-ipfs) provide a convenient interface.
* The more repositories you have, the more important it becomes that you choose a meaningful name.
We suggest following the naming convention Year (2 digits) Conference acronym (3-5 letters) Project name

## Step 2: Register the trusted timestamping service OriginStamp

By integrating originstamp you can automatically generate decentralized trusted timestamps, which are stored on Bitcoin's blockchain. These tamper-proof digital timestamps allow you to verifiably and permanently trace (on the blockchain) the time of existence of your individual research contributions, ideas, data, etc.

To automatically integrate OriginStamp into your own GitHub projects and research workflow, follow the instructions at: 
[the developer section of originstamp.org](https://originstamp.org/dev/git).

### Background Information
* __Proof of originality__ means that the consortium of authors can prove that they were in possession of the research data at a certain time, e.g. at the time of writing an article.

* From the legal domain, we use the __trusted timestamping service__ opriginstamp.org to ensure the integrity of our data or software and to prove that data was not massaged or manipulated in retrospect. 

* The history of a git repository provides information on the authors of each change and also on the commit dates.
However, this information can be modified, since Git allows to rewrite the history.
To prevent this from happening you can announce your change to a service that certifies that you authored it.

* Currently, GIT uses the [SHA-1](https://en.wikipedia.org/wiki/SHA-1), which is no longer considered as secure.
However, this will be [fixed](https://github.com/git/git/blob/master/Documentation/technical/hash-function-transition.txt) in future versions of GIT.  

## Step 3: Register the continuous integration service Travis CI

Follow the getting started instruction on [the travis website.](https://docs.travis-ci.com/user/getting-started)
### Background Information

* __Automation and objective execution__ in this case means being able to execute automated document management or computation tasks independent of a researcher's computer setup.
The goal is to prevent reproducibility issues that are caused by the unique setup of a researcher's computer system.
While individually configured and installed computer systems are convenient, the results produced by these systems are hard to replicate.

* We use Travis CI to test our software run scientific experiments to compile our scientific texts.

* A problem with this approach is that the centralized execution service Travis could be corrupted or stop functioning. As such, we advocate distributing the execution. For example, the Ethereum blockchain can execute code in the form of smart contracts.

## Step 3: Write your paper

Write your paper as you would usually do.
Small commits, descriptive and GPG-signed commit messages help track your contributions to the paper, in the case of a dispute.

You can use the [VMEXT2 paper repo](https://github.com/ag-gipp/18CicmVmext2) as a template to get the configuration setting how to make Travis compile your LaTeX paper for you. 
### Background information

With the _blame_ feature of git, you can see who edited which lines of the file most recently.
Using the same method you can also find out who did the second-to-last edit to a line and so on.
Therefore, we recommend beginning each sentence on a new line.

## Step 4: Make your preprint public

If you want to get a DOI for your paper and enable long-term archival of your paper, then your paper must be public.
On GitHub, you can change your repository from private to public in the repository settings.
You have to confirm this action by typing in the repository name.

## Step 5: Register the publication service

Register the publication service Zenodo, by following the steps on 
 https://zenodo.org/account/settings/github/

## Step 6: Release a version and get a DOI

After having integrated the Zenodo service, create a new release on your GitHub repository and a DOI will be automatically assigned to your preprint.
Your document will be archived by Zenodo, which is a long-term research data archival service and a [project funded by the European Union and cern](http://about.zenodo.org/).

### Background information
* There is a high fluctuation in research.
Even though the aforementioned techniques for document management are the state of the art right now this might change in the future and services might disappear.
The task of __longtime archival__ deals with making the research results available to future generations of scientists.

* The longtime archival service __zenoodo__ was particularly designed for this purpose.
 At the time of writing, we are not aware of any downsides with this service.  

## Step 7: (Optional) Link a TeX web editor
Since some of your colleagues might not be as familiar with LaTeX and GitHub as others, it might be easier for some to use an online editor for LaTeX, such as OverLeaf. 
Beginning with [version 2](https://www.overleaf.com/blog/641-try-out-overleaf-v2#.WxpJGRyxWqM), Overleaf enables working together on GitHub hosted projects.
Pull requests automatically syncronize between GitHub and Overleaf.

## Feedback and comments

Feedback and comments on this post are possible via [github issues](https://github.com/ag-gipp/OpenScienceTemplate/issues), or by contacting the [author.](https://schubotz.org)


[1]: https://trends.google.com/trends/explore?date=2008-06-05%202018-06-05&q=%2Fm%2F025ttdm
[2]: https://www.openaire.eu/openaire2020-project-factsheet
[3]: https://help.github.com/articles/about-github-education-for-educators-and-researchers/
