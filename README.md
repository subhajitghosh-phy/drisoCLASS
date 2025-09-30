drisoCLASS: CLASS for Dark Radiation Isocurvature (Based on CLASS)
==================================================================

Authors:

CLASS: Julien Lesgourgues and Thomas Tram

drisoCLASS: Subhajit Ghosh, Soubhik Kumar, Peizhi Du, and Jae Hyeok Chang.

Authors of the original version: Subhajit Ghosh, Soubhik Kumar, and Yuhsin Tsai.

CLASS code for dark radiation (DR) isocurvature for free-streaming DR (with options for decoupling & recoupling interactions) and coupled (fluid-like) DR.

Using drisoCLASS code
---------------------
You can use drisoCLASS freely provided you cite the following works:

1. CLASS papers (see below)
2. [Cosmological Constraints on Secluded Dark Radiation](): The code is used and made public in this publication.
3. [Free-streaming and coupled dark radiation isocurvature perturbations: constraints and application to the Hubble tension](https://arxiv.org/abs/2107.09076): The initial conditions for free-streming DR (FDR) and coupled DR (CDR) were first derived in this paper. An older version of this code was used for this publication.
4. [Confronting interacting dark radiation scenarios with cosmological data](https://arxiv.org/abs/2212.13264): Boltzmann Equations for decoupling and recoupling DR are implemeted following this reference. 

<ins>Operational details:</ins>

1. The massless DR is implemented using the 'idr' module in base CLASS.
2. The intial conditions for FDR or CDR are chosen automatically depending on 'idr_nature' input.
3. Both decoupling and recoupling DR interaction take the input 'log10_Geff'. For decoupling, it's definition is the same as in Ref. 2 above. For recoupling, the coupling in Ref. 2 is related as 'log10_lambda_eff = (log10_Geff - 25.56)/2'.   

For detailed instructions on how to use the code, please refer to the notebook driso.ipynb.

CLASS: Cosmic Linear Anisotropy Solving System  {#mainpage}
==============================================

Authors: Julien Lesgourgues and Thomas Tram

with several major inputs from other people, especially Benjamin
Audren, Simon Prunet, Jesus Torrado, Miguel Zumalacarregui, Francesco
Montanari, etc.

For download and information, see http://class-code.net


Compiling CLASS and getting started
-----------------------------------

(the information below can also be found on the webpage, just below
the download button)

Download the code from the webpage and unpack the archive (tar -zxvf
class_vx.y.z.tar.gz), or clone it from
https://github.com/lesgourg/class_public. Go to the class directory
(cd class/ or class_public/ or class_vx.y.z/) and compile (make clean;
make class). You can usually speed up compilation with the option -j:
make -j class. If the first compilation attempt fails, you may need to
open the Makefile and adapt the name of the compiler (default: gcc),
of the optimization flag (default: -O4 -ffast-math) and of the OpenMP
flag (default: -fopenmp; this flag is facultative, you are free to
compile without OpenMP if you don't want parallel execution; note that
you need the version 4.2 or higher of gcc to be able to compile with
-fopenmp). Many more details on the CLASS compilation are given on the
wiki page

https://github.com/lesgourg/class_public/wiki/Installation

(in particular, for compiling on Mac >= 10.9 despite of the clang
incompatibility with OpenMP).

To check that the code runs, type:

    ./class explanatory.ini

The explanatory.ini file is THE reference input file, containing and
explaining the use of all possible input parameters. We recommend to
read it, to keep it unchanged (for future reference), and to create
for your own purposes some shorter input files, containing only the
input lines which are useful for you. Input files must have a *.ini
extension.

If you want to play with the precision/speed of the code, you can use
one of the provided precision files (e.g. cl_permille.pre) or modify
one of them, and run with two input files, for instance:

    ./class test.ini cl_permille.pre

The files *.pre are suppposed to specify the precision parameters for
which you don't want to keep default values. If you find it more
convenient, you can pass these precision parameter values in your *.ini
file instead of an additional *.pre file.

The automatically-generated documentation is located in

    doc/manual/html/index.html
    doc/manual/CLASS_manual.pdf

On top of that, if you wish to modify the code, you will find lots of
comments directly in the files.

Python
------

To use CLASS from python, or ipython notebooks, or from the Monte
Python parameter extraction code, you need to compile not only the
code, but also its python wrapper. This can be done by typing just
'make' instead of 'make class' (or for speeding up: 'make -j'). More
details on the wrapper and its compilation are found on the wiki page

https://github.com/lesgourg/class_public/wiki

Plotting utility
----------------

Since version 2.3, the package includes an improved plotting script
called CPU.py (Class Plotting Utility), written by Benjamin Audren and
Jesus Torrado. It can plot the Cl's, the P(k) or any other CLASS
output, for one or several models, as well as their ratio or percentage
difference. The syntax and list of available options is obtained by
typing 'pyhton CPU.py -h'. There is a similar script for MATLAB,
written by Thomas Tram. To use it, once in MATLAB, type 'help
plot_CLASS_output.m'

Developing the code
--------------------

If you want to develop the code, we suggest that you download it from
the github webpage

https://github.com/lesgourg/class_public

rather than from class-code.net. Then you will enjoy all the feature
of git repositories. You can even develop your own branch and get it
merged to the public distribution. For related instructions, check

https://github.com/lesgourg/class_public/wiki/Public-Contributing

Using the code
--------------

You can use CLASS freely, provided that in your publications, you cite
at least the paper `CLASS II: Approximation schemes <http://arxiv.org/abs/1104.2933>`. Feel free to cite more CLASS papers!

Support
-------

To get support, please open a new issue on the

https://github.com/lesgourg/class_public

webpage!
