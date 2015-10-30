#Calculate Reference Mappability

To calculate reference mappability.

##hg38 50mers
```
gem-indexer -i hg38.fa -o hg38
gem-mappability -I hg38.gem -l 50 -o hg38.50mer -T 8
gem-2-wig -I hg38.gem -i hg38.50mer.mappability -o hg38.50mer
wigToBigWig hg38.50mer.wig hg38.50mer.sizes hg38.50mer.bw
bigWigToBedGraph hg38.50mer.bw  hg38.50mer.bedGraph
bedGraphTobed hg38.50mer.bedGraph hg38.50mer.Excludable.bed 0.33 hg38.fa hg38.Excludable.Delly.bed
```

##GRCh37 25mers
```
gem-indexer -i human_g1k_v37.fasta -o human_g1k_v37
gem-mappability -I human_g1k_v37.gem -l 25 -o human_g1k_v37.25mer -T 8
gem-2-wig -I human_g1k_v37.gem -i human_g1k_v37.25mer.mappability -o human_g1k_v37.25mer
wigToBigWig human_g1k_v37.25mer.wig human_g1k_v37.25mer.sizes human_g1k_v37.25mer.bw
bigWigToBedGraph bigWigToBedGraph human_g1k_v37.25mer.bw  human_g1k_v37.25mer.bedGraph
bedGraphTobed human_g1k_v37.25mer.bedGraph human_g1k_v37.25mer.Excludable.bed 0.33 human_g1k_v37.fa human_g1k_v37.25mer.Excludable.Delly.bed
<<<<<<< HEAD

=======
>>>>>>> b0eef0fbf64ed6099ec5a38243e883b9650aa946
```
