# Cipher Decryption Using Genetic Algorithm and Language Model

### Substitution Cipher :

Substitution cipher is a type of encryption technique in which each letter in the plaintext is replaced by another letter in the ciphertext. In order to decrypt a substitution cipher, it is necessary to determine the mapping between the ciphertext and plaintext letters. This can be accomplished using a genetic algorithm and a language model, which can help determine the most likely mapping based on the frequency of letters and words in the language being used.

### Genetic Algorithm :

A genetic algorithm is a search-based optimisation technique inspired by the process of natural selection. In the case of cipher decryption, the genetic algorithm can be used to generate and evolve potential mappings between the ciphertext and plaintext letters. The algorithm can then evaluate and select the most promising mappings, gradually refining them until the correct mapping is found.

### Why Use Genetic algorithm to find the reverse mapping ?

- In order to crack the right reverse mapping there are 26! combinations, making it infeasible for any machine to solve
- So we make intelligent guesses which takes us closer to the optimal answer
- We initially take a random reverse mapping and then apply a process such as mutation, swapping 2 strands, deletion or updation
- For Substitution Cipher Decryption we use Swapping 2 alphabet mappings because:
    - The mapping should be invertible , hence we can’t have 2 alphabets pointing towards same alphabet, so mutation is not possible
    - The mapping should map all the 26 alphabets to other 26 alphabets, hence deletion is not possible
    - Swapping 2 alphabet maintains invertibility and maps 26 alphabets to other 26 alphabets

### How to judge which combination is performing better ?

- We calculate a score which makes use of log probabilities of the combination of characters in words in the message
- The log probability is calculated from the state transition Markov matrix and initial state distribution. This is trained from the training corpus
- We sort the ranked combinations and choose the top x scoring combinations and add them with their off spring combinations