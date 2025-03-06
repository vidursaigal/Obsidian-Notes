For each letter x ∈ S, we follow the path from the root to the leaf labeled x. Each time the path goes from a node to its left child, we write down a 0, and each time the path goes from a node to its right child, we write down a 1. We take the resulting string of bits as the encoding for x.

![[Pasted image 20250303121043.png]]


Note the contrast with the Shannon-Fano codes. Instead of a divide-and-conquer, top-down approach, Huffman’s algorithm uses a bottom-up, “greedy” approach. Here, “greedy” just means that at each step, we make local, short-sighted decision (merge the two lowest frequency nodes without worrying about how they will fit into the overall structure) that leads to a globally optimal outcome (an optimal prefix code for the whole alphabet).

Running Time:

Let n be the number of characters in the alphabet S. The recursive calls of the algorithm define a sequence of n − 1 iterations over smaller and smaller alphabets until reaching the base case. Identifying the lowest frequency letters can be done in a single scan of the alphabet in O(n) time, and so summing over the n − 1 iterations, the runtime is T(n) ≈ n + (n − 1) + ... + 2 + 1 = Θ(n 2 ). However, note that the algorithm requires finding the minimum of a set of elements. Thus we should expect to use a data structure that makes it easy to find the minimum of a set of elements quickly. A priority queue works well here. In this case, the keys are the frequencies. In each iteration, we just extract the minimum twice (to get the two lowest frequency letters), and then insert a new letter whose key is the sum of these two minimum frequencies, building the tree as we go. Our priority queue then contains a representation of the alphabet needed for the next iteration. Using a binary-heap implementation of a priority queue, we know that each insertion and extract-min operation take O(log n) time. Hence summing over all n iterations gives a total running time of O(n log n).


