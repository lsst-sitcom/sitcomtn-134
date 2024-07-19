.. image:: https://img.shields.io/badge/sitcomtn--134-lsst.io-brightgreen.svg
   :target: https://sitcomtn-134.lsst.io
.. image:: https://github.com/lsst-sitcom/sitcomtn-134/workflows/CI/badge.svg
   :target: https://github.com/lsst-sitcom/sitcomtn-134/actions/

#############################################
CBP Pointing and Ghosting Simulation Notebook
#############################################

SITCOMTN-134
============

This notebook performs raytracing through the CBP and LSST and computes ghosting and transmission profiles. It has three main uses: 
1. Returns CBP and LSST alt/az pointings for a given positioning of the CBP within the observatory dome and desired CBP pointing on the M1 pupil. 
2. Raytracing for any CBP mask, returning final beam positions on the focal plane of LSSTcam and Comcam. 
3. Ghosting analysis: raytracing returns realistic estimations of ghosting along with transmission values for the CBP across the wavelength spectrum.

Links
=====

- Live drafts: https://sitcomtn-134.lsst.io
- GitHub: https://github.com/lsst-sitcom/sitcomtn-134

Build
=====

This repository includes lsst-texmf_ as a Git submodule.
Clone this repository::

    git clone --recurse-submodules https://github.com/lsst-sitcom/sitcomtn-134

Compile the PDF::

    make

Clean built files::

    make clean

Updating acronyms
-----------------

A table of the technote's acronyms and their definitions are maintained in the ``acronyms.tex`` file, which is committed as part of this repository.
To update the acronyms table in ``acronyms.tex``::

    make acronyms.tex

*Note: this command requires that this repository was cloned as a submodule.*

The acronyms discovery code scans the LaTeX source for probable acronyms.
You can ensure that certain strings aren't treated as acronyms by adding them to the `skipacronyms.txt <./skipacronyms.txt>`_ file.

The lsst-texmf_ repository centrally maintains definitions for LSST acronyms.
You can also add new acronym definitions, or override the definitions of acronyms, by editing the `myacronyms.txt <./myacronyms.txt>`_ file.

Updating lsst-texmf
-------------------

`lsst-texmf`_ includes BibTeX files, the ``lsstdoc`` class file, and acronym definitions, among other essential tooling for LSST's LaTeX documentation projects.
To update to a newer version of `lsst-texmf`_, you can update the submodule in this repository::

   git submodule update --init --recursive

Commit, then push, the updated submodule.

.. _lsst-texmf: https://github.com/lsst/lsst-texmf
