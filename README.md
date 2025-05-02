# Orthogonal-DNA-Library-Generator


📘 Project Introduction:
This repository implements a DNA sequence generator and screening pipeline inspired by the design principles outlined in the Supplementary Methods of “DNA-based programmable gate arrays for general-purpose DNA computing” by Hui Lv et al. (2023, Nature). The tool is developed to produce a high-quality orthogonal DNA sequence library for domains β and μ used in programmable molecular computing systems. Key design constraints are enforced to minimize crosstalk, structural interference, and unintended bonding—ensuring reliability in downstream logic gate implementation on DPGA (DNA Programmable Gate Arrays).

📄 Rephrased Description for Repository (README Section):

🧬 Random DNA Sequence Generation & Screening Tool
This Python-based tool generates a library of 12-nucleotide DNA sequences composed from the nucleotide set A, C, and T, designed for orthogonal and low-leakage use in DNA computing components (e.g., logic gates on DPGAs). The tool implements a multi-stage filtering process to enforce biochemical and information-theoretic constraints:

🛑 Constraints Applied:
Pattern Avoidance:

Sequences containing the patterns "TTTT", "AAAA", or "CCC" are excluded to minimize homopolymer-induced artifacts.

Hamming Distance Rule:

Any two sequences must differ in more than 4 positions, ensuring signal separation and orthogonality.

Common Subsequence Limit:

The longest common subsequence between any two sequences must be less than 8 nucleotides.

Positional Base Repetition Rule:

No more than 5 identical bases at the same position across the dataset (column-wise constraint).

Base Neighborhood Rule (for edge case in Rule 4):

If two sequences share 5 identical bases at the same position, their surrounding bases must not form a C-T pair, to prevent strong unintended T-G mismatched bonds.

💾 Output:
The final set of sequences passing all filters is saved to a variable library for downstream use in the design of DNA computing components.

https://github.com/armanhajizadeh/Orthogonal-DNA-Library-Generator/blob/main/Screenshot%202025-05-02%20at%2019.18.55.png
