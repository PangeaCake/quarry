Quarry for python3
==================

`original repo`_

.. _original repo: https://github.com/barneygale/quarry/

This repo has modifications so that quarry can run on python 3 :D

Installation
------------

Use ``pip`` to install quarry:

.. code-block:: console

    $ pip install quarry
    
Here's where the python 3 part comes out. However, do note YMMV.

Twisted on python 3 + windows was broken at least for me. To fix this, we need to do some extra stuff.

**HOWEVER: DO NOTE THAT THIS IS NOT GUARANTEED TO WORK AND EVEN AFTER THESE CHANGES MAY HAVE BUGS FOR PYTHON 3**

First you need to navigate to your Python/lib/site-packages/twisted folder.
Open twisted/python/lockfile.py and edit line 52 to be `_open = open`.

Then, download the two files `_win32stdio.py` and `_pollingfile.py` from this repo's twisted/ folder, and put them in your local twisted/internet/ folder.

Lastly, you may need to install win32api/pywin32. I did this by downloading http://www.lfd.uci.edu/~gohlke/pythonlibs/#pywin32, then running the following as that page suggests:

.. code-block:: console

    $ pip install filename.whl
    $ python C:\Python34\Scripts\pywin32_postinstall.py -install
    
Again, YMMV. Good luck.
