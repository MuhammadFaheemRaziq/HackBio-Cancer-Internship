**Stage 02 Task**

**HackBio Internship: Cancers**

![](media/image1.jpeg){width="1.1041666666666667in"
height="1.1041666666666667in"}

**[Title]{.underline}**

Gene Expression Analysis and Functional Enrichment of Differentially
Expressed Genes

**[Authors]{.underline}**

Favour Igwezeke^1^, Jessica ovabor^2^, Anarghya Hegde^3^, Oluwatobiloba
Johnson Osedimilehin^4^, Ogochukwu Nwaigwe^5^, Muhammad Faheem Raziq^6^

**[Contributors Information]{.underline}**

| Authors | Slack ID                                                   | Email                           |
|---------|------------------------------------------------------------|---------------------------------|
| 1       | <https://hackbiointern-leo4437.slack.com/team/U07KE59TWEP> | <beingfave@gmail.com>           |
| 2       | <https://hackbiointern-leo4437.slack.com/team/U07JVPSU917> | <ovaborjessica85@gmail.com>     |
| 3       | <https://hackbiointern-leo4437.slack.com/team/U07JM2UDL7R> | <anarghyahegde@outlook.com>     |
| 4       | <https://hackbiointern-leo4437.slack.com/team/U07JP06QDB4> | <tobijohnson01@gmail.com>       |
| 5       | <https://hackbiointern-leo4437.slack.com/team/U07KP1D2F24> | <nwaigweogochukwu756@gmail.com> |
| 6       | <https://hackbiointern-leo4437.slack.com/team/U07KUECLR40> | <faheemraziq1999@gmail.com>     |

[  
]{.underline}

**1. Overview**

In this analysis, a gene expression dataset was processed, visualised
and interpreted to gain insights on the biological importance of
differential expression. To investigate the pathways associated with
gene expression under specific conditions, heatmaps were generated,
clustering was performed, and functional enrichment analysis was
conducted. This analysis was completed by a team of 3 data scientists
and 3 biomarker hunters.

**[Dataset utilised for the study:]{.underline}**

Glioblastoma gene expression dataset

The top 500+ differentially expressed genes are included in this dataset
and the goal of the study was to visualise the data, find significant
gene clusters and employ enrichment analysis to determine the biological
significance of these genes.

**2. Data Preprocessing**

Prior to generating heatmaps, necessary preprocessing steps were
conducted:

- **Normalisation**: Data was normalised to ensure comparable expression
  values across genes and samples.

- **Filtering**: Differentially expressed genes were filtered based on
  fold change and p-values, depending on team-decided threshold values.
  Genes with a fold change greater than 2 and p-values less than 0.05
  were focussed on for significant upregulation, and fold change less
  than -2 for significant downregulation.

**[Tools used]{.underline}**:

R, tidyverse, dplyr, ShinyGo, and DESeq.

**3. Heatmap Generation**

To visualise the gene expression data, *heatmap.2()* function from the
*gplots* package in RStudio was utilised. Heatmaps were generated using
two different colour palettes: *diverging* and *sequential*. The purpose
of selecting these colour schemes was to improve the plots' readability
and facilitate the differentiation of various expression levels across
the dataset.

***3.1 Importance of Colour Selection***

- **Diverging colour palette**: This palette helps in clearly
  distinguishing between upregulated and downregulated genes. It uses
  two contrasting colours, making it ideal for highlighting significant
  changes.

![](media/image2.jpg){width="5.333333333333333in" height="5.5in"}

**Figure 1:** Image of divergent colour palette

- **Sequential colour palette**: This palette helps to visualise a
  gradient of expression changes. It is useful for observing trends
  where changes are more gradual rather than radically divergent.

![](media/image3.jpg){width="5.333333333333333in" height="5.5in"}

**Figure 2:** Image of sequential colour palette

Both colour variants of the heatmap were included to demonstrate the
impact of colour choices on data interpretation.

**4. Clustering of Genes and Samples**

Three different clustering strategies were explored to investigate gene
expression patterns across samples:

- **Clustering genes alone (rows)**: Grouping genes that show similar
  expression patterns across samples.

![](media/image4.jpg){width="5.33in" height="5.5in"}

**Figure 3:** Clustering gene (rows)

- **Clustering samples alone (columns):** Grouping samples with similar
  expression patterns.

![](media/image5.jpg){width="5.33in" height="5.5in"}

**Figure 4:** Clustering samples (columns)

- **Clustering both genes and samples**: A combined approach to observe
  how genes and samples cluster together.

![](media/image6.jpg){width="5.33in" height="5.5in"}

**Figure 5:** Clustering of both genes (rows) and samples (columns)

**5. Subsetting Genes Based on Expression**

To get the p-values and fold changes, DESeq was performed and then
subsets of genes were identified based on significant upregulation and
downregulation using team-decided fold change and p-value cutoffs; a
significance threshold of 0.05 was chosen.

- *Upregulated genes*: log2Foldchange \> 1 and P value \< 0.05

- *Downregulated genes*: log2Foldchange \< -1 and P value \< 0.05

**6. Functional Enrichment Analysis**

Functional enrichment analysis was performed using *ShinyGO* to
determine which pathways are overrepresented in the gene expression
dataset. The analysis helped identify biological processes associated
with significantly downregulated genes but there were no biological
processes that were significantly enriched with the genes in the
upregulated set.

**6.1 Enrichment Results**

Based on the analysis, the top 5 enriched pathways were identified. A
*bubble plot* was generated to visualise these pathways, showing the
number of genes involved and the significance of each pathway. The size
of the bubbles corresponds to the *negative log10 of the p-value*,
emphasising pathway significance.

**Top 5 Enriched Pathways**:

1.  Regulation of Transcription by RNA Polymerase II

2.  Transcription by RNA Polymerase II

3.  Regulation of Biosynthetic Process

4.  Nervous System Development

5.  Anatomical Structure Morphogenesis

**7**. **Detailed Description of Top 3 Enriched Pathways**

Here a detailed description of the top 3 enriched pathways according to
biological processes is provided:

**7.1 Regulation of Transcription by RNA Polymerase II (GO:0006357)**

*Enrichment FDR: 0.0024*

*Number of Genes Involved: 21*

*Total Pathway Genes: 2747*

*Fold Enrichment: 2.34*

One essential biological process that governs the transcription of DNA
into messenger RNA (mRNA) is Transcription Regulation by RNA polymerase
II. The transcription of genes that code for proteins is carried out by
RNA polymerase II, whose regulation is necessary for cell development,
differentiation and responsiveness to external stimuli. The
over-representation of this pathway in the dataset implies that
transcriptional regulation is a major contributor to the observed gene
under-regulation.

**7.2** **Transcription by RNA Polymerase II (GO:0006366)**

*Enrichment FDR: 0.0024*

*Number of Genes Involved: 21*

*Total Pathway Genes: 2859*

*Fold Enrichment: 2.34*

The expression of genes and cellular function depend on the
Transcription process by RNA polymerase II. The pathway's
over-representation suggests that a large number of the genes in this
dataset are crucial for transcriptional processes. The pathway's
significance in maintaining cellular homeostasis and controlling gene
expression in response to both external and internal signals is
highlighted by the high fold enrichment.

**7.3** **Regulation of Biosynthetic Process (GO:0009889)**

*Enrichment FDR: 0.0024*

*Number of Genes Involved: 25*

*Total Pathway Genes: 4545*

*Fold Enrichment: 2.08*

In simpler terms, the process by which cells generate complex chemicals
from simpler ones is known as Biosynthesis and it is essential to both
metabolism and cellular growth. The regulation of biosynthetic pathways
is essential for cellular growth, cellular energy-balance maintenance
and for its responsive function towards external stimuli. The pathway's
enrichment in this dataset implies that under-regulating genes related
to biosynthetic activities may have important metabolic repercussions.

**8. Visualisation of Enrichment Results**

To convey the importance of these pathways, a *bubble plot* was
constructed. Each bubble represents one of the top 5 pathways, with the
size of the bubble proportional to the number of genes involved and the
colour representing the *log10 p-value* for enrichment significance.

![](media/image7.PNG){width="6.007221128608924in"
height="3.457541557305337in"}

**Figure 6:** Bubble plot of top 5 enriched pathways.

**9. Conclusion**

The enrichment analysis conducted in this study reveals the critical
roles of biological processes such as transcriptional regulation and
biosynthesis in the dataset of the underregulated genes. The identified
pathways are heavily involved in maintaining cellular homeostasis,
development, and metabolism. Their dysregulation may have broad effects
in domains like metabolic diseases and neurobiology. FOXP2, HIF3A and
GBX2 are among the genes found in these pathways that are critical for
functions ranging from transcription to neurogenesis. When it comes to
developmental disorders and metabolic dysfunctions, more research into
the functional implications of these pathways may yield important
insights into disease mechanism and cause.
