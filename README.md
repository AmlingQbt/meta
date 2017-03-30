# QBT Repository

What is this?  This repository is a QBT repository.  QBT is an open-source dependency management and
repostiory stiching tool.  Think of QBT as being similar to the android development tool "repo", or
git with submodules, but with many additional features and benefits.

# Where is the code?

QBT works by having an external metadata file in a separate metadata repository (usually called
"meta") which refers to specific commits by sha1 in each code repository ("sattelites").  If you
want to inspect the code, or build it, you need to find the metadata repository and clone it, then
run QBT.

Usually, but not always, sattelite repositories are located next to the metadata repository on the
server.

# Why?

For reproducibility, the version specified in the metadata must be authoritative, but branches can
be changed on the server and cannot themselves be versioned, so instead QBT uses a concept called
"pins".  The code in the sattelite is pushed ("pinned") to refs/qbt-pins/X where X is the sha1 of
the commit.  Because the branch itself is content-addressed, it can always be found (and should
never be deleted, just like git objects).

If you insist upon manually inspecting the code, you can see the branches in the sattelite
repositories using ls-remote:

    git ls-remote <clone URL>

The best way to view the code is to use QBT.  For details, see [The Qbt Website](https://qbtbuildtool.com).

# What License is QBT released under?

QBT is released under [The Unlicense](http://unlicense.org/).  The license file is [here](UNLICENSE).

Some code built by QBT, or upon which QBT depends, may be released under other
licenses, so check the sattelite repositories and packages themselves for
license information.



