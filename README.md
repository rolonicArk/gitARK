# gitARK
A rolonic ark built on git.

The basic idea is to use git as a repository for rolons, i.e. an ark.

Files in the repository are rolons in the ark, while commits are the journal entries.

GitARK would not make use of any git features aside from commits and commit queries. 
This allows the full range of git tools for managing an ark. 
Movement of rolons between arks, for example, can be done with pull requests.
Or an ark can be created in github which users can synchronize with a copy on their own computer.

Rolons would be created/edited by hand as .md files, each rolon having its own directory in the repository.
Generated files in the same directory hold a single classifier or descriptor per file.

Additionally, there will be a separate directory for each classifier used in the ark. 
Each file in a classifier directory is for a classifier value and contains a list of all the rolons
which currently have that classifier/value assignment.

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

## docs
- [file content](docs/file-content.md)
