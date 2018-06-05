# Extract portions of bigwig data from a bigwig file
## General Workflow
1. generate the chrom.size file based on the genome fasta
2. use bigWigToBedGraph to extract portions of bigwig data(bedGraph format output)
3. merge all the bedGraph files
4. sort the merged bedGraph file
5. use bedGraphToBigWig to convert bedGraph file to bigWig format

## Requirements
* Linux
* Python
* bigwigToBedGraph and bedGraphToBigwig from UCSC, see http://hgdownload.cse.ucsc.edu/admin/exe/

## Usage
### help and usage messages
```shell
usage: bigwig_extract.py [-h] -in_b INPUT_BIGWIG -regions REGIONS [-f FASTA]
                         -out_b OUTPUT_BIGWIG [-v]

Extract the specified regions from the bigwig file.

Quick start:
bigwig_extract.py -in_b input.bigwig -regions region.txt -f genome.fasta -out_b output.bigwig

optional arguments:
  -h, --help            show this help message and exit
  -in_b INPUT_BIGWIG, --input_bigwig INPUT_BIGWIG
                        Input Bigwig file
  -regions REGIONS, --regions REGIONS
                        Input a file that contain the list of the specified
                        regions. Regions can be specified as:
                        RNAME[:STARTPOS[-ENDPOS]]
  -f FASTA, --fasta FASTA
                        The genome fasta
  -out_b OUTPUT_BIGWIG, --output_bigwig OUTPUT_BIGWIG
                        Output Bigwig file
  -v, --version         show program's version number and exit
```
### Quick start
`bigwig_extract.py -in_b input.bigwig -regions region.txt -f genome.fasta -out_b output.bigwig`

### Example region.txt
```shell
Scaffold1:50
Scaffold2:60-3000
Scaffold3
```
