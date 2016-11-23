evosoro: soft robot simulator
=======================================

<div class="row">
<a href=https://youtu.be/EXuR_soDnFo>
<img src="https://github.com/skriegman/img/blob/master/nick.png" height="135" width="135">
</a>

<a href=https://www.youtube.com/watch?v=HgWQ-gPIvt4>
<img src="https://github.com/skriegman/img/blob/master/electro.png" height="135" width="135">
</a>

<a href=https://youtu.be/4ZqdvYrZ3ro>
<img src="https://github.com/skriegman/img/blob/master/swimming.png" height="135" width="135">
</a>

<a href=https://youtu.be/Cw2SwPNwcfM>
<img src="https://github.com/skriegman/img/blob/master/plant1.png" height="135" width="135">
</a>

<a href=https://www.youtube.com/watch?v=XqIUJcuOgmwl>
<img src="https://github.com/skriegman/img/blob/master/teeth1.png" height="135" width="135">
</a>

<a href=https://www.youtube.com/watch?v=r_SL8VUt-wA>
<img src="https://github.com/skriegman/img/blob/master/cage.png" height="135" width="135">
</a>

</div>

Evosoro is a Python soft robot simulation library based on the Voxelyze physics engine. It provides a high-level interface for the dynamic simulation and automated design of soft multimaterial robots.

Evosoro was designed and developed by the [Morphology, Evolution & Cognition Laboratory](http://www.meclab.org), University of Vermont. 
The library is built on top of the open source [VoxCAD](https://github.com/jonhiller/VoxCAD
) and the underlying voxel physics engine ([Voxelyze](https://github.com/jonhiller/Voxelyze)) which were both developed by the [Creative Machines Lab](http://www.creativemachineslab.com/), Columbia University.


1. Citing
------

If using this code for academic purposes please cite the following two papers,

Physical simulation:

>Hiller, J., & Lipson, H. (2014). 
>*Dynamic simulation of soft multimaterial 3d-printed objects.*
>Soft Robotics, 1(1), 88-101.

Encoding and optimization:

>Cheney, N., MacCurdy, R., Clune, J., & Lipson, H. (2013). 
>*Unshackling evolution: evolving soft robots with multiple materials and a powerful generative encoding.* 
>In Proceedings of the 15th annual conference on Genetic and evolutionary computation (pp. 167-174). ACM.




2. Dependencies
------------

- Python 2.7

#### Mandatory

- [numpy](http://www.numpy.org/)

- [scipy](http://www.scipy.org/)

- [networkx](http://networkx.github.io/)

#### Recommended

- [pandas](http://pandas.pydata.org/)

- [matplotlib](http://matplotlib.org/)

- [seaborn](http://seaborn.pydata.org/)



3. Installation
------------

<!--To install the released version, just do-->
    
<!--    pip install evosoro-->

<!--You may instead want to use the development version from Github, by running-->

<!--    pip install git+git://github.com/skriegman/evosoro.git#egg=evosoro-->

------------------------------------------------------------------
**If you do not meet the requirements start here.**

It is recommended that you install [Anaconda](https://docs.continuum.io/anaconda/install#) as your Python (2.7) distribution. Anaconda is a free package manager and Python distribution that includes all of the dependencies required for evosoro. However if you instead choose to manually install Python 2.7,

    sudo apt-get install python-dev python-pip
    sudo pip install scipy numpy networkx decorator  

If you experience an error installing scipy it might be due to the incompatibility of different fortran compilers (see [scipy installation](https://docs.scipy.org/doc/numpy-1.10.1/user/install.html)). In most cases, you must build numpy/scipy with the same fortran compiler used to build blas/lapack/atlas. Try the following:

	sudo apt-get install libatlas-base-dev gfortran
	sudo pip install scipy numpy networkx decorator

------------------------------------------------------------------

**If you already have Anaconda (2.7) or otherwise fulfil the mandatory dependencies start here.**

Install Qt and QMake if you have not already done so, specifically these packages: "libqt4-dev", "qt4-qmake", "libqwt-dev", "freeglut3-dev" and "zlib1g-dev".

    sudo apt-get install libqt4-dev qt4-qmake libqwt-dev freeglut3-dev zlib1g-dev


Install git if you have not already done so.

    sudo apt-get install git

Navigate to your working directory (e.g. your home).

    cd ~

Clone the repo.

    git clone https://github.com/skriegman/evosoro.git

There are different well documented examples (evosoro/examples) and custom versions of VoxCad/Voxelyze (evosoro/_voxcad folders) included in this repository. Let's try running an example in which soft robots are optimized to locomote in a terrestrial environment, using an evolutionary algorithm and a basic version of the physics engine (the procedure is the same for all the examples). 
Navigate to the _voxcad directory and compile as follows:

    cd evosoro/evosoro/_voxcad/
    make

Install the voxelyze library.

    cd Voxelyze
    make
    make installusr
    cd ../voxelyzeMain/
    make

Navigate back out to the examples folder and run basic.py
    
    cd ../../examples
    python basic.py

You should start seeing some output being produced in your console, and a new directory being created (evosoro/evosoro/basic_data), which contains the results of the simulation.


4. Examples
--------

After running basic.py for some time, you can start having a look at some of the evolved morphologies and behaviors by opening up some of the generated .vxa files within the VoxCAD GUI. A .vxa file is just an XML file representing a robot that can be simulated by VoxCad/Voxelyze. Different custom versions of the physics engine can play slightly different .vxa files.
Navigate to evosoro/evosoro/_voxcad/release:
    
    cd ../_voxcad/release
    
Open VoxCad:

    ./VoxCad

Then select the desired .vxa file from 

    "File -> Import -> Simulation"

The .vxa files for the best performing individuals will be saved in 

    evosoro/evosoro/basic_data/bestSoFar/fitOnly.

Once the design is loaded, you can start the physics simulation by clicking the <img src="https://github.com/skriegman/evosoro/blob/master/evosoro/_voxcad/VoxCad/Icons/Sandbox.png" height="25" width="25"> icon in the top bar ("Physics Sandbox"). 



---------------------------------------------

#### The examples

- **running.py** evolve running soft robots in a terrestrial environment. 

- **swimming.py** a simple mesh-based fluid model, that allows you to observe how soft morphologies evolve in a fluid environment.

- **growing.py** plants that grow towards a light source.

--------------------------------------------
 


5. Documentation
-------------

Online documentation for Voxelyze is available [here](http://jonhiller.github.io/Voxelyze/annotated.html).


6. License
-------

Released under a MIT License (MIT).

