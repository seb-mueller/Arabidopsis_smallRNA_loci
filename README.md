# Arbidopsis_smallRNA_loci

## Publication

Thomas J. Hardcastle, Sebastian Y. Müller & David C. Baulcombe *Scientific Reports* volume 8, Article number: 6338 (**2018**)
https://www.nature.com/articles/s41598-018-24515-8

## Public data

https://www.ebi.ac.uk/ena/data/view/PRJEB22276

## Additional material for small RNA loci project

GFF file contains all annotation used to class sRNA-loci in Arabidopsis.
The 9 cluster described in the paper are saved as *cluster*.
See below an example R snippet to access:

```r
library(rtracklayer)
loci <- import.gff3(file.path("lociV_gr9.gff3"))

length(loci)
# [1] 24559

head(loci[,c("ID", "cluster")])
# GRanges object with 6 ranges and 2 metadata columns:
#       seqnames         ranges strand |          ID     cluster
#          <Rle>      <IRanges>  <Rle> | <character> <character>
#   [1]        1 [  690,  1022]      * |  ATSL000010           5
#   [2]        1 [ 1023,  1070]      * |  ATSL000020           4
#   [3]        1 [ 8629,  8700]      * |  ATSL000040           3
#   [4]        1 [11911, 11933]      * |  ATSL000050           1
#   [5]        1 [13006, 13043]      * |  ATSL000060           1
#   [6]        1 [16957, 17154]      * |  ATSL000070           7
#   -------
#   seqinfo: 5 sequences from an unspecified genome; no seqlengths
table(loci$cluster)
#
#    1    2    3    4    5    6    7    8    9
# 5242 2808 2196 1788 4787 2898 2240 1259 1341

```
