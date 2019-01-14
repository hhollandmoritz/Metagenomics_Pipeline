
# Metagenomics Pipeline

Updated 1/14/19

## Step 0: Demultiplexing and Quality Filtering

First demultiplex the reads and quality-filter them with `sickle`.

Sickle: https://github.com/najoshi/sickle

Notes: Need a demultiplexing script. 


```python
# for illumina nextseq reads; quality score 20; length >50
sickle pe -i -t sanger -o -q 20 -l 50
```


      File "<ipython-input-1-d51c2711e906>", line 2
        sickle pe -i -t sanger -o -q 20 -l 50
                ^
    SyntaxError: invalid syntax



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
