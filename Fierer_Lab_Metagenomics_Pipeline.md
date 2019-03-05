
# Metagenomics Pipeline

Created 2019-01-14: Hannah Holland-Moritz

Updated 2019-01-14: Hannah Holland-Moritz

A note about running these scripts: 

Since many of these scripts take a long time to run, and may benefit from the use of the server's job scheduler, we have added asterisks where we recommend scripts be submitted to the job scheduler. 

### Samples we plan to test the pipeline on:
- Showerhead (2) - high coverage
- Panama (2) - low depth
- Tess CZO (2) - medium coverage
	* Calhun 60-70
	* Shale hills 90-100

## Step 0: Demultiplexing and Quality Filtering

First demultiplex the reads and quality-filter them with `sickle`.

Sickle: https://github.com/najoshi/sickle

Notes: Need a demultiplexing script. 

### Step 0a: Demultiplexing


```python
prep_fastq_for_uparse_paired.py -i /data/shared/metagenomics_tutorial/seqs_fw.fastq.gz -r /data/shared/metagenomics_tutorial/seqs_rv.fastq.gz -b /data/shared/2014_02_03_data_tutorial/Undetermined_S0_L001_I1_001_t.fastq.gz -m Demo_MappingFile.txt -o demultiplexed_seqs/
```

### Step 0b: Look at sequence quality with fastqc


```python
fastqc seqfile1 seqfile2 .. seqfileN -o qual_check
```

### Step 0c: Quality filter with sickle


```python
# for illumina nextseq reads; quality score 20; length >50
sickle pe -i infile -t sanger -o outfile -q 20 -l 50
```

# Assembly-free taxonomic characterization

For assembly-free taxonomic characterization of shotgun-sequencing samples, you can use `metaxa2`. 

## Metaxa2: 16S - Fragment identification


```python
# Jon's script goes here
```

## Emirge: Full-length 16S rRNA gene assembly (optional)


```python
# emirge pipeline here
```

# Creating MAGs

To create Metagenome Assembled Genomes (MAGs), follow the pipeline below. 

## Step 1: Assembling Contigs


```python
# MegaHit Assembly Goes here
```


```python
# metaSpades assembly goes here
```

## Step 2: Mapping Reads

After assembling, map reads to assembled contigs and check the quality of the assemblies. 

*Add notes/guidelines about assembly quality; mention quast?*

WARNING: This step will take a long time.


```python
# Bowtie mapping goes here
```

## Step 3: Binning Contigs

Once satisfied with your assemblies, bin contigs.


```python
# CONCOCT goes here [still needs to be installed]
```


```python
# MetaBAT goes here
```


```python
# Maxbin goes here
```


```python
# DAS_TOOL goes here [still needs to be installed]
```

## Step 4: Bin ID/Quality Checking

Check the quality of your bins and identify them taxonomically. Use CheckM, GTDB and Anvio to do this.


```python
# CheckM goes here
```


```python
# GTDB goes here [methodology needs to be figured out]
```


```python
# Anvio - check final binning in Anvio - Do you trust it?

# Perhaps this should be a link to anvio tutorials? or a link to another mini tutorial?
```

## Step 5: Gene Annotation

Annotation of genes can happen two ways. The quick 'n dirty way (prokka) and the slow, but more in-depth way (online databases). 


```python
# prokka instructions here
```


```python
# IMG guidelines; 
# - Prepare files for upload
# - link to sequence submission guidelines
```
