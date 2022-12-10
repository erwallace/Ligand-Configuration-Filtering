# Filtering Ligand-Protein Configurations by Salt Bridge Length

This is my first cheminformatics project and I have been using it as an opportunity to learn the RDKit library. I was given the idea after a discussion with 
computational chemist at CHARM Theraputics who kindly provided the protein and ligand input files.

**Why is filtering ligand positions useful?**

The nature of ligand-protein binding is at the centre of medicine, whether that be preventing illness or designing new drugs to treat disease. Much of this comes down 
to how drugs and pathogens bind to proteins in the human body. When developing *de novo* drugs, understanding where these will bind to a protein is very important 
particuarly as proteins configuration are affected by the position of the binding ligand. Hence, filtering possible ligand positions is an important step in the 
development of drugs.

**What does the script do?**

The purpose of this script is that, given a protein (in a PDB file), a residue number and a set of possible docked ligand configurations, this script will return a 
list of ligand configurations that could form salt bridges (under a threshold distance) with the specified residue.

The returned ligands also have an SDTag specifying the maximum and minimum allowed salt bridge length.

The files included here are for the ligand 5HT2A and the Aspartate residue at index 155. I have defined the salt bridge as a oxygen-nitrogen distance of less than 3.5Å.
For simplicity I have assumed that all conjugated nitrogens and adjacent to aromatic systems cannot from salt bridges.

**What next?**
- Learn more about SMARTS matching and use this to find the bridging groups and basic nitrogens. This will allow me to compute all possible salt bridges to any residue,
and then perform a simple filter to ASP155 at the end.
- Add in the logger library, this will help with debugging when I add additional features. Unit testing will also help.
- Find a more robust way to filter nitrogens as some conjugated nitrogens can form salt bridges (e.g. amidine and guanidine). This might be fixed by using SMARTS.
