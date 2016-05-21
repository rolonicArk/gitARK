# gitARK
A rolonic ark built on git and integrated with slack.

## Introduction

The basic idea is to use git as a repository for rolons, i.e. an ark, 
and to support interaction via slack.

GitARK would not make use of any git features aside from commits and commit queries. 
This allows the full range of git tools for managing an ark. 
Movement of rolons between arks, for example, can be done with pull requests.
Or an ark can be created in github which users can synchronize with a copy on their own computer.

Commands, or performing journal entries, are entered as slack direct messages.
Messages placed on other slack channels are treated as performing journal entries.

## Directory Structure

There are 3 top-level directories in the repository:
- .git, the standard directory used by git for internal files.
- rolons, which holds all the rolon directories, one directory per rolon. And
- classifiers, which holds the classifier directories, one directory per classifier type.

Directories under the top-level rolons directory holds ledger, classifier and descriptor files.

Ledger files have the .md file extension and are standard github markdown text files.

Classifier and descriptor files within a rolon directory are named for individual classifier
and descriptor types. The file content is the current value of the corrisponding classifier or descriptor.

By breaking rolon classifiers and descriptors into individual files, navigation through time is a
simple matter of filtering the git commit structures with the appropriate rolon descriptor or classifier
path name.

The names of the directories under the rolons directory are immutable and serve as
the identity of the corrisponding rolons.
In contrast, the name of a rolon is a classifier value and is quite mutable.
If no name classifier is given, the rolon name is taken from the name of the rolon directory.

Directories under the top-level classifiers directory are named for their corrisponding classifier.
Files under a given classifier directory are named for the classifier value and contain a list
of the directory names of rolons with that classifier name/value.
Finding the rolons with a particular name then is simply done by reading the name classifier file.

## Implementation

Implementation language would be clojure. 
The initial program would examine all changed rolon.md files, update the secondary files generated from
the rolon files, and then check in all updated files.

Subsequent enhancements would support various queries, including changes over time.
Queries for other than current time would make use of git commit structures.

The [jgit](https://git-scm.com/book/en/v2/Embedding-Git-in-your-Applications-JGit) library and/or 
the [clj-jgit](https://github.com/clj-jgit/clj-jgit) library will be used to make commits and to
perform commit queries.

Looks helpful: 
- [Git Internals](https://git-scm.com/book/en/v2/Git-Internals-Plumbing-and-Porcelain)
- [getting started with jgit](http://www.codeaffine.com/2015/12/15/getting-started-with-jgit/)
- [embedding jgit](http://alblue.bandlem.com/2013/11/embedding-jgit.html)
- [jgit cookbook](https://github.com/centic9/jgit-cookbook)
- [Java implementation of git](http://git.eclipse.org/c/jgit/jgit.git/tree/org.eclipse.jgit/src/org/eclipse/jgit/api)
- [more jgit goodness](http://stackoverflow.com/questions/1685228/how-to-cat-a-file-in-jgit/7427658#7427658)
- [jgit api](http://download.eclipse.org/jgit/site/4.3.1.201605051710-r/apidocs/index.html)

## docs
- [example1 rolon](docs/rolon-example1.md)
- [bang, tick, star & cash](https://github.com/rolonicArk/gitARK/blob/master/docs/Bang-Tick-Star-Cash.txt)
- [rolonics terminology](https://github.com/rolonicArk/gitARK/blob/master/docs/Rolonics%20Terminology.pdf)
