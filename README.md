# <b>Visualize Protein Sequences Using Chaos Game Representation</b>
Protein CGR image generator.ipynb can be used to generate visualizations of protein sequences by using a modified chaos game representation.<br>
<br>
Chaos game representation is an iterated function over an amino acid sequence an drawing a new a point for each element. The position of this point is a a distance between the previous point and the corresponding amino acid vertex.<br>
I encourage reading of "Chaos game representation of gene structure" by H.Joel Jeffrey for an in-depth explanation of the algorithm.<br><br>
To apply this to proteins, which are too noisy for conventonal CGR, I use a dynamic step size such that the distance between two sucessive points is dependent on amino acid similarity.
This provides structure to the resultant image.

Example visualization of <i>H.s.</i> µ-opioid receptor compared to <i>R.n.</i>  µ-opioid receptor and <i> H.s.</i> p53
![examples](https://github.com/WillCheney/Protein-CGR/blob/master/Protein%20CGR%20example-01.png)
We can see that visualizations between the closely related µ-opioid receptors are very similar and both are distinct from outgroup protein p53


Whats handy about these visualizations is that we can leverage deep learning's image recognition tools.<br><br>
I've implemented two Convolutional neural networks, using LeNet Architecture, for image classification:<br>
(1) classify proteins into four families: Type A GPCR, Helicase, Major Facilitator Superfamily and AMP binding. This achieves 97%/92% train/test accuracy<br>
(2) classify if missense mutation in tumor supression p53 are functional or non-functional. This achieves 95%/87% train/test accuracy
