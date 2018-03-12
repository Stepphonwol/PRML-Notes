### 1.3
- **validation set** : an independent data set used to evaluate different approaches;when over-fitting occurs, turn to **test set** for help (when training data is plentiful, only some part of it is used)
- **cross-validation**: the whole data set is partitioned into S parts. In each run, choose one part as the held-out group to evaluate the performance of using the remaining (S-1)/S of the data set as the training group. This process is repeated S times for all S possible choices for held-out group(*leave-one-out technique*)
    - *major drawback of cross-validation* : the number of training runs is increased by a factor of S and the training process itself could be computationally expensive. And multiple parameters for a single model might require an exponential number of training runs according to the number of parameters.
- A method which only depends on the training data and does not suffer from bias (*fully bayesian approach*)