# PC3old-CNV

gatk PreprocessIntervals -R /projects/verhaak-lab/GLASS-NF/references/GRCh37/Homo_sapiens_assembly19.fasta --bin-length 1000 --padding 0  -O preprocessed_intervals.interval_list
##collectreadcounts
 gatk CollectReadCounts -I /projects/verhaak-lab/Eunhee_WGS/PC3oldWGS/BAM/PC3-NCI60-DM.realn.mdup.bqsr.bam -L  /projects/verhaak-lab/Eunhee_WGS/PC3oldWGS/BAM/preprocessed_intervals.interval_list --interval-merging-rule OVERLAPPING_ONLY -O PC3NCIold.counts.hdf5
          
gatk CollectReadCounts -I /projects/verhaak-lab/Eunhee_WGS/PC3oldWGS/WGS/PC3-NCI60-DM.realn.mdup.bqsr.bam -L projects/verhaak-lab/Eunhee_WGS/PC3oldWGS/WGS/Preprocessed.interval_list --interval-merging-rule OVERLAPPING_ONLY -O PC3NCI.counts.hdf5
