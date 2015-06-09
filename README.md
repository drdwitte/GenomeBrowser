# GenomeBrowser (part 1: Genome Crunching with Apache Pig in Cloudera VM)

**1)** K-mer frequency distribution per genome

	A) Generate Kmer distributions for k=1 -> 7 for a 4 monocot genomes

**2)**
    	A) Filter a motif database for C,F,T + project out relevant columns	

    	B) Select the top 100 motifs under different scores: 1) F 2) F*C 3) best FC per motif length 4) best FC per motif length/degeneracy (degeneracy requires writing a EvalFunc UDF in Pig, NOTE give pom.xml to facilitate packaging and explain how to use UDF: register hdfs:///path/to/name.jar; DEFINE alias path/in/jar/to/class; )	

	C) Write a UDF that returns a bag of matching positions for every sequence, motif pair (BLS95 => all species)

    	D) For the set of best motifs in B4) 100 per class: calculate the matching positions on a certain gene family

	E) Make a histogram aggregation of enriched areas in a gene family (will be used in next lab)

# GenomeBrowser (part 2: Creating a genome browser in D3.js)

**1)**
	A) Design a histogram visualization of the histogram aggregations in part 1

	B) Add a slider and a + and - button to zoom

	C) If you click on positions in the histogram the character at this position should be visualized

	D) If you select positions show a frequency matrix (PWM on wikipedia: stacked bar seems most sensible)

	E) For consecutive positions show pads between the stacked bar charts to reveal position dependencies

**2)**	Scatter visualization enrichment difference between species

	A) each motif results in a dot: #occurrences in maize #occurrences in rice

	B) add horizontal and vertical grid lines (interactive) per point with each time the green fraction showing the number of GF the motif is enrichted => FPR	


