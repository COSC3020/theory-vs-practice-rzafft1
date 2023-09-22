[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-718a45dd9cf7e7f842a935f5ebbe5719a5e09af4491e668f4dbf3b35d5cca122.svg)](https://classroom.github.com/online_ide?assignment_repo_id=11949062&assignment_repo_type=AssignmentRepo)
# Theory vs. Practice

- List 3 reasons why asymptotic analysis may be misleading with respect to
  actual performance in practice.

  - We may have many constants which we dont take into account in asymptomatic analysis
  - Ignoring ordering of terms. We may have one million elements to sort, however we come to the same asymptomatic conclusion with the same algorithm that we would if we were sorting ten elements
  - We ignore hardware, which can make a massive difference with runtime speeds, and memory capacity 

- Suppose finding a particular element in a binary search tree with 1,000
  elements takes 5 seconds. Given what you know about the asymptotic complexity
  of search in a binary search tree, how long would you guess finding the same
  element in a search tree with 10,000 elements takes? Explain your reasoning.

  - For positive onstant c and n0 such that T(n) <= cf(n)
  - Assuming both trees are balenced, the average case complexity of searching a binary search tree is &Theta;(log<sub>2</sub>n), where n is the size of the tree
  - log<sub>2</sub>(n) also gives us the maximum height of a balenced search tree, and if n = 1000, the search will require a maximum of log<sub>2</sub>(n + 1) comparisons 
  - log<sub>2</sub>(1000) = 10 ... this infers that a tree (assuming its balenced) with 1000 elements has a height 10
  - We know that a tree with 1000 elements has height 10, and this will require at most, 11 comparisons, which in this case, took 5 seconds
  - log<sub>2</sub>(10000) = 13.3 ... this infers that a tree (assuming its balenced) with 10000 elements has a height 13
  - Now using this information, we can estimate that a tree that will require about 14 comparisons will take around ($\frac{13.3}{10}$ + 5) = 6.33 seconds

- You measure the time with 10,000 elements and it takes 100 seconds! List 3
  reasons why this could be the case, given that reasoning with the asymptotic
  complexity suggests a different time.

  - The desired item could have been found near the root in the tree with 1000 elements, and when we searched in the tree with 10000 elements the desired item could have been near the bottom of the tree
  - We may have gotten the best case in the first run (5 seconds) and then the worst case in the second run(100 seconds)
  - Was the element not even there? we maybe just searched through the entire tree without finding anything
  - These two cases could have ran on different machines, which can play a massive factor in runtime 
  - What types are we searching / comparing... we could be comparing videos rather than numbers or very long strings rather than single characters. The type of data could have a massive difference between runtimes. 

Add your answers to this markdown file.
