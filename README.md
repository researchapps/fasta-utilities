# Fasta Utilities

This is a Singularity build file for the [fasta-utilities](https://github.com/jimhester/fasta_utilities) library.


## 1. Install Singularity

Instructions can be found on the [singularity site](https://singularityware.github.io).


## 2. Download this repo

    git clone https://www.github.com/singularituhub/fasta-utilities
    cd fasta-utilities


## 3. Bootstrap the image


    sudo singularity create fasta-utils.img
    sudo singularity bootstrap fasta-utils.img Singularity


## 4. Run commands

What commands are in bin?

       $ ./fasta-utils.img ls
	2big.pl			 fetch_entrez.pl	  pairs_unsorted.pl
	CpG_count.pl		 fetch_gi.pl		  percent_GC.pl
	absolute_coordinates.pl  fetch_sra.pl		  regex_fasta.pl
	add_type.pl		 filter_align.pl	  remap_file.pl
	align_progress.pl	 filter_bam.pl		  remove_ambiguous.pl
	ascii2csv.pl		 filter_reads.pl	  rename_script.pl
	avg_coverage.pl		 fix_headers.pl		  reverse_complement.pl
	bed2fasta.pl		 generate_fasta.pl	  sam2fastq.pl
	bed2igv.pl		 generate_map.pl	  sam_lengths.pl
	bisulfite_convert.pl	 get_fasta.pl		  sequence_counts.pl
	blast_information.pl	 gff2bed.pl		  size.pl
	calcN.pl		 gff2data_frame.pl	  size_select.pl
	collapse_duplicates.pl	 grep.pl		  sort.pl
	combine_bed.pl		 in_list.pl		  splice.pl
	commify.pl		 lengths.pl		  split_fasta.pl
	consensus.pl		 maf2bed.pl		  standardize_names.pl
	distances.pl		 mate_pair2paired_end.pl  subset_fasta.pl
	fasta2fastq.pl		 merge_records.pl	  trans_fasta.pl
	fasta_head.pl		 mpileup_consensus.pl	  trim_fasta.pl
	fasta_tail.pl		 mpileup_counts.pl	  unique_headers.pl
	fastq2fasta.pl		 pairs_sorted.pl	  wrap.pl


Run a command


       ./fasta-utils.img perl add_type.pl


Mount the data directory

      
      singularity run -b /path/to/data:/data/ fasta-utils.img


To specify inputs and outputs, and run with data (not tested)


      singularity run -b /path/to/data:/data/ fasta-utils.img perl in_list.pl [args]



Shell into a (writable) container to test changes (that you should then add to the build file [Singularity](Singularity).


      sudo singularity shell --writable fasta-utils.img
