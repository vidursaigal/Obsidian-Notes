https://www.youtube.com/watch?v=k9VFNLLQP8c

Single Cell Sequencing allows you to get specificity on the type of cell (B-cells, T-cells, macrophages etc.). This is in contrast to bulk sequencing. 

After you get the sequence, you can see up to 20,000 genes that are in the human genome.
	Thus, dimensionality reduction collapses this down into two-dimensions. (UMAP)
		After dimensionality reduction, you can cluster to see different cell-types. 
			The same information could be obtained with flow cytometry. However, this allows you to see all of the genes in each cluster, instead of just flow markers. 

You can cluster within each cluster to get better specificity to find more specific gene expression. 

Original Techniques: 
Plate-based SMART-seq - Use flow to sort one cell into each well of 96-well. Lyse the cell and then do a reverse transcription reaction. You end up with cDNA with PCR handles on both ends. This undergoes amplification.

Able to process a few hundred to max a few thousand cells. Also, very expensive. 

New Techniques:
DropSeq - Uses microfluidics, very small droplets. Uses oil and emulsion to make droplets. One bead and one cell in each of the droplets. Each bead has many barcoded oligo-dTs, which allows it to capture the cell's RNA. It also has a unique identification barcode. Do a reverse transcription reaction on each of the beads. Then amplify with PCR. 

Problem with this method is that only a small fraction of droplets contained one bead and one cell (2%).

Can sequence thousands, tens of thousands of cells. 

10x Genomics - very similar to dropseq except 90% of droplets had only one bead. Additionally, reverse transcription happened within the droplets. Can sequence up to 25,000 cells in each of the lanes of the chip. Each chip has 8 lanes on it. 

Microwells - BD Rhapsody!, very small wells that cells fall into, then lyse and do the needed reactions

Combinatorial Indexing - in situ, many cells in each well barcoded multiple times

CITE-seq






