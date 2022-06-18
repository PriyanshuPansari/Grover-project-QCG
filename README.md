# Solving Boolean SAT Problem using Grover’s Algorithm

## Problem Statement
Frank wants to throw a dinner party to celebrate Alice and Bob’s engagement. He is also considering inviting their mutual friends Charles, Dave and Eve. However, he is aware that Charles will come to the party only if Dave comes without Eve. Frank wants to know what possible combinations of invitations he can write for his friends Alice, Bob, Charles, Dave and Eve.

Help Frank calculate all the possible combinations using Grover’s algorithm.

## Implementaion
[This](https://qiskit.org/textbook/ch-applications/satisfiability-grover.html) was used as inspiration.

### Channels
We create 5 quantum channel labelled as q<sub>i</sub>, i∈ {0, 1, 2, 3, 4}. where q<sub>o</sub> represents presence of Alice, q<sub>1</sub> represents presence of Bob, q<sub>2</sub> represents presence of Charles, q<sub>3</sub> represents presence of Dave, q<sub>4</sub> represents presence of Eve.

### Initialization
We apply Hadamard gate to each channel, it creates superposition of every possible states.
$$  |Ψ> = |S> $$

### Oracle
We create an oracle such that it flips a state if it satisfies the problem state.

$$ |Ψ> = |Sp > + |W> $$

where |Sp > is the superposition of state not satisfying Problem statment, while |W> is superposition of state satisfying Problem statment but with there phase flipped.

### Reflector
We create an reflector operator which reflects all the state about its mean-

$$  U(r) = 2*|S > < S| - I $$

### Measurment-
We get answer in one iteration so we don't need to reapply oracle and reflector pair.
The peaks of histogram shows which of the states satisies the problem states. 
 
