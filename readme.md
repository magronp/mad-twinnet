# MaD TwinNet GitHub Repository

#####Welcome to the repository of the MaD TwinNet. 

If you know what you are doing, then jump ahead, get the **_pre-trained
weights_** from 
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.1164592.svg)](https://doi.org/10.5281/zenodo.1164592)
and start using the MaD TwinNet.  

If you just need the **_results_**, you can get them from
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.1164592.svg)](https://doi.org/10.5281/zenodo.1164592)
.

There is also an on-line demo of the MaD TwinNet at the [website of
the MaD TwinNet](http://arg.cs.tut.fi/demo/mad-twinnet).

If you need some help on using MaD TwinNet, please read the following
instructions. 

##Important!
Before you read anything else here, please make sure that you 
checked the licencing of this code. 

Also, if you use any of the things existing in this repository
or the associated binary files from Zenodo, please consider 
citing our paper available
[from here](https://arxiv.org/abs/1802.00300). 

##Table of contents

- [How do I use it with no manual](mad-twinnet#How do I use it with no manual)
- [What is the MaD TwinNet](mad-twinnet#What is the MaD TwinNet)
- [How do I use the MaD TwinNet](mad-twinnet#How do I use the MaD TwinNet)
- [Acknowledgements](mad-twinnet#Acknowledgements)

##How do I use it with no manual
You can:

- re-train the MaD TwinNet, by running the script
[training.py](scripts/training.py),
- re-test it, by running the script 
[testing.py](scripts/testing.py), or 
- use it, by running the script 
[use_me.py](scripts/use_me.py).

The settings for all the above processes are controller by 
the [settings.py](helpers/settings.py) file. For the 
[use_me.py](scripts/use_me.py) script, you can find directions
in it or go to the How do I use it (RTFM version)? section.

If you want to re-test or use the MaD TwinNet, you will need 
the pre-trained weights of the MaD TwinNet. You can get the 
pre-trained weights from 
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.1164592.svg)](https://doi.org/10.5281/zenodo.1164592)
.  

##What is the MaD TwinNet
MaD TwinNet stands for the "Masker-Denoiser with Twin Networks
architecture/method" for monaural music sound source separation. 
An illustration of the MaD TwinNet can be seen in the following 
figure: 

[Illustration of MaD TwinNet](images/method.png "Illustration of MaD TwinNet")

You can read more at [our paper on arXiv](https://arxiv.org/abs/1802.00300). 

For the implementation of our method, we used the
[PyTorch framework](http://pytorch.org). 

##How do I use the MaD TwinNet
###Setting up the environment
Before starting using the code of this repository, you will have to
install some packages for your python environment. 

Must be noted that, our code is based on Python 3.6 version. So, for
a better experience, we recommend using Python 3.6. 

To install the dependencies, you can either use the `pip` package
manager or the `anaconda`/`conda`. 

If you want to **use the `pip`**, then you have to
- clone our repository (e.g. `git clone `),
- navigate with your terminal inside the directory of the cloned 
  repo (e.g. `cd mad-twinnet`), and then
- issue at your terminal the command 
`pip install -r requirements.txt` 

If you want to **use the `anaconda`/`conda`**, then you have to
- clone our repository (e.g. `git clone `),
- navigate with your terminal inside the directory of the cloned 
  repo (e.g. `cd mad-twinnet`), and then
- issue at your terminal the command 
`conda install --yes --file conda_requirements.txt`

###Dataset set-up
To do so, you will have to obtain your dataset. Your dataset should
be in the `dataset` directory. By default, the training set should
be under a directory named `Dev` and the testing set under a directory
named `Test`. This means that the directories for the training and
testing sets must be `dataset/Dev` and `dataset/Test`, respectively.

Also, by default, you will need numbered file names (e.g. `001.wav`)
and each file name should have an identifier whether the file is about
the mixture, the voice, the bass, and other. **Please check the 
[Demixing Secret Dataset (DSD)]()
for the exact file naming conventions.** 

If you want to use the DSD, then you most probably will want to 
extract it in the `dataset` directory and you will end up with 
the above mentioned directory structure and proper file names.  

If you want to use a different dataset, then you have two options: 
- either you format your file names and directory structure to match
the one from the DSD, or
- you modify the file reading function to suit your needs.

For the second option, you will have to at least modify the 
`_get_files_lists` function, in the `helpers` directory/package.

###Re-training MaD TwinNet
You can re-train the MaD TwinNet. For example, you might want to 
try and find better hyper-parameters, try how the MaD TwinNet will
go on a different training dataset, or any other wonderful idea :)

If you have set up the dataset correctly, then you just want to 
run the `scripts/training.py` file. You have quite enough options
to run this file. For example, you can run it through your favorite
IDE, or through terminal. 

If you run it through terminal, **please do not forget to set up
the PYTHONPATH environmental variable correctly**. E.g., if you are
in the project root directory, you can issue the command 
`export PYTHONPATH=$PYTHONPATH:../` and then you can issue the 
command `python scripts/training.py`. 

####Altering the hyper-parameters
All the hyper-parameters are in the `helpers/settings.py` file. 

You can alter any hyper-parameter you want, but make sure that 
the values that you will use are correct and can actually be used. 

###Re-testing MaD TwinNet
You can re-test the MaD TwinNet. To do so, you need again the proper
set-up of the dataset and the weights of the MaD TwinNet. You can
get the weights from [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.1164592.svg)](https://doi.org/10.5281/zenodo.1164592)
.

When the above are OK, then you simply run the `scripts/testing.py`
file. 

If you run the testing file through terminal, **please do not forget to set up
the PYTHONPATH environmental variable correctly**. E.g., if you are
in the project root directory, you can issue the command 
`export PYTHONPATH=$PYTHONPATH:../` and then you can issue the 
command `python scripts/testing.py`.

###Use MaD TwinNet

