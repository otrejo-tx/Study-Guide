#Omar Trejo

### Exam 1 Review

### Arithmetic Series 

-

### Geometric Series

-

### Logarithms

-

### Linked List

- Structure
```c++ 
class LinkedList
{
  struct Node {
    int _val;
    Node * _next;
    Node(int v, Node* n) :_val(v), _next(n) {};
    
  };
  Node* _header; // will store the size in the headers _val variable.
  Node* _last; // You could also have placed the size variable here!! and not placed in in the header.
  
  public:
  LinkedList();
  ~LinkedList();
  // This is the insert function. It adds a new item to the end of the linked list
  void push_back(int n);
  // Print out the Linked List on one line.
  void print(int n);
};
```
- Clear()
```c++
void SSList::Clear(){
  Node * follow = Headerptr -> next;
  for (int i = 0; i < size; i++){
    Headerptr = follow -> next;
    delete follow;
    follow = Headerptr;
  }
  LastNodeptr = Headerptr;
  follow = nullptr;
}
```

### Big O

-

### Complexity

-


### Exam 2 Review

### Binary Search Tree

-


### Exam 3 Review

### DSW Algorithm

-

### AVL Tree

-

### Heaps (Heap Sort)

-

### Priority Queue

-

### Sorts

- Quick Sort
- f

```c++
BFS(G, s) {
    initialize vertices;
    Q = {s};		// Q is a queue (duh); initialize to s
    while (Q not empty) {    
        u = RemoveTop(Q);
        for each v  u->adj {
            if (v->color == WHITE)
                v->color = GREY;
                v->d = u->d + 1;
                v->p = u;
                Enqueue(Q, v);
        }
        u->color = BLACK;
    }
}
```
```c++
vector<int> Graph::BFS(int vertex)
{
	int u;
	queue<int> Q;

	Color.resize(G.size()); // Resize to number of Vertices
	for (int i = 0; i < Color.size(); i++)//initialize every vertex with WHITE
		Color[i] = WHITE;

	vector<int> Parent(G.size(), -1);
	Q.push(vertex);

	while (!Q.empty()) {
		u = Q.front(); Q.pop();

		for (auto v : G[u])
			if (Color[v.first] == WHITE) {
				Color[v.first] = GREY; // If visted sets color to GREY
				Parent[v.first] = u;
				Q.push(v.first);
			}
		Color[u] = BLACK; // After fully explored color to BLACK
	}
	return Parent;
}
```
```c++
void Graph::DFS_Visit(int edge, vector<int>& visited)
{
	visited.push_back(edge);
	Color[edge] = GREY; // If visted sets color to GREY
	for (auto v : G[edge]) { //Visit each edge in vertex
		if (Color[v.first] == WHITE)
			DFS_Visit(v.first, visited);
	}
	Color[edge] = BLACK;// After fully explored color to BLACK
}
```
