## File Formats

The similar property principle suggests that often, if two chemical structures are similar, they will also exhibit a number of similarities in their properties. However, although this heuristic holds true in many examples, it is also observed that highly similar chemical structures have significantly differences in properties, particularly in biological activity, a phenomenon known as **Activity Cliffs.**

There exist many molecular descriptors in the literature that are used to rapidly generate molecular similarities, which can be simply classified into **property descriptors, topology descriptors (those generated from molecular connectivity alone), and topographical descriptors (those that are generated from the geometric shapes of molecular structures).*** 


1. [Slides](https://www.slideshare.net/abhikseal/chemical-file-formats)
2. [Mol File format](https://chem.libretexts.org/Courses/University_of_Arkansas_Little_Rock/ChemInformatics_(2017)%3A_Chem_4399_5399/2.2%3A_Chemical_Representations_on_Computer%3A_Part_II/2.2.2%3A_Anatomy_of_a_MOL_file)


#### Molecular Property Descriptors
The property descriptors, or modelled properties that indicate some reliable prediction of a physicochemical property, such as molecular weight or the octanol-water partition coefficient (ClogP). One such set of property descriptors that has gained wide acceptance is the Lipinski rule-of-five, which has been suggested as an heuristic for indicating the oral absorption of a potential drug based on marketed orally-dosed drugs.
The rule-of-five applies four calculated properties and defined cut-offs, each of which is a multiple of five. The four properties and their cut-off ranges are:
1. Molecular Weight (MW or MWt) less than 500 daltons; 
2. Predicted octanol-water partition coefficient (ClogP) less than five;
3. Fewer than five hydrogen bond donors (HBD = total number of nitrogen-hydrogen and oxygen-hydrogen bonds); and 
4. Fewer than ten hydrogen bond acceptors (HBA = total number of all nitrogen and oxygen atoms).

#### Topological Descriptors
Derieved directly from 2D molecular structure (connection tabel representation of structure aka how atoms are connected). Two types of molecular descriptor are often used, molecular indices and
molecular fingerprints.

Molecular Indices: Use distance matrix based on Wiener index.
Read more from [Chemical descriptors and molecular graphs](https://www.slideserve.com/raleigh/chemical-descriptors-and-molecular-graphs)

A canonical form is a completely unique representation within a system. For example, “diethyl ketone” and “3- pentanone” are both unambiguous names: each represents one and only one compound. However, since they represent the same compound, they are not unique names. Within the system of Preferred IUPAC Names (see below), “3-pentanone” is a canonical name – an unambiguous and unique representation of this compound.


