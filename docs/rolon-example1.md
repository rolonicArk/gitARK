!name example1

'fat-wrap 92

This rolon shows the use of a classifier and descriptor which would be copied to individual files when doing a commit.

Links like [this](https://github.com/rolonicArk/gitARK/new/master/docs) would also be used to create classifiers,
allowing fast access to rolons which reference a particular page. The name of the classifier would be link and
the value would be the URL.

Any **bold** text would also be treated as a classifier. The name of the classifier is the bold text, the value is simply true.

The children and childOf descriptors are a special case, as childOf does not appear in a rolon.md file 
but is generated or deleted when a children descriptor in a rolon.md file is updated. 
The value of a children descriptor is a list of the pathnames of the child rolons relative to the rolons directory.
Similarly the value of a childof descriptor is the pathname of the parent rolon, again relative to the rolons directory.
