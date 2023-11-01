# Engineering-Escherichia-coli-pyruvate-dehydrogenase-complex-to-reduce-a-noncanonical-redox-cofactor
This is the Rosetta docking protocol used in the manuscript from Professor Han Li lab at UC Irvine and Professor Justin Siegel lab at UC Davis. The Rosetta files listed here are for docking the ligand NMN, ligand FAD and Ec Lpd Lpd-Ortho variant. Rosetta version: 2018.24.post.dev+17.master.450949e 450949e481542459ae6534e867a61fe9709846be

In order to successfully run the simulation, all the files are required:

1. PDB file with the target ligands NMN and FAD bound in the active site. (Lpd_penta.pdb)
2. Parameter files for each cofactor that is readable by Rosetta and the corresponding conformers' library pdb. (X00.params, FAD.params)
3. Constraint file that restricts the movement of active site catalytic residues and relative position between ligand and active site residues (LPD.enzdes.cst)
4. Rosetta simulation option flag file (Lpd_ortho_flags)
5. Rosetta ligand docking protocol xml file (docking_2_mutations.xml)
6. Slurm submission file, only executed for cluster jobs running (submit_simulation.bash)

Below are example commands for generating protein-ligand models for LPD-Ortho:

Run the following command to perform Rosetta docking locally in MacOS system: Rosetta/main/source/bin/rosetta_scripts.default.macosclangrelease -database /Rosetta/main/database @Lpd_ortho_flags -out:path:all ./

Run the following command to perform Rosetta docking in the cluster: sbatch submit_simulation.bash
