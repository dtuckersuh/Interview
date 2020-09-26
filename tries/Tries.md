# [Trying to Understand Tries](https://medium.com/basecs/trying-to-understand-tries-3ec6bede0014)

A **trie** is a tree-like data structure where the nodes store entire alphabet, and strings/words can be **retrieved** by traversing down a branch path of the tree

Each trie has an empty root node, w/ links to other nodes -- one for each possible alphabetic value

![Trie](https://miro.medium.com/max/500/1*-KWorUiWCwn-a5iGw2chZg.jpeg)

#### The size of a trie is directly correlated to the size of all possible values the trie could represent

![Trie Node](https://miro.medium.com/max/500/1*kxvAPQ3xtvRV5mnLE2_9Hw.jpeg)

A single node in a trie contains two things:

1. A value, which might be `null`
2. An array of references to child nodes, all of which might also be `null`

We can use the array's indexes to find specific references to nodes
    - If using English alphabet, A will be stored at index 0

## Giving trie traversal a try

![Trie example](https://miro.medium.com/max/500/1*sZOrNXzlQICVv5ePpav1-g.jpeg)

If we want to add the word 'pecked' to the list of words represented by the trie, we need to do two things:

1. Check that 'pecked' doesn't already exist in trie
2. If we traversed down branch where word ought to live and the word doesn't exist yet, we'd insert a value into the node's reference where the word should go

![Array pointers in tries](https://miro.medium.com/max/500/1*wbk03zSyo_BM2m2G7pOBcg.jpeg)

![Searching through a trie](https://miro.medium.com/max/500/1*H-kT86L4BVATY71T4exqxg.jpeg)

![Deleting from a trie](https://miro.medium.com/max/700/1*PCPqDi6_hBM67Mg9LFCxjw.jpeg)

Two steps to deleting from a trie:

1. Find node that contains key value to be deleted, and set the value to null
2. Check node's references and see if all its pointers to other nodes are also null. If so, there are no other words/branches stemming from this one and so this node can be removed
    - If we fail this step, we can remove substrings of a word

## Differences between Hash Tables and Tries

![Hash tables vs tries](https://miro.medium.com/max/500/1*l2w5kHuKypUf60itGDXIzQ.jpeg)

### How tries change as they grow

![wake up in the morning and i ask myself](https://miro.medium.com/max/500/1*OH24lEX3tbNeMYzORFf6qg.jpeg)

## Big O of Tries

![biggo](https://miro.medium.com/max/700/1*1Cmj94uageBuWb22vW-uWw.jpeg)

## Problems

[Implement Trie(Prefix Tree)](https://leetcode.com/problems/implement-trie-prefix-tree/)
[Design Add and Search Words Data Structure](https://leetcode.com/problems/design-add-and-search-words-data-structure/)
