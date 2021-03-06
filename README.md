# autoVSimulator

This is a simulator for autonomous driving. 

To run the demo,
```python
python visualize_ngsim.py
python first_person_view.py
python flash_view.py
```

To start in Windows:

Install 32-bit Anaconda2 and set its build-in Python as the default Python.

Install Panda3D and set the Anaconda Python as the connected Python: (1)Uncheck the python2.7 during installing (2)Simply create a "panda.pth" file inside your copy of Python, containing the path of the panda directory and the bin directory within it on separate lines (for example C:\Program Files\Panda3D-1.2.3 and C:\Program Files\Panda3D-1.2.3\bin).

Install numpy(using command): pip install numpy

Install cvxopt(using command): conda install -c https://conda.anaconda.org/omnia cvxopt

-----

Visualization of intention prediction

[![Watch the video](https://img.youtube.com/vi/HenBoL-mchA/0.jpg)](https://youtu.be/HenBoL-mchA)

-----

Based on the simulator developed by Jianyu Chen and Changliu Liu in Berkeley MSC Lab in 2016.
