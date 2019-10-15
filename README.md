# assignment 3
17011626 seungpil-Kwon
the assignment is to train a classifier that we help to detect PE files as bad (malicious) or good files.
When learning whether the file is malcious, I used [this]:  http://wildfire.paloaltonetworks.com/publicapi/test/pe file.
When learning whether the file is legitimate, I used calc.exe

## Learning 

```
$ python learning.py 
Researching important feature based on 54 total features

/usr/local/lib/python2.7/dist-packages/sklearn/ensemble/forest.py:246: FutureWarning: The default value of n_estimators will change from 10 in version 0.20 to 100 in 0.22.
  "10 in version 0.20 to 100 in 0.22.", FutureWarning)
15 features identified as important:
1. feature Machine (0.181214)
2. feature DllCharacteristics (0.095521)
3. feature Characteristics (0.091682)
4. feature ImageBase (0.091101)
5. feature SectionsMaxEntropy (0.059102)
6. feature Subsystem (0.052672)
7. feature VersionInformationSize (0.048965)
8. feature ResourcesMaxEntropy (0.045192)
9. feature ResourcesMinEntropy (0.037687)
10. feature MajorOperatingSystemVersion (0.037542)
11. feature MajorSubsystemVersion (0.036819)
12. feature SizeOfOptionalHeader (0.024746)
13. feature SectionsMeanEntropy (0.021679)
14. feature SectionsNb (0.021442)
15. feature MinorLinkerVersion (0.019809)

Now testing algorithms
GNB : 70.264397 %
DecisionTree : 99.051068 %
RandomForest : 99.445853 %
AdaBoost : 98.634553 %
GradientBoosting : 98.855487 %

Winner algorithm is RandomForest with a 99.445853 % success
Saving algorithm and feature list in classifier directory...
Saved
False positive rate : 0.386618 %
False negative rate : 0.949945 %
```

## Execute

```
seungpil@ubuntu:~/Desktop/assignment3$ python checkpe.py samplemalware.exe 
The file samplemalware.exe is malicious
```

```
seungpil@ubuntu:~/Desktop/assignment3$ python checkpe.py calc.exe
The file calc.exe is legitimate
```
