# Some convenient extensions to MeSH

[MeSH](https://www.ncbi.nlm.nih.gov/mesh) (Medical Subject Headings) is
a NLM controlled vocabulary thesaurus. MeSH is structured as an ontology
and is used for indexing articles for PubMed. Data sets included here
provide more convenient access to this vocabulary as simple tables (in
`rds` format).

R-based build process are detailed
[here](https://github.com/jaytimm/mesh-builds/tree/main/build). Raw data
from MeSH have been included
[here](https://github.com/jaytimm/mesh-builds/tree/main/download).

## Datasets

### `descriptor-terms`

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

### `descriptor-tree-numbers`

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

### `supplemental-terms`

``` r
readRDS('data/data_scr_thesaurus.rds') |>
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

## Notes & useful links:

-   [MeSH XML data
    elements](https://www.nlm.nih.gov/mesh/xml_data_elements.html)

-   XML elements as [RDF](https://id.nlm.nih.gov/mesh/D000001.html)

-   Supplementary Concept Records

> ‘SCR records are created for some chemicals, drugs, and other concepts
> such as rare diseases. They are labeled as “MeSH Supplementary Concept
> Data” and the unique ID begins with the letter “C.”’

> ‘Supplementary Concept Records - these are not full MeSH Headings and
> do not fall under the MeSH tree hierarchy. Many times they are used to
> identify substances that are not included in the MeSH terms.’

> ‘These do not belong to the controlled vocabulary as such and are not
> used for indexing MEDLINE articles; instead they enlarge the thesaurus
> and contain links to the closest fitting descriptor to be used in a
> MEDLINE search. Many of these records describe chemical substances.’

-   [descriptor-terms file
    download](https://nlmpubs.nlm.nih.gov/projects/mesh/MESH_FILES/xmlmesh/)
    – as `desc20YY.gz`

-   [tree file
    download](https://nlmpubs.nlm.nih.gov/projects/mesh/MESH_FILES/meshtrees/)
    – as `mtrees20YY.gz`

-   [supplemental-terms file
    download](https://nlmpubs.nlm.nih.gov/projects/mesh/MESH_FILES/xmlmesh/)
    – as `supp20YY.gz`

-   [Utility functions](https://github.com/scienceai/mesh-tree) –

## Working examples:
