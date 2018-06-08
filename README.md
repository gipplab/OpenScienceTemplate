# How to "abuse" OpenSource tools for OpenScience

Open science gets increasing attention recently [[1]].
For instance, the OpenAIRE project supports the European vision for open access and open data [[2]].
Rather than discussing the theory, political and ethical implications, this guide outlines, how you can do open science right now.
To do this we combine systems originating from the open source movement, the digital legal initiative, and first results of the open science movement itself.
The main idea is to have a service dedicated for each task
* proof of originality --> [originstamp](https://originstamp.org)
* document management --> [github](https://github.com)
* longtime archival --> [zenodo](https://zenodo.org)
* automation and objective execution --> [travis](https://travis.org)

In this 7 step guide, we describe how to collaboratively write a paper in LaTeX and obtain a DOI for that.
However, the same principle can be applied to plan a user study, run a computer experiment or develop a research prototype of a software.

## Step 1: Create a git repository

The first step is to create a git repository.
For GitHub navigate to

 http://github.com/new/
 
and chose a meaningful name.
I suggest following the naming convention Year (2 digits) Conference acronym (3-5 letters) Project name

### Background information

* We use the version control system git hosted on GitHub.com to manage our software, documentation, notes and the scientific text. GitHub.com has a large user base and is well maintained. However, any other git repository works as well as long as you can guarantee that the data is properly backed up and that the service is available to you and your contributors. We recommend to install a mirror for important git projects to ensure data integrity.

* If you want to start open science secretly, you might want to start with a private repository. Note, that GitHub provides free educational licenses [[3]].

* To prove that you are the author of your commits, we recommend that you sign each commit with your private key.

* Read more about all the features of git to improve your effectiveness when working in a team.

* A fancy way to backup your public github projects is using the interplenatary filesystem IPFS using services such as [mango,](https://github.com/axic/mango) [github-ipfs
,](https://github.com/airalab/github-ipfs) or [git-remote-ipfs
](https://github.com/cryptix/git-remote-ipfs).

## Step 2: Register the trusted timestamping service

Follow the instructions on [the developer section on originstamp.org](https://originstamp.org/dev/git).

### Background Information 
* From the legal domain, we use the trusted timestamping service opriginstamp.org to ensure the integrity of our data, software and to prove it's originality.

* The history of a git repository provides information on the authors of each individual change and also on the dates when each change was done.
However, this information can be modified since git allows to rewrite the history.
To prevent this from happening you can announce your change to a service that certifies that you authored it. 

## Step 3: Register the continuous integration service

Follow the getting started instruction on [the travis website.](https://docs.travis-ci.com/user/getting-started)
### Background Information


* We use travis to test our software run scientific experiments to compile our scientific texts.

* A problem with this approach is that centralised execution service travis could be corrupted or stop functioning. As such the execution parts should be distributed. For example the etherium blockchain has the ability to execute code in the form of smart cont form of smart contracts.

## Step 3: Write your paper

Write your paper as you would usually do.
Small commits, descriptive and gpg-signed commit messages help to understand your contribution to the paper, in the case of a dispute.

You can use the [VMEXT2 paper repo](https://github.com/ag-gipp/18CicmVmext2) as a template to get the configuration setting how to make travis compile the your LaTeX paper for you. 
### Background information

With the _blame_ feature of git you can see who edited which lines of the file at last.
Using the same method you can also find out who did the second last edit to this line and so on.
Therefore, I recommend to start each sentence on a new line.

## Step 4: Make your preprint public

If you want to get a DOI for and have long time archival for your paper, your paper needs to be public.
On GitHub you can change from private to public by in the repository settings.
You have to confirm this action by typing in the repository name.

## Step 5: Register the publication service

Register the publication service zenodo, by following the advise on 
 https://zenodo.org/account/settings/github/

## Step 6: Release a version and get a DOI

After having integrated the zenodo service just create a new release on your github repository and a DOI is assigned to your preprint.
This will be long time archived by a [project funded by the european union and cern](http://about.zenodo.org/).


## Step 7: (Optional) Link a TeX web editor
Since some of your colleagues might not be familar with LaTeX and GitHub etc. it might be easier for them use a online editor for LaTeX.
Starting with version 2 overleaf provides the ability to work togehter on github hosted projects.
The synchronization between github and overleaf is managed via pull-request.  




[1]: https://trends.google.com/trends/explore?date=2008-06-05%202018-06-05&q=%2Fm%2F025ttdm
[2]: https://www.openaire.eu/openaire2020-project-factsheet
[3]: https://help.github.com/articles/about-github-education-for-educators-and-researchers/
