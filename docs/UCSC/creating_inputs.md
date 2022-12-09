## Generating Inputs
In order to use the genomic broswer features, sample files must be created.

### Individual sample files
For individual samples, where peak density is to be observed, bigwig formatted files must be generated. If using the CCBR/CARLISLE pipeline these are automatically generated as outputs of the pipeline (WORKDIR/results/bigwig). If not using this pipeline, example code is provided below for the file generation.
```
```

### Contrasts between samples
For contrasts, where peak differences are to be observed, bigbed formatted files must be generated. If using the CCBR/CARLISLE pipeline these are automatically generated as outputs of the pipeline (WORKDIR/results/peaks/contrasts/contrast_id/). If not using this pipeline, example code is provided below for the file generation.
```
```

## Sharing data
For all sample types, data must be stored on a shared directory. It is recommended that symlnks be created from the source location to this shared directory to ensure that minial disc space is being used. Example code for creating symlinks is provided below.

### single sample
```
# single sample
## set source file location
source_loc="/WORKDIR/results/bigwig/sample1.bigwig "

## set destination link location
link_loc="/SHAREDDIR/bigwig/sample1.bigwig"

## create hard links
ln $source_loc $link_loc
```

### contrast sample
```
# contrast
## set source file location
source_loc="WORKDIR/results/peaks/contrasts/sample1_vs_sample2/sample1_vs_sample2_fragmentsbased_diffresults.bigbed "

## set destination link location
link_loc="/SHAREDDIR/bigbed/sample1_vs_sample2.bigbed"

## create hard links
ln $source_loc $link_loc
```

Once the links have been generated, the data folder must be open to read and write access. 
```
## set destination link location
link_loc="/SHAREDDIR/bigbed/"

# open dir
chmod -R 777 $link_loc
```