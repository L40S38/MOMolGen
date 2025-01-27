# MOMolGen

TODO: add some introduction words

## Requirements
1. [Python](https://www.anaconda.com/download/)==3.7, some errors show up in newer version of python.
2. [Keras](https://github.com/fchollet/keras) (version 2.0.5) If you installed the newest version of keras, some errors will show up. Please change it back to keras 2.0.5 by pip install keras==2.0.5. 
3. tensoflow-gpu (version 1.15.2, ver>=2.0 occurred error.) 
4. [rdkit](https://anaconda.org/rdkit/rdkit)
5. [rDock](http://rdock.sourceforge.net/installation/)
6. [Autodock Vina](https://vina.scripps.edu/) Make sure to add Vina into system path.
7. [Open Babel](http://openbabel.org/wiki/Category:Installation) Make sure to add OpenBabel into system path.

## How to Use

#### Train the RNN model

1. cd train_RNN
2. Run python train_RNN.py to train the RNN model.

#### Molecule generate

1. cd ligand_design
2. Run python mcts_ligand.py

Although MOMCTS-MolGen has an extendable objective set, the default setting of objectives is docking score, QED score, logP, and a filter on SA score.

To modify your own objective set, change simulation functions in add_node_type.py, and change reward functions in mcts_ligand.py. (it may integrate into one function in future work)

If the size of the objective set is not 3, don't forget to change 'default_reward' in mcts_ligand.py.

Outputs of ligand_design process will store in data/present/, including:
```
output.txt             ## output of pareto front change
ligands.txt            ## ligands pass SA score filter.
scores.txt             ## raw scores of ligands
hverror_output.txt     ## output of hypervolume calculation errors
error_output.txt       ## output of vina and obabel errors
```

## License
This package is distributed under the MIT License.
