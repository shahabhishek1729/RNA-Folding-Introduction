# An Introduction to the Stanford Ribonanza RNA Folding Competition

For people (like myself) who don't have a biology background, understanding what this competition is really asking you to do can be a little challenging, especially since the train, test and sample submission datasets look so different. This notebook aims to help you get started with the competition, not by going through every single folder or explaining some of the details behind knot theory (for which you can check out some other excellent notebooks), but to share just what you might find helpful to dive in for yourself. If you think I left out something or would like to expand on this work, please feel free to do so. 

### Shapes of DNA and RNA
So the primary objective of this competition is to predict RNA folding, but first we need to understand the differences in the shapes of these molecules.

###### DNA
DNA is a double-stranded molecule - simply, this means that it consists of two long sequences paired together according to the following rules:

A (adenine) always pairs with T (thymine), and vice versa
C (cytosine) always pairs with G (guanine), and vice versa (NOTE: There are special cases where G and U can pair as well, but for simplicity's sake, we ignore this possibility).
So for instance, the following sequence (or strand): ATCGTAAC, is paired with the following complementary sequence (or strand): TAGCATTG.

In DNA, these two strands come together to form a tightly woven, double helix structure and this gives DNA many of its interesting properties. This is illustrated below:

![image](https://github.com/shahabhishek1729/RNA-Folding-Introduction/assets/67338646/31a036f9-ee76-4c75-9776-9dc8fd2621f0)

###### RNA
RNA, however, is single-stranded (i.e., it has only one sequence, instead of two paired sequences). This means that it is free to take on a huge number of more interesting shapes than DNA, locked in its double helix, can - it does this by folding in on itself, pairing its own bases together (according to the same rules above, except now bases can be unpaired as well. ).

For instance, consider the following sequence: AAGAGCC. We know that the a G must pair with a C, and an A must pair with a U (in RNA). However, this sequence doesn't have any U bases - therefore, the As must be unpaired in the final structure. The Gs and Cs, unfortunately, are more ambiguous. The first G could pair with the last C, the second to last C, or with nothing at all. The second G has the same three possibilities, for a total of 3 + 3 = 6 possibilities for the structure of a simple, 7-base long sequence - in our training set, examples range from 115 to 206 bases long, and in the test set, sequences can be as long as 457 bases. Clearly, listing out possibilities by hand isn't going to get us very far.

This is really the essence of the RNA folding problem - **given the raw sequence of letters of an RNA strand, can we build a model to predict the shape it will take?**

[Example](https://www.google.com/imgres?imgurl=https%3A%2F%2Fi.ytimg.com%2Fvi%2F2XTi9LG9NnU%2Fmaxresdefault.jpg&tbnid=tuc_B4XDsom_qM&vet=12ahUKEwifkdvHjsCCAxUqElkFHW3hA6sQMygQegQIARBw..i&imgrefurl=https%3A%2F%2Fnews.northwestern.edu%2Fstories%2F2021%2F01%2Fnew-videos-show-rna-as-its-never-been-seen%2F&docid=lkNT0YHFp6vi_M&w=1280&h=720&q=rna%20folded%20structure&ved=2ahUKEwifkdvHjsCCAxUqElkFHW3hA6sQMygQegQIARBw) of RNA molecule, once it has folded.

### Conclusion and Next Steps
I hope this notebook will be useful for you to really understand the crux of this competition, so that you can continue future exploration yourself and potentially find insights that change the world molecular biology! For instance, you may want to explore some of the other files and folders the competitions hosts have provided, such as the *.bpp files in the Ribonanza_bpp_files folder (where bpp stands for base-pair probabilities), as well as the puzzles in eterna_openknot_metadata, and the .fasta files in sequence_libraries. These files provide a wealth of information that could be invaluable during model training. It might also be worth looking at open-source models that have already been built for similar or related tasks (e.g. AlphaFold-v2 for protein folding) and attempting to fine-tune those to fit this dataset. You may also want to consider building your own baseline model from scratch (for which various starter notebooks are available on Kaggle). There are no limits to where you can go with this competition so have fun and happy coding!
