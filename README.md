# GRC Sierra Leone & Guinea Analysis Manuscript

###  **Genetic Report Cards (GRCs)**
The Genetic Report Cards (GRCs) are comprehensive datasets that provide detailed genetic information about malaria parasites. These datasets are derived from blood samples collected from malaria-infected individuals. The samples undergo a series of processes:

1. **Sample Collection:** Blood samples are collected from individuals infected with malaria.
2. **Parasite Isolation:** The malaria parasites are isolated from the blood samples.
3. **DNA Extraction:** The DNA of the malaria parasites is extracted.
4. **Genome Sequencing:** The extracted DNA is sequenced to determine the genetic makeup of the parasites.
5. **Data Compilation:** The genetic data is compiled into the GRCs, which include various genetic markers, mutations, and other relevant information. 

The GRCs provide valuable insights into the genetic diversity, drug resistance, and transmission patterns of malaria parasites, aiding in the development of effective control strategies.


### **Purpose of the Analysis**

The primary objectives of this analysis are:

* **Prevalence and Diversity:** To understand the prevalence and genetic diversity of malaria parasites in different regions.
* **Drug Resistance:** To identify and characterize drug resistance profiles of malaria strains.
* **Geographical Mapping:** To map the spread and relatedness of malaria strains across various locations.
* **Genetic Relationships:** To explore the genetic relationships between samples using IBS matrices and related plots.


### **Dataset Overview**

We have Genetic Report Cards from various countries like **The Gambia**, **Sierra Leone**, **Guinea**, **Cameroon**, **Ethiopia**, **Nigeria** etc. 
Below is an example of some columns present in the dataset:

* **Sample Internal ID:** Unique identifier for each sample.
* **ENA Accession Number:** Identifier for the sample in the European Nucleotide Archive.
* **Sample External ID:** Another identifier, possibly from an external source or study.
* **Date of Collection:** Date when the sample was collected.
* **Location:** Specific location where the sample was collected.
* **Country:** Country of sample collection.
* **Study:** Identifier for the study the sample is part of.
* **Species:** Species of the malaria parasite (e.g., Plasmodium falciparum).
* **Important Genetic Markers Columns**
  + **PfCRT:** Gene associated with chloroquine resistance.
  + **PfDHPS:** Gene linked to sulfadoxine-pyrimethamine resistance.
  + **80 SNPs:** Single nucleotide polymorphisms used to assess genetic diversity and relatedness among samples.


### **Analysis Steps**

This analysis was conducted using R, with R Markdown utilized to document the steps in code blocks. Packages such as dplyr and ggplot2 were used for data manipulation and visualization.

1. **Clean the Data:** Filter for samples that contain the Plasmodium falciparum specie.
2. **Classify Samples by Drug Resistance:** Create a function to classify samples as: 
   + **Resistant**: Samples with haplotypes containing mutations that correspond to chloroquine resistance, e.g., **CVIET**.   
   + **Mixed Resistant**: Samples with haplotypes containing mixed mutations that correspond to chloroquine resistance, e.g., **CV[M/I][N/E][K/T]**.
   + **Sensitive**: Samples with haplotypes that have no mutations and hence correspond to chloroquine sensitivity, e.g., **CVMNK**.
   
   After this classification, we filter out other cases such as  **undetermined** and **missing** haplotypes.
3. **Summarize Data:** Summarize the data by location and Haplotype condition.
4. **Generate Distribution Plots and Tables:** Create plots and tables to show the distribution of drug resistance across different locations. E.g. Pie charts, bar charts etc.
5. **Generate Distribution maps:** Create maps using the sample count and distributions tables for the haplotype condition and mutations. E.g. Sample Count map, drug resistance map, mutation map, alle proportion map etc. 
6. **Calculate IBS Matrix:** Compute the Identity-By-State (IBS) matrix to assess genetic similarity between samples.
7. **Generate Connection and Cluster Plots:** After generating the IBS matrix we use it to generate varous visualizations like, Connectedness Maps, Neighbour Joining trees, heatmaps, PCoA scatter plot etc. 

