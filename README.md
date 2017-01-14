=======================================================================

PSOVina2LS version 1.0                                                    

Allan H. Lin & Giotto H. K. Tai & Shirley W. I. Siu                                   

                                                                       

Computational Biology and Bioinformatics Lab (CBBio)                        

University of Macau                                                    

                                                                       

Visit http://cbbio.cis.umac.mo for more information.                   

                                                                       

PSOVina2LS was developed based on the framework of PSOVina.                                                                                

For more information about Vina, please visit http://vina.scripps.edu.                                                                       

=======================================================================



0. REQUIRED SOFTWARE

   For successful compilation, please install Boost (version 1.59.0) 

   from http://www.boost.org. For preparing molecules for docking, 

   please install AutoDockTools (ADT) from http://mgltools.scripps.edu.



1. INSTALLATION



   The installation basically follows the installation of AutoDock Vina. 

   The steps are simple:



     a. unpack the files

     b. cd psovina2ls_1.0/build/<your-platform>/release

     c. modify Makefile to suit your system setting

     d. type "make" to compile

    

    The binary psovina2ls will be generated at the current directory. You can 

    copy this binary to a directory in your PATH e.g. /usr/local/bin, or add

    the path of the current directory to your PATH.



2. RUNNING PSOVINA2LS



   You can run psovina2ls as the way you run vina but additional three 

   parameters (optional) are used to specify how the PSO algorithm performs 

   searching:



   % <path-to-psovina2ls>/psovina2ls



   PSO parameters (optional):

       --num_particles arg (=8)      Number of particles

       --w arg (=0.36)               Inertia weight

       --c1 arg (=0.99)              Cognitive weight 

       --c2 arg (=0.99)              Social weight 
 
   2LS parameters (optional):
       --Cr arg(=15)                 Roughing condition
       --R arg(=0.1)                 Roughing factor



   For example, docking Kifunensine in the Mannosidase enzyme (PDBID 1ps3 from

   the PDBbind v2012 dataset) using PSOVina2LS with default PSO parameters in a 

   8-core computer and return the lowest energy prediction:



   % <path-to-AutoDockTools>/prepare_ligand4.py -l 1ps3_ligand.mol2 \

     -o 1ps3_ligand.pdbqt -A 'hydrogens' -U 'nphs_lps_waters'



   % <path-to-AutoDockTools>/prepare_receptor4.py -r 1ps3_protein.pdb \

     -o 1ps3_protein.pdbqt -A 'hydrogens' -U 'nphs_lps_waters' 



   % <path-to-psovina2ls>/psovina2ls \

     --receptor 1ps3_protein.pdbqt --ligand 1ps3_ligand.pdbqt \

     --center_x  31.951 --center_y 65.5053 --center_z 7.63888 \

     --size_x    33.452 --size_y   27.612  --size_z   35.136  \ 

     --num_modes 1      --cpu 8  

   

   More test cases can be downloaded in our web site. 



3. DEVELOP PSOVINA2LS



   If you are interested in the source code of PSOVina2LS for any academic

   purposes, please note that the following files were newly developed   

   in our work or modified based on PSOVina:

   	src/lib/quasi_newton.cpp

	src/lib/pso_mutate.cpp



4. CITATION

   Please cite our paper if you have used PSOVina2LS. It would be nice to let us

   know that you found PSOVina2LS useful by sending us an email. 



   Allan H. Lin & Giotto H. K. Tai & Shirley W. I. Siu 

   Improving The Efficiency of PSOVina for Protein-Ligand Docking By Two-Stage Local Search 

   (Submitted) 



   Please check out our homepage for the updated citation.



5. CONTACT US

    

   Developer: Allan H. Lin <lhang33@126.com>, Giotto H. K. Tai <giottotai@yahoo.com.hk>

   Project P.I.: Shirley W. I. Siu <shirleysiu@umac.mo>



   Computational Biology and Bioinformatics Lab, University of Macau

   http://cbbio.cis.umac.mo

   http://www.cis.umac.mo/~shirleysiu


