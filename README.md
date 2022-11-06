## Some convenient extensions to MeSH

### RMDs

### Datasets

-   descriptor-terms

``` r
readRDS('data/data_mesh_thesaurus.rds') |>
  head() |> knitr::kable()
```

| DescriptorUI | DescriptorName | ConceptUI | TermUI  | TermName           | ConceptPreferredTermYN | IsPermutedTermYN | LexicalTag | RecordPreferredTermYN |
|:------|:-------|:-----|:----|:---------|:-----------|:--------|:-----|:----------|
| D000001      | Calcimycin     | M0000001  | T000002 | Calcimycin         | Y                      | N                | NON        | Y                     |
| D000001      | Calcimycin     | M0353609  | T000001 | A-23187            | Y                      | N                | LAB        | N                     |
| D000001      | Calcimycin     | M0353609  | T000001 | A 23187            | N                      | Y                | LAB        | N                     |
| D000001      | Calcimycin     | M0353609  | T000004 | A23187             | N                      | N                | LAB        | N                     |
| D000001      | Calcimycin     | M0353609  | T000003 | Antibiotic A23187  | N                      | N                | NON        | N                     |
| D000001      | Calcimycin     | M0353609  | T000003 | A23187, Antibiotic | N                      | Y                | NON        | N                     |

-   tree-numbers

``` r
readRDS('data/data_mesh_trees.rds') |>
  head() |> knitr::kable()
```

| DescriptorUI | DescriptorName | tree_location           | code | cats                                  | mesh1                                     | mesh2                                   | tree1 | tree2   |
|:-----|:-----|:--------|:--|:-------------|:--------------|:-------------|:--|:---|
| D000001      | Calcimycin     | D03.633.100.221.173     | D    | Chemicals and Drugs                   | Heterocyclic Compounds                    | Heterocyclic Compounds, Fused-Ring      | D03   | D03.633 |
| D000002      | Temefos        | D02.705.400.625.800     | D    | Chemicals and Drugs                   | Organic Chemicals                         | Organophosphorus Compounds              | D02   | D02.705 |
| D000002      | Temefos        | D02.705.539.345.800     | D    | Chemicals and Drugs                   | Organic Chemicals                         | Organophosphorus Compounds              | D02   | D02.705 |
| D000002      | Temefos        | D02.886.300.692.800     | D    | Chemicals and Drugs                   | Organic Chemicals                         | Sulfur Compounds                        | D02   | D02.886 |
| D000003      | Abattoirs      | J01.576.423.200.700.100 | J    | Technology, Industry, and Agriculture | Technology, Industry, and Agriculture     | Industry                                | J01   | J01.576 |
| D000003      | Abattoirs      | J03.540.020             | J    | Technology, Industry, and Agriculture | Non-Medical Public and Private Facilities | Manufacturing and Industrial Facilities | J03   | J03.540 |

-   supplemental-terms

``` r
readRDS('data/data_src_thesaurus.rds') |>
  head() |> knitr::kable()
```

| SupplementalRecordUI | SupplementalRecordName                   | ConceptUI | TermUI  | TermName                                 | ConceptPreferredTermYN | IsPermutedTermYN | LexicalTag | RecordPreferredTermYN |
|:-------|:--------------|:----|:---|:--------------|:--------|:------|:----|:--------|
| C114158              | quantum dye macrocyclic europium-chelate | M0294520  | T324525 | quantum dye macrocyclic europium-chelate | Y                      | N                | NON        | Y                     |
| C114158              | quantum dye macrocyclic europium-chelate | M0294520  | T324524 | QD macrocyclic                           | N                      | N                | NON        | N                     |
| C008718              | osteoclast activating factor             | M0052808  | T082811 | osteoclast activating factor             | Y                      | N                | NON        | Y                     |
| C008720              | otoline                                  | M0052812  | T082815 | otoline                                  | Y                      | N                | NON        | Y                     |
| C002540              | miracil A                                | M0043189  | T073192 | miracil A                                | Y                      | N                | NON        | Y                     |
| C055240              | Leakadine                                | M0155620  | T185625 | Leakadine                                | Y                      | N                | TRD        | Y                     |

### Notes & useful links:
