
Build a snapshot
================

Sonatype Nexus is used for the package release, if you want to build
a snapshot first have a read at their guide:
[Sonatype OSS Maven Repository Usage Guide](http://docs.sonatype.org/display/Repository/Sonatype+OSS+Maven+Repository+Usage+Guide).

Building a snapshot is as easy as running a single command when you have
proper configuration.

    mvn clean deploy


Perform a release
=================

In order to release the package and get it synchronized with
central Maven repo follow the Sonatype guide:
[Sonatype OSS Maven Repository Usage Guide](http://docs.sonatype.org/display/Repository/Sonatype+OSS+Maven+Repository+Usage+Guide).

If you have the proper configuration for Sonatype and it is not your first
release then the release process can be summarized with the following steps:

    # make sure to clear any pending commit/push
    # eventually you want to build a snapshot and test it
    mvn clean deploy
    # then proceed with the release steps
    mvn release:clean
    mvn release:prepare
    mvn release:perform

At this point follow point 8 of the Sonatype guide in order to confirm
the release and get it synchronized with central Maven repository.
