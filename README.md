# Prepare-and-measure-and-Entanglement-simulation-beyond-qubits
The code needed to run the numerical simulations of the paper titled by: Prepare-and-measure and Entanglement simulation beyond qubits

1- The same name is chosen for the classical resources, for different dimensions. When the download is finished, the appropriate classical resource for that specific dimension is put into the variable that the protocol uses.
2- if one needs, it is possible to produce the randomized classical resources within the code.
3- The functions AutCalcpm[count_, n_, N_, div_] ; AutCalcent[count_, n_, N_, div_] , and AutCalcpmPAR[n_, N_, div_] are the automated functions that run all the protocols, for the PM-scenario, entanglement scenario (Both the randomized and CGLMP cases), and Phi-Parameterized cases, respectively.
4- For the CGLMP setup, one has to manually run the AutCalcent, by setting the variables States = StatePA[I] and Meas = StatePB[j] for I and j being 1, and 2, and running it for all four possible pairs (i.j).
5- In AutCalcPM and AutCalent, the count, is the counter of choosing from the set of randomized inputs data, which is loaded to the variables: RandomizedStates and RandomPVM, for each dimension. For PM-Scenario, the counter starts from 1. For the entanglement scenario it starts from 1001 in the data set. The full data set contains 3000 inputs, for each dimension.Notcie that for the PM-scenario, the state given to Alice is set to be the first element in each RandomizedStates[[I]] , which contains the full basis. For the entanglement scenario, all three is given to Alice.
6- n, is the number of indexes one ones to go forward from the variable count: For example, count =1 , n = 5 means, the protocols will be run for the inputs indexed by 1, 2, 3, 4, and 5.
7- N is the number of inputs, corresponding to N_ini in the paper.
8- div divides the iterations into bulks to help the computational efficiency by applying the calculations in modules of inputs. It is by default set to 10.
9- for the Phi-Parameterized case, AutCalcpmPAR, initiates the code by giving Alice the random state, indexed by 2001, and constructing the Bob’s inputs from it as is explained in the paper.
10- in AutCalcpmPAR[n_,N_,div_] n sets the number of points between the range of the variable phi. In our work, it is set to 11. One can choose it manually to be deferent.
11- The outputs of all the functions, has the form of a list of 6 different TVD’s corresponding to P1, PMON-1, PMON-2A, PMON-2B, PRUD-1 and PRUD-2. At the end of the evaluation, a list of scaled errors, and the number of outputs, per each protocol is reported.
12- All the necessary functions for the code to run are defined before the definition of the above-mentioned functions. Therefore the code should be run successively from above.
13- Inside the functions, the inputs of the protocols are set such that the number of outputs become statistically comparable for a fair judgement of their TVD.
14- For PMON-2B in d=2. One should use the functions defined in the section: PMON-2B-d=2. For d=3,4, the appropriate functions are defined in section PMON-2B-d=3,4.
15- for checking the threshold delta, the code iterates from the first 20 inputs that used for the PM-scenario.
16- In the code, the protocol PMON-2A is labled as PMON-B1.
17- In the code, the protocol PMON-1 is labeld as PMON-A1.
