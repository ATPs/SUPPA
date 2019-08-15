# understanding PSI

https://bioinformatics.mdanderson.org/public-software/spliceseq/methods/

Next, the gene splice graph statistics are evaluated by a splice event detection module, which identifies and characterizes splice events. It identifies splice events such as alternate acceptor sites (AA), alternate donor sites (AD), alternate promoters (AP), alternate terminators (AT), exon skipping (ES), mutually exclusive exons (ME), and retained introns (RI) by analyzing the structure of the splice graph, looking for regions of the splice graph that can be traversed in multiple ways. The diagram below illustrates each event as represented within the splice graph.

For the purposes of quantifying the event, we have arbitrarily labelled two types of paths for each event, one type being ‘inclusive’, meaning that a certain exon would be included if the path was traversed; and the other type being ‘exclusive’, meaning that a certain exon would be excluded if the path was traversed. In the diagram above, the inclusive path of each event type is colored in purple while the exclusive path(s) is colored in green.

![PSI](500px-SpliceSeqV2Methods_06.png)

For each event detected in a given sample, a value called called Percent-Spliced-In (PSI) is calculated for the event, which measures the proportion of reads falling on the ‘inclusive path’ as normalized by length. The actual formula is:

PSI = Inclusive reads / (inclusive reads + exclusive reads)

For instance, a PSI of 0.5 for an exon skip event would mean that the exon is included in half of the expressed isoforms, and a PSI of 0 would mean that the exon is never included in any of the transcripts.
