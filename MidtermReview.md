# Midterm Review

### Linked Lists
* Consider the below node class which forms a linked list. Write code which can print the linked list in reverse order.
```
class Node {
    Node next;
    int val;
    Node(int val) {
        this.val = val;
    }
}

// in main
Node n1 = new Node(1);
Node n2 = new Node(2);
n1.next = n2;
MyClass.myfunc(n1); // 2 1
```

### Sets and Hashing
* What might be an issue with the below hashcode ?
```
class PersonBadHashCode {
    String firstName;
    String lastName;
    PersonBadHashCode(String firstName, String lastName) {
        this.firstName = firstName;
        this.lastName = lastName;
    }

    @Override
    public int hashCode() {
        return this.firstName.hashCode() + 2 * this.lastName.hashCode();
    }

}
```

* Explain how sets offer O(1) lookup time for `set.contains` and `set.add`. When would this not be the case?



### Maps
* Write a function which can transform a roman numeral into an Arabic number, as below.
```
Symbol       Value
I             1
V             5
X             10
L             50
C             100
D             500
M             1000

Input: s = "LVIII"
Output: 58
Explanation: L = 50, V= 5, III = 3.
```

### Trees
* What is the advantage of a Red-Black tree over a Binary Search Tree?

* What is a Trie? Where would you use one?

* Consider the following TreeNode class. Write code to find the longest path from source to leaf.
```
class TreeNode {
    List<Node> children = new ArrayList<>();
    int val;
    Node(int val) {
        this.val = val;
    }

    void addChild(Node node) {
    	children.add(node);
    }

}

// in main
Node n1 = new Node(1);
Node n2 = new Node(2);
n1.addChild(n2);
```

* Consider a tree as outlined below. Which of the following begins "10 6 4 8..."? What about "4 6 8 10..."? 
    * In-order traversal
    * Pre-order traversal
    * Post-order traversal
```
    /**
     *              10
     *      6             14
     * 4       8      12      16
     *              11  13
     *
     */
    public static Node getTree2() {
        Node subtree1 = new Node(6, new Node(4), new Node(8));
        Node subtree2 = new Node(12, new Node(11), new Node(13));
        Node subtree3 = new Node(14, subtree2, new Node(16));

        Node root = new Node(10, subtree1, subtree3);
        return root;
    }

```


### Graphs
* Which of the following algorithms could be used to find the shortest path between two points in a graph?
    * `A*`
    * Breadth-first search
    * Depth-first search
    * Dijkstra's algorithm

* Consider the below DFS code. Make a drawing of the graph created in main, and add arrows to show the direction that the DFS will travel.

```
import java.util.*;

class Graph {
  private LinkedList<Integer> adjLists[];
  private boolean visited[];

  // Graph creation
  Graph(int vertices) {
    adjLists = new LinkedList[vertices];
    visited = new boolean[vertices];

    for (int i = 0; i < vertices; i++)
      adjLists[i] = new LinkedList<Integer>();
  }

  // Add edges
  void addEdge(int src, int dest) {
    adjLists[src].add(dest);
  }

  // DFS algorithm
  void DFS(int vertex) {
    visited[vertex] = true;
    System.out.print(vertex + " ");

    Iterator<Integer> ite = adjLists[vertex].listIterator();
    while (ite.hasNext()) {
      int adj = ite.next();
      if (!visited[adj])
        DFS(adj);
    }
  }

  public static void main(String args[]) {
    Graph g = new Graph(4);

    g.addEdge(0, 1);
    g.addEdge(0, 2);
    g.addEdge(1, 2);
    g.addEdge(2, 3);

    System.out.println("Following is Depth First Traversal");

    g.DFS(0);
  }
}

```

### Other
* In the below code snippet, what is the purpose of the `<h1>` tags?
```
<h1>Fox</h1>
<p>Foxes are small to medium-sized, omnivorous mammals belonging to several genera of the family Canidae. </p>
```
* What is the name of a computer technique which solves through a bunch of random trials what is difficult to solve through equations or calculations?
