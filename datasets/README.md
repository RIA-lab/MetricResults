# Dataset accession lists

Identifiers of the molecules in the datasets of the paper, for retrieving the structures and sequences from the public databases
(structures and predictor weights are third-party and are not redistributed). Retrieved 2026-10-13 from
[RCSB PDB](https://www.rcsb.org), [UniProt](https://www.uniprot.org), [PDBe](https://www.ebi.ac.uk/pdbe/) (SIFTS mapping of PDB entries to UniProt)
and [M-CSA](https://www.ebi.ac.uk/thornton-srv/m-csa/).

## Files
```
DATASETS.csv                   one row per dataset of the paper: size in the paper, members listed, file, sha256 of the file
accessions.csv                 one row per (dataset, identifier): dataset, id_type (PDB, UniProt, M-CSA, design model), accession, label
zymogen_pairs_evaluation.csv   the 21 proteins of the zymogen-mature evaluation pairs (Results 3.1.1)
plated_designs.csv             the 199 design models of the deposit; 192 are the plated designs (Results 3.1.2, 3.3.2)
substrate_swap_enzymes.csv     the 59 M-CSA enzymes of the substrate-swap experiment; 55 form the evaluation set (Results 3.2)
chemistry_ladder_systems.csv   the 74 systems of the re-predicted chemistry ladder: 59 natural enzymes and 15 designed systems (Results 3.4.1)
bglb.csv                       the BglB protein, its PDB entry and its catalytic residues (Results 3.3.1)
```

## Identifiers
* **PDB** entry ids are RCSB PDB accessions (four characters, `https://www.rcsb.org/structure/<id>`).
* **UniProt** accessions are UniProtKB accessions (`https://rest.uniprot.org/uniprotkb/<accession>`); for a PDB entry the accession is the
  one that the PDBe SIFTS mapping gives for the entry.
* **M-CSA** ids are the entry numbers of the Mechanism and Catalytic Site Atlas (`https://www.ebi.ac.uk/thornton-srv/m-csa/entry/<id>/`).
  `assembly` is the biological assembly of the PDB entry on which the M-CSA catalytic residues are placed. A PDB entry can belong to two M-CSA
  entries (PDB 2ZR8 belongs to M-CSA entries 330 and 956), so the 59 enzymes have 58 distinct PDB entries.
* **Design models** are the files of Supplementary Data 3 of Kim et al. (Nature 649, 246–253, 2026, doi:10.1038/s41586-025-09746-w); `design_campaign1__A1_ZETA_1.pdb`
  is the model of the design named ZETA_1 in well A1 of the first plate. The ordered sequences, the well of every design and the measured
  kcat/KM are in Supplementary Data 2 of that paper. The two crystal structures of the design ZETA_2 are the PDB entries 9PYJ (apo) and 9PYL (Zn(II)-bound).

## Notes on the files
* `substrate_swap_enzymes.csv`: `evaluation_set` is `yes` for the 55 enzymes of the evaluation set and `no` for the 4 that were excluded (`note`).
  The natural arm of the chemistry ladder is the same 59 enzymes.
* `plated_designs.csv`: the plated designs are the designs of the two 96-well plates (96 wells of each campaign); `plated` is `no` for the seven
  variant models of the design in well A1 of the first campaign (`variant`). `reported_kcat_KM` is `yes` for the 16 designs with a reported kcat/KM
  (5 of the first campaign, 11 of the second) and `no` for the other 176 plated designs; the values are in Supplementary Data 2 of the paper above.
  `chemistry_ladder` marks the 15 designed systems of the chemistry ladder.
* `zymogen_pairs_evaluation.csv`: one row per pair, listed by the UniProt accession of its protein (every pair is two forms of one protein).
  `propeptide_positions` and `mature_chain_positions` are the UniProt feature positions (residue numbers of the UniProt sequence) from which the
  zymogen and mature forms are told apart.
* `bglb.csv`: the BglB variants and their measurements are D2DCure data whose licence is unstated, so no variant, position or measurement is listed.

## Datasets without a member list in this release
The member lists of the following datasets are not part of this release (`DATASETS.csv`, column `members_listed` is 0): the 143-enzyme set, the
53-enzyme set and the pooled 195 enzymes of the catalytic lesion test (Methods 2.5.1); the 30 curated designs (the 15 designed systems of the
chemistry ladder are listed); the wider zymogen-mature sets of 55, 49, 45 and 28 pairs and the 96 same-state null pairs (only the 21 evaluation pairs are listed,
and only by protein: the PDB entries of the two forms are not listed).
