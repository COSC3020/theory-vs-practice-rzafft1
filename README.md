[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-718a45dd9cf7e7f842a935f5ebbe5719a5e09af4491e668f4dbf3b35d5cca122.svg)](https://classroom.github.com/online_ide?assignment_repo_id=11949062&assignment_repo_type=AssignmentRepo)
# Theory vs. Practice

- List 3 reasons why asymptotic analysis may be misleading with respect to
  actual performance in practice.

  - We may have many constants which we dont take into account in asymptomatic analysis
  - Ignoring ordering of terms. Using our equation for Big O Theory, T(n) <= cf(n) + n<sub>0</sub>, we need to find a single set of constants, c and n<sub>0</sub>. This means that in our asymptomatic analysis, we may end up ignoring low order terms that still have a large impact on runtime, but are ignored for our analysis, because there is a higher order term that will have an even larger impact on runtime. We will pick the higher order term for our analysis rather than the lower order term, however the lower order may have still been growing fast, and could still have an impact on runtime. 
  - We ignore hardware, which can make a massive difference with runtime speeds, and memory capacity 

- Suppose finding a particular element in a binary search tree with 1,000
  elements takes 5 seconds. Given what you know about the asymptotic complexity
  of search in a binary search tree, how long would you guess finding the same
  element in a search tree with 10,000 elements takes? Explain your reasoning.

  - According to Big O, T(n) <= cf(n) for all positive constants c and n<sub>0</sub>
  - Assuming both trees are balenced, the average case complexity of searching a binary search tree is &Theta;(log<sub>2</sub>n), where n is the size of the tree
  - log<sub>2</sub>(n) also gives us the maximum height of a balenced search tree, and if n = 1000, the search will require a maximum of log<sub>2</sub>(n + 1) comparisons 
  - log<sub>2</sub>(1000) = 10 ... this infers that a tree (assuming its balenced) with 1000 elements has a height 10
  - We know that a tree with 1000 elements has height 10, and this will require at most, 11 comparisons, which in this case, took 5 seconds
  - log<sub>2</sub>(10000) = 13.3 ... this infers that a tree (assuming its balenced) with 10000 elements has a height 13
  - Now using this information, we can estimate that a tree that will require about 14 comparisons will take around ($\frac{13.3}{10}$ * 5) = 6.6 seconds

- You measure the time with 10,000 elements and it takes 100 seconds! List 3
  reasons why this could be the case, given that reasoning with the asymptotic
  complexity suggests a different time.

  - The desired item could have been found near the root in the tree with 1000 elements, and when we searched in the tree with 10000 elements the desired item could have been near the bottom of the tree, or not even in the tree. 
  - We may have gotten the best case in the first run (5 seconds) and then the worst case in the second run(100 seconds). There are several things that could account for a different this large. We could have changed the type of input between runs (searching for strings rather than integers, where we have to compare each string which would take longer than comparing each integer)... Assuming that we dont know that the tree will always be balenced, the first run could have had a very balenced tree of 10,0000 elements (best case) whereas the second run could have delt with a very unbalenced tree of 10,0000 elements (worse case) with a much larger depth. 
  - These two cases could have ran on different machines, which can play a massive factor in runtime 

Add your answers to this markdown file.

Resources : 

Stack Overflow

- https://stackoverflow.com/questions/34421620/role-of-lower-order-terms-in-big-o-notation
