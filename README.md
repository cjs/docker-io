docker-io
=========

Dockerfile for an image providing access to the [IO Language](http://iolanguage.org/), based on Debian Stable. The build artifacts are still in the /tmp directory. 

This fails 3 tests, but I'm not familiar enough with IO to understand why.

~~~
root@97111b64e45f:/tmp/iobuild/io-2013.12.04/build# io ../libs/iovm/tests/correctness/run.io
..........EE.......................................................E..
......................................................................
......................................................................
...................
======================================================================
FAIL: DirectoryTest testWalk
----------------------------------------------------------------------

  Exception: `self files map(name) != found` --> `list(testFile.x, testFile.y, testFile.z) != list(testFile.y, testFile.x, testFile.z)`
  ---------
  Exception raise                      UnitTest.io 136
  DirectoryTest fail                   UnitTest.io 158
  DirectoryTest assertEquals           DirectoryTest.io 53
  DirectoryTest testWalk               doString 1

======================================================================
FAIL: DirectoryTest testRecursiveFilesOfTypes
----------------------------------------------------------------------

  Exception: `self files map(name) != files map(name)` --> `list(testFile.x, testFile.y, testFile.z) != list(testFile.y, testFile.x, testFile.z)`
  ---------
  Exception raise                      UnitTest.io 136
  DirectoryTest fail                   UnitTest.io 158
  DirectoryTest assertEquals           DirectoryTest.io 73
  DirectoryTest testRecursiveFilesOfTypes doString 1

======================================================================
FAIL: SequenceTest testAsNumber
----------------------------------------------------------------------

  Exception: `Number constants nan asString != "" asNumber asString` --> `"-nan" != "nan"`
  ---------
  Exception raise                      UnitTest.io 136
  SequenceTest fail                    UnitTest.io 158
  SequenceTest assertEquals            SequenceTest.io 35
  SequenceTest testAsNumber            doString 1

----------------------------------------------------------------------
Ran 229 tests in 0.805072s

FAILED (failures 3)                                                run
~~~
