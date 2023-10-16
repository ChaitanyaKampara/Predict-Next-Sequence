# Predict-Next-Sequence
PREDICTING NEXT SEQUENCE:

1.) IMPORTING LIBRARIES :-
    
    * NUMPY      :  CONSISTS MULTI DIMENTIONAL ARRAYS USED FOR MATHEMATICAL,LOGICAL OPERATORS
    * PANDAS     :  USED FOR MANPULATING DATA
    * MATPLOTLIB :  PLOTTING , EXTENTION OF NUMpy PROVIDES API FOR EMBEDDING PLOTS INTO GUI(TKINTER OR GTK)
    * SEABORN    :  FOR VISUALIZATION HAS BETTER "COLOR PALETTE" AND MORE VARITY OF GRAPHS
    * TENSORFLOW :  LIKE SKLEARN IN ML : TENORFLOW IN DL

2.) DATASET :
     
    * CREATE YOUR OWN DATASET

3.) FUNCTION splitSequence(seq, n_steps):
 
    * 1st CRAETE EMPTY LIST OF X,Y
    * NEVER => "lastIndex > len(seq) - 1:"  (  lastIndex = i + n_steps )
    * CREATE SEQ FOR i/p , o/p => [0,...,X-1] , [X]
    * APPEND THIS SEQ i/p , o/p to X,Y ( EMPTY LIST )
    * CONVERT INTO "ARRAY" (USE NUMPY)

4.) n_steps = 7 MEANS MY COLUMNS ARE => 7

     * X => 7 COLUMNS ( [0,...,X-1] )
     * Y => 1 COLUMN  ( [X] )

5.)  Creating the model:
     * Adding an LSTM layer to the model
     * TIMESTEP :  It means that at each time step , the LSTM unit takes in the data from that specific point in the sequence and updates its state based on the current input and its previous state.
 
     * (1)layers: 1.)   This is an import statement for Keras layers. 
                  2.)   Keras provides various layers for building neural networks, and "LSTM" is one of them.

     * (2)50  :        No of LSTM neurons in this layer.
     *(3)n_steps :    No of time steps in the sequence 
     *ex         :    if n_steps= 3 => This means you'd create input sequences like [10, 20, 30], [20, 30, 40], [30, 40, 50],........
     *(4)n_features : No of features at each time step.
     *ex         :    Numerical 1 feature only

     *layers.Dense(1) :  o/p contains 1 neuron

6.) MODEL COMPILATION :
 
     * optimizers = adjusts model's parameters optimizer's job is to minimize this loss function tunes the model to make it better at its task.

7.) MODEL EVALUTION :

     * X_train,y_train : training data
     * batch_size=64   : number of samples in each batch , update its weights after processing 64 training examples at a time.
     * epochs =100     : 1 fp + 1 bp ,  model will see training data 100 times during training.
     * validation_data : test data
     * verbose : 1 ( used to see information when epochs are getting trained )
