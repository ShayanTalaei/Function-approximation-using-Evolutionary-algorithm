# Function-approximation-using-Evolutionary-algorithm
### This repository contains the code for the course project on Artificial Intelligence at SUT.


### It is the implementation of an evolutionary algorithm (EA) for approximating a mathematical function. The individuals in the population are tree-structured calculators.

#### Nodes

Each individual is a rooted tree that takes a multi-dimensional input like $X \in \mathcal{R}^d$ and computes its target function in a bottom-up fashion from its leaf. Each node in a tree is a subclass of either *Unary* or *Binary* node class. Below there is a description of Node's classes inheritance. 

Node: It is an abstract class identifying the main functionalities of each node, namely *evaluate*, *get_written_form*, *get_sub_nodes*, and *get_children*.

Unary: Is is a child of *Node* class, having the implementation of unary nodes other than their *evaluate* method. The unary nodes defined for this project are *Const* (a constant value), *Param* (an element of the input X), *Sin*, and *Cos*.

Binary: Is is a child of *Node* class, having the implementation of binary nodes other than their *evaluate* method. The uniary nodes defined for this project are *Add*, *Sub*, *Mul*, *Div*, and *Pow* $(a^b)$.

#### Trees

Different computation tree structures can be built using these building blocks. There are two different structures in this project, *XPolyTree* and *ComplexTree*, with their mutation and breed protocols.

#### Data sets

For creating the data sets, there is a *Dataset* class which takes *sample* count, a *function*, the *input dimension*, and the sampling *interval* and makes a data set with these parameters accordingly.

#### Evolution protocol

There is an *EvolutionaryTrainer* class for managing the evolution protocol abstractly; it is not for a particular tree type. It takes a *dataset*, the initial *population*, and the *mutate* and *breed* functions of the corresponding population.
It has a *loss* function for evaluating a tree on the dataset and uses this to make the *selection* process. After selecting the next generation's parents, it does the *cross_over* followed by the *mutation* to make the next generation. Repeating this process in the *evolute* function starts from the initial population and reaches a population with a much higher performance on the given task.

A series of tests and results are provided in the Doc.pdf file and the Function_Approximation.ipynb.
