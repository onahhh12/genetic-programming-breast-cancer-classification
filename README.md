Genetic Programming Breast Cancer Classification
Overview

This project implements two Genetic Programming (GP) approaches for classifying the Breast Cancer Wisconsin (Diagnostic) Dataset:

Symbolic / Arithmetic GP Classifier — evolves mathematical expressions using arithmetic operators.
Logical / Decision Tree GP Classifier — evolves decision trees for classification.

The main objective is to compare the classification performance of the two GP approaches using training accuracy, test accuracy, F-measure, runtime, and statistical significance testing.

Project Objectives

The system is designed to:

Evolve classification models using Genetic Programming.
Compare an arithmetic-expression-based classifier with an evolved decision-tree classifier.
Evaluate the models on unseen test data.
Perform multiple independent runs using different random seeds.
Record and compare the best-performing models.
Provide reproducible results through explicit seed values.

The project requires 30 independent runs for each algorithm, with every run using a unique seed.

Algorithms
1. Arithmetic GP Classifier
The symbolic GP approach evolves arithmetic expressions that are used to classify instances.
The GP population consists of individuals represented as expression trees. Through selection, crossover, and mutation, increasingly effective expressions are evolved according to classification accuracy.

2. Decision Tree GP Classifier
The logical GP approach evolves decision trees where internal nodes represent logical/conditional decisions and terminal nodes represent classification outcomes.
The evolved tree is used to classify previously unseen instances.

The project requires both an arithmetic classifier and a decision-tree classifier.

Dataset

The project uses the Breast Cancer Wisconsin (Diagnostic) Dataset.

The target class is represented as:

Class	Encoding
no-recurrence-events	0
recurrence-events	1

Several categorical attributes are encoded numerically, including age, menopause, breast side, quadrant, node caps, and irradiation status.

Genetic Programming Configuration

The GP algorithms use the following core configuration:

Parameter	Value
Population Size	200
Initial Tree Generation	Ramped Half-and-Half
Initial Tree Depth	Design Decision
Maximum Offspring Depth	Design Decision
Selection Method	Design Decision
Tournament Size	Design Decision
Function Set	Design Decision
Crossover Rate	Design Decision
Mutation Rate	Design Decision
Mutation Type	Point Mutation
Mutation Offspring Depth	Design Decision
Fitness Function	Accuracy
Maximum Generations	100

The parameters marked as design decisions were selected as part of the implementation and experimentation process.

Running the Program

The program requires the user to provide:

A random seed.
The relevant dataset filepath.
Any additional parameters required by the implementation.

This allows experiments to be reproduced using the same configuration and seed.

Arithmetic GP
java -jar arithmetic-gp.jar

Example:

Enter seed: 12345
Enter training dataset path: data/train.csv
Enter test dataset path: data/test.csv
Decision Tree GP
java -jar decision-tree-gp.jar

Example:

Enter seed: 12345
Enter training dataset path: data/train.csv
Enter test dataset path: data/test.csv

Replace the JAR names above with the actual generated JAR filenames in the repository.

Training Demonstration

During training, the program displays the best individual and its corresponding metrics for each generation.

Example:

Generation: 1
Best Individual: ...
Training Accuracy: ...

Generation: 2
Best Individual: ...
Training Accuracy: ...

...

Generation: 100
Best Individual: ...
Training Accuracy: ...

The assignment requires the training demonstration to display the best evolved individual and its metrics at each generation.

Testing / Classification

After training, the best evolved model can be evaluated against the unseen test dataset.

The testing phase loads the test file and classifies each instance using the best pre-trained/evolved model.

The following metrics are reported:

Training Accuracy
Test Accuracy
F-measure
Runtime

Report

The accompanying report contains:

Model design
Data preprocessing
Genetic Programming configuration
Experimental methodology
Results from the independent runs
Comparison of both GP approaches
Statistical significance analysis
Final conclusions
