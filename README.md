# Public tables

6 data tables of the Results (Tables 5 to 10) and 31 supplementary tables of the paper, as CSV (UTF-8, comma-separated, one header row).
The Supplementary PDF describes every supplementary table (what a row is, what the key columns mean and which part of the paper uses it) and lists the data tables of the Results with the supplementary tables that hold their complete versions; the columns of a data table of the Results are those of its complete table.
`INDEX.csv` lists all tables with kind, title, what the paper uses it for, topic, size, licence flag and a sha256 of each file.

```
main/            T5 ... T10         Tables 5 to 10 of the paper (Tables 1 to 4, in the Methods, are descriptive and not released as files)
supplementary/   S1 ... S31        supplementary tables, numbered in the order in which the paper first cites them
INDEX.csv        id, file, title, where the paper uses it, rows, columns, licence flag, sha256
datasets/        PDB, UniProt and M-CSA accessions of the datasets of the paper (see datasets/README.md)
```

## Numbering
Supplementary tables are numbered S1, S2, S3 ... by first citation in the Methods and Results.
S1 and S2 describe the metric panel: the role of every distinct metric and what each named quantity reads.

## Conventions
* `applicability_status` says whether a metric can be tested in an experiment (`OK`, `GLOBAL`, `OK-KNOCKON`,
  `OK-PROVISIONAL`) or why not (`X-ARM`, `X-NOINPUT`, `X-BOOKKEEP`, `X-UNDEF-COV`,
  `X-CONFOUND`, `NOT-RUN`); the Supplementary PDF explains each.
* `lesion_test` is `catalytic lesion`, `second-shell lesion` or `deformation` (an experiment that could not be used).
* `mode` and `valid_modes` are `structure-space` or `prediction-based` (in the metric audit also `PLACER`, `any` or `deposit metadata`).
* Result tables carry the same columns for traceability of a row to its denominator: `claim_type`, `unit`, `n_units`,
  `n_clusters`, `cluster_def`, `k`, `N`, `k_of_N`, `denominator_def`, `status`, `licence_flag`.
* Pointers into the private project (file paths, hashes, internal ids) are not part of the public tables.

## Licence
Tables flagged `D2DCure_aggregate` in `INDEX.csv` (T8, S9, S10, S11) are aggregates of D2DCure BglB data, whose licence is
unstated. They contain no per-variant row. Check the licence before redistributing them.

## Integrity
`sha256` in `INDEX.csv` is the hash of each file as released.
