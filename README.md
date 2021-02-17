# A Sparse Kernel Relevance Model for Image Annotation

Current version: 0.1. Distributed under a Creative Commons Attribution-NonCommercial License: http://creativecommons.org/licenses/by-nc/4.0/deed.en_US

This code is a memory efficient implementation of the Continous Relevance Image Annotation Model. The code is memory frugal but disk heavy, enabling very large image datasets to be processed on machines with a modicum of RAM e.g. your laptop.

[Sean Moran and Victor Lavrenko. A Sparse Kernel Relevance Model for Image Annotation. International Journal of Multimedia Information Retrieval, 2014](http://link.springer.com/article/10.1007%2Fs13735-014-0063-y)

## Prerequisites:

1. Yari MTX library: see the compiled version (mtx) included with this distribution, or check out: http://ir.inf.ed.ac.uk/wiki/doku.php?id=yari:mtx
2. Korn Shell: sudo apt-get install ksh
3. CSH: sudo apt-get install csh

If you use the SKL-CRM code for a publication, please cite the following papers:

```
@article{year={2014}, issn={2192-6611}, journal={International Journal of Multimedia Information Retrieval}, doi={10.1007/s13735-014-0063-y}, title={A sparse kernel relevance model for automatic image annotation}, url={http://dx.doi.org/10.1007/s13735-014-0063-y}, publisher={Springer London}, keywords={Image annotation; Object recognition; Kernel density estimation}, author={Moran, Sean and Lavrenko, Victor}, pages={1-21}, language={English} }
```
```
@inproceedings{Moran:2014:SKL:2578726.2578734, author = {Moran, Sean and Lavrenko, Victor}, title = {Sparse Kernel Learning for Image Annotation}, booktitle = {Proceedings of International Conference on Multimedia Retrieval}, series = {ICMR '14}, year = {2014}, isbn = {978-1-4503-2782-4}, location = {Glasgow, United Kingdom}, pages = {113:113--113:120}, articleno = {113}, numpages = {8}, url = {http://doi.acm.org/10.1145/2578726.2578734}, doi = {10.1145/2578726.2578734}, acmid = {2578734}, publisher = {ACM}, address = {New York, NY, USA}, keywords = {Image Annotation, Statistical Models, Visual Features}, }
```

## Usage

Obtain the pre-processed dataset files for Corel5K, IAPR-TC12 and ESPGame:

https://www.dropbox.com/sh/289zxx8teqpjyb0/AADTMR_flAlxbojykU4-8Onta?dl=0

These are simply the Tagprop features available for download at INRIA here:

http://lear.inrialpes.fr/people/guillaumin/data.php

But formatted in ROW-COLUMN-VALUE (RCV) format appropriate for loading into MTX

2. Change the environment variables in the set_env_vars function in run_crm.ksh 
   to values appropriate to your system

3. Run the model: ./run_crm.ksh

Results are in res.log and on standard output. You should get the following results 
on the Corel5k testing dataset:

Results computed on 260.000000 words:                                                                                                                                         
MPR:  0.362088                                                                                                                                                                
MPP:  0.324235                                                                                                                                                                
F1:  0.3421                                                                                                                                                                   
Words recall > 0:  161.000000   

To replicate the SKL-CRM results change the kernels in initialise.sh to the optimal
kernels specified in our journal paper. See the comments in initialise.sh for further
guidance on how to do this.
 
## Copyright

Copyright (C) by Sean Moran, University of Edinburgh

Please send any bug reports to sean.j.moran@gmail.com
