# **Trinity-Denovo-transcriptome-assembly**
Denove assembly and Annotation


- ### Install Trinity from conda

conda install -c bioconda trinity 


- ### Create an environment to run trinity there

conda create -n trinity

- ### Look at the header of your fastq file. You may need to modify it in order to run this version of trinity

_Use this code to modify your fastq file_

zcat Sample_name.trim.fastq.gz | awk '{{print (NR%4 == 1) ? "@1_" ++i "/2": $0}}' | gzip -c > Sample_name.trinity.fastq.gz &

 #### _pls note- your file name musr consists of word trinity in it._

- ### For single end reads-

nohup Trinity --seqType fq --max_memory 300G  --single Sample_name.trinity.fastq.gz  --CPU 48 --output Sample_name_trinity_result > sample_name.out &


_This will run in three step and generate a final trinity.fasta. file._



