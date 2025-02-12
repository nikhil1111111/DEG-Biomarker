# Pupil-Bio
Data Analysis and Statistics &amp; NGS Alignment and Mutation Calling
The present test comprises two challenges designed to evaluate candidates’ technical and
analytical skills:
1. Data Analysis and Statistics: Assessing the ability to analyze and interpret complex data,
particularly phased methylation patterns.
2. NGS Alignment and Mutation Calling: Evaluating proficiency in processing raw
sequencing data, aligning reads to a reference genome, and identifying somatic
mutations.
______________________________________________________________________________
Task 1: Data Handling and Statistical Analysis
Objective: Assess candidates’ ability to handle complex data and apply statistical methods
effectively.
Background: CpG methylation is an epigenetic marker that varies across tissue types.
However, the methylation status of a single CpG site is unreliable as a biomarker due to
errors introduced by bisulfite sequencing, sampling techniques, and biological variability.
Definition: Phased Methylation Pattern (PMP) is a unique set of coordinates that includes
the DNA strand (‘f’ for forward (+) or ‘r’ for reverse (-)), the relative positions of three CpG
sites on the same strand (e.g., x:y:z), and their methylation status (e.g., ‘000’ for all
unmethylated or ‘111’ for all methylated). It represents a combined epigenetic signature
across these CpG sites.
Hypothesis: Phased methylation patterns (PMPs) can act as reliable biomarkers to
differentiate tissue types, providing higher specificity compared to individual CpG sites.
Dataset: The dataset (Link to Data) summarizes phased methylation patterns from NGS
results across two tissues. Key columns include:
•
Strand: Indicates the DNA strand (‘f’ or ‘r’).
Confidential and Proprietary information of Pupil Bio
1Bioinformatics coding Challenge | rev A
•
•
•
•
•
CpG Coordinates: Relative positions of three CpG sites (x:y:z).
Methylation Status: Eight possible patterns (‘000’ to ‘111’).
Sample ID: Unique identifier for each sample.
Replicate: Indicates technical replicates.
Tissue: Tissue type (Tissue #1 or Tissue #2).
Sub-tasks:
1. Coverage Analysis:
a. Calculate the median and coefficient of variation (CV) for single CpG coverage
in each tissue.
b. Generate plots summarizing the coverage statistics.
2. Biomarker Identification:
a. Identify PMPs with high specificity for tissue differentiation, minimizing false
positives for Tissue #1 while allowing some false negatives. Use statistical or
machine learning approaches to assign confidence (e.g., p-values) to each PMP
(15 points).
b. Calculate the mean variant read fraction (VRF) for each PMP in both tissues (5
points).
3. Address the following questions (20 points):
a. How does sequencing depth affect specificity confidence?
b. For the top 10 PMPs, estimate the threshold of reads required to confidently
call Tissue #2 at a sequencing depth of 1 million reads. 
c. Validate the hypothesis by comparing the specificity of the top 10 PMPs
against individual CpG sites.
______________________________________________________________________________
Task 2: NGS Data Analysis
Objective: Evaluate candidates’ ability to process and analyze raw sequencing data.
Dataset: The dataset (Link to Data) consists of NGS samples in FASTQ format, including one
sample from normal tissue and one from cancer tissue.
Sub-tasks:1 & 2 
Quality Control:
a. Perform quality checks using tools like FastQC and summarize quality
metrics (e.g., sequence counts, per-base quality, read duplication levels).
(10 points)
Alignment and Mutation Calling:
Confidential and Proprietary information of Pupil Bio
2Bioinformatics coding Challenge | rev A
a. Align the samples to the human genome using tools like Bowtie2 or BWA.
(10 points).
b. Identify somatic mutations present in the cancer sample but absent in the
normal tissue.
i. Benchmark Software: Use established tools such as Mutect2,
Strelka2, or VarScan2 for somatic mutation identification
and background mutation estimation. 
ii. Custom Code Development: Write your own scripts,
leveraging tools like Samtools, bcftools, or Python/R
libraries, to perform mutation detection and calculate the
required metrics.
c. Use the normal tissue to calculate the median background mutation level.
The background mutation level accounts for sequencing errors or biases
that can mimic true mutations. Determine how many reads per million are
required to confidently call a given mutation. 
________________________________________________________________________________________________________________________
