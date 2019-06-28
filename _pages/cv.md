---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

EDUCATION
======
* M.S. in Simulation Based Mechanical Engineering Science, University of Colorado, Boulder, 2014
* Ph.D in Applied Mathematics, Washington State University, 2020 (expected)

EXPERIENCE
======
* **Washington State University**
* Graduate Researcher, *May 2016 - present*	
* Developing efficient and scalable algorithms for tool path planning in additive manufacturing (AM) using combinatorial topology and discrete optimization.
* Developed novel mathematical theory and scalable algorithms to generate continuous tool path with no crossover for any arbitrary partial fill problem in AM. Developed a unique framework to integrate it with AM. (Manuscript in preparation)
    
* **Oak Ridge National Laboratory (ORNL)**  
* Research Collaboration, *May 2019 – present*
* Developing multi-robot additive manufacturing framework to reduce print time and failures, jointly with researchers from MIT and ORNL.
 
* **Oak Ridge National Laboratory (ORNL)**   
* Research Intern, *Jun 2017 - Dec 2017* 
* Developed an optimal tool path traversal algorithm based on Traveling salesman problem (TSP) for any dense fill problem in AM. Implemented these algorithms in Python and C++, using CPLEX Python and C++ API. Further, effects of mechanical parameter of AM on tool path is jointly investigated with researchers from MIT and ORNL (Manuscript in preparation).    
* Developed a Python module to do Euler Transformation of any arbitrary infill lattice. 
* Testing and integrating variable density hexagonal meshing library in C++ for ORNL SLICER 2.

* **Oak Ridge National Laboratory (ORNL)**
* Research Intern, *May 2018 - Aug 2018* 
* Integrated Triangle mesh generator library in C++ with ORNL SLICER 2. 
* Developed C++ module to do Euler transformation of Triangle mesh and integrated it with ORNL SLICER 2. 

* **Washington State University** 
* Graduate Research, *Jan 2015 – May 2016*
* Developed a C++ module in lammps from scratch for nanoscale fluids, works for both shared memory and distributed shared memory systems. 
* Developed a C++ tool that captures 3D geometry projections on any plane in 3D during simulation in lammps and a C tool to handle pre and post processing for lammps involving multiple formats. 

* **NEi Software**, Westminster, CA                                                                                                                    
* Finite Element Analysis intern, *May 2013 - Aug 2013*
* Testing and developing NEi Nastran non-linear optimization solver written in C++.  
* Integrated and tested a non-linear optimization solver, IPOPT to NEi Nastran that gives better performance in terms of checkerboard and symmetry of design when forces are symmetric.   

TECHNICAL SKILLS
======
* Packages: Open MP, open MPI, SciPy, NumPy, pandas, Pyspark, Cplex, lpsolve, Caffe, TensorFlow   

PUBLICATIONS
======
  <ul>{% for post in site.publications %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
  