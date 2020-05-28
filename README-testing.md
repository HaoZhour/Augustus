

The following modes are used only when creating a new data set (bedtools required)
2) PREDICT mode to run original cmpAugustus prediction
3) TEST mode to run a test concerning the crrectness in the use of minimal FASTAs
4) PREPARE to build new data sets


[![Build Status](https://travis-ci.org/Gaius-Augustus/Augustus.svg?branch=master)](https://travis-ci.org/Gaius-Augustus/Augustus)

# Gene Prediction with AUGUSTUS

[INTRODUCTION](#introduction)  
[BASIC](#basicuse)  
[ADVANCED](#advanceduse)  
[LICENSES](#licenses)  

# INTRODUCTION

The present version of Augustus allows to run prediction over a minimal data set to assess how changes in the code may have affected accuracy.

# BASIC

## Dependencies
Please make sure boost-serialization-dev is installed. If it is not the case, try and run:

```
sudo apt-get update
sudo apt-get install libboost-serialization-dev
```
In order to have accuracy returned, eval should be installed on your machine. Make sure it is the case and set eval_dir within script/executeTestCGP.py to eval path as follows:

```
eval_dir = /my_path_to_EVAL/
```

Running the python3 script executeTestCGP.py has the following software dependency:
  - Python3

## First use
Set TESTING = false in [common.mk](common.mk) if this feature is not required or the required libraries are not available. By default TESTING = true.

Run the following commands from within ./scripts/ :
```
YOURPYTHON executeTestCGP.py --chunk=1 --run
```
this command runs prediction using minimal FASTAs (expected running time 1h c.ca). Results are stored in example/cgp12way/out1run.
```
YOURPYTHON executeTestCGP.py --chunk=1 --eval 
```
this command computes accuracy for some prediction obtained using minimal FASTAs. Results are stored in example/cgp12way/out1result. Chunk parameter can be set to be any chunk, provided data are available for it (e.g. MAF, SQlite db).

# ADVANCED
Todo add description of advanced use here

# LICENSES

All source code, i.e.
  - the AUGUSTUS source code (src/*.cc, include/*.hh)
  - the scripts (scripts/*.pl)
  - the auxiliary programs (auxprogs/)
  - the tree-parser (src/scanner,src/parser)
  
is under the [Artistic License](src/LICENSE.TXT).