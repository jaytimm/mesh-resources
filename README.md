# MeSH resources (2026 update)

> **mesh-builds** turns NLM MeSH XML and tree files into three R-ready
> tables: a **descriptor thesaurus** (terms and concepts), a
> **supplementary concept thesaurus** (SCR terms), and a **tree table**
> that links descriptors to tree numbers and high-level category labels.
> The pipeline is in
> [`descriptor-records-trees.Rmd`](https://github.com/jaytimm/mesh-builds/blob/main/descriptor-records-trees.Rmd);
> the RDS outputs power the R package
> [**puremoe**](https://github.com/jaytimm/puremoe).

> **May 2026:** built from MeSH `desc2026`, `supp2026`, and `mtrees2026`
> (newterms release).

## MeSH ontology

> Based on MeSH files `desc2026`, `mtrees2026` & `supp2026`.

### `descriptor-terms`

[Raw
data](https://nlmpubs.nlm.nih.gov/projects/mesh/MESH_FILES/xmlmesh/)

``` r
readRDS('data/data_mesh_thesaurus.rds') |>
  head() |> knitr::kable()
```

| DescriptorUI | DescriptorName | ConceptUI | TermUI | TermName | ConceptPreferredTermYN | IsPermutedTermYN | LexicalTag | RecordPreferredTermYN |
|:---|:---|:--|:---|:---------------------------------------|:-----|:----|:---|:-----|
| D000001 | Calcimycin | M0000001 | T000002 | Calcimycin | Y | N | NON | Y |
| D000001 | Calcimycin | M0000001 | T001124965 | 4-Benzoxazolecarboxylic acid, 5-(methylamino)-2-((3,9,11-trimethyl-8-(1-methyl-2-oxo-2-(1H-pyrrol-2-yl)ethyl)-1,7-dioxaspiro(5.5)undec-2-yl)methyl)-, (6S-(6alpha(2S*,3S*),8beta(R\*),9beta,11alpha))- | N | N | NON | N |
| D000001 | Calcimycin | M0353609 | T000001 | A-23187 | Y | N | LAB | N |
| D000001 | Calcimycin | M0353609 | T000001 | A 23187 | N | Y | LAB | N |
| D000001 | Calcimycin | M0353609 | T000003 | Antibiotic A23187 | N | N | NON | N |
| D000001 | Calcimycin | M0353609 | T000003 | A23187, Antibiotic | N | Y | NON | N |

### `descriptor-tree-numbers`

[Raw
data](https://nlmpubs.nlm.nih.gov/projects/mesh/MESH_FILES/meshtrees/)

``` r
readRDS('data/data_mesh_trees.rds') |>
  head() |> knitr::kable()
```

| DescriptorUI | DescriptorName | tree_location | code | cats | mesh1 | mesh2 | tree1 | tree2 |
|:------|:-------|:---------|:---|:---------|:----------|:---------------|:---|:----|
| D000001 | Calcimycin | D02.355.291.933.125 | D | Chemicals and Drugs | Organic Chemicals | Ethers | D02 | D02.355 |
| D000001 | Calcimycin | D02.540.576.625.125 | D | Chemicals and Drugs | Organic Chemicals | Lactones | D02 | D02.540 |
| D000001 | Calcimycin | D03.633.100.221.173 | D | Chemicals and Drugs | Heterocyclic Compounds | Heterocyclic Compounds, Fused-Ring | D03 | D03.633 |
| D000001 | Calcimycin | D04.345.241.654.125 | D | Chemicals and Drugs | Polycyclic Compounds | Macrocyclic Compounds | D04 | D04.345 |
| D000001 | Calcimycin | D04.345.674.625.125 | D | Chemicals and Drugs | Polycyclic Compounds | Macrocyclic Compounds | D04 | D04.345 |
| D000002 | Temefos | D02.705.400.625.800 | D | Chemicals and Drugs | Organic Chemicals | Organophosphorus Compounds | D02 | D02.705 |

### `supplemental-terms`

[Raw
data](https://nlmpubs.nlm.nih.gov/projects/mesh/MESH_FILES/xmlmesh/)

``` r
readRDS('data/data_scr_thesaurus.rds') |>
  head() |> knitr::kable()
```

| DescriptorUI | DescriptorName | ConceptUI | TermUI | TermName | ConceptPreferredTermYN | IsPermutedTermYN | LexicalTag | RecordPreferredTermYN |
|:-----|:------|:----|:----|:-------------------|:---------|:-------|:----|:--------|
| C000002 | bevonium | M0040005 | T070005 | bevonium | Y | N | NON | Y |
| C000002 | bevonium | M0040005 | T000946882 | 2-(hydroxymethyl)-N,N-dimethylpiperidinium benzilate | N | N | NON | N |
| C000002 | bevonium | M0040001 | T070001 | Acabel | Y | N | TRD | N |
| C000002 | bevonium | M0040002 | T070002 | CG 201 | Y | N | LAB | N |
| C000002 | bevonium | M0307342 | T337342 | bevonium sulfate (1:1) | Y | N | NON | N |
| C000002 | bevonium | M0402330 | T070003 | bevonium methyl sulfate | Y | N | NON | N |

## Maintained outputs

``` r
list.files('data', pattern = 'data_.*\\.rds$')
# [1] "data_mesh_thesaurus.rds" "data_mesh_trees.rds" "data_scr_thesaurus.rds"
```

### Notes & useful links:

-   [MeSH XML data
    elements](https://www.nlm.nih.gov/mesh/xml_data_elements.html)

-   XML elements as [RDF](https://id.nlm.nih.gov/mesh/D000001.html)

-   [Utility functions](https://github.com/scienceai/mesh-tree)

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
