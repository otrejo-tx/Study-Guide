### Study Guide

**1)** BST Structure

```C++
struct treeNode; //needed to use typedef below
typedef treeNode* pTreeNode;

struct treeNode
	{
		int _key;
		pTreeNode _left;  //treeNode *_left
		pTreeNode _right; //treeNode *_right
		treeNode(int key) : _key(key), _left(nullptr), _right(nullptr) {}
	};

	pTreeNode _root;
```

**2)** Insert Node

```C++
void BST::Insert(int value)
{
	//1, Inserts new node,adds it to the vector and increments _size
	if (_root == NULL)
	{
		_root = new treeNode(value);
		_size++;
	}
	else
		insert(_root, value);
}

void BST::insert(pTreeNode & leaf, int value)
{
	//Less Than Leaf (Left Side)
	if (value < leaf->_key)
	{
		if (leaf->_left == NULL)
		{
			leaf->_left = new treeNode(value);
			_size++;
		}
		else
			insert(leaf->_left, value);
	}

	//More Than Leaf (Right Side)
	if (value > leaf->_key)
	{
		if (leaf->_right == NULL)
		{
			leaf->_right = new treeNode(value);
			_size++;
		}
		else
			insert(leaf->_right, value);
	}

	//Equal to Leaf (if = to then will move to right to insert)
	if (value == leaf->_key)
	{
		if (leaf->_right == NULL)
		{
			leaf->_right = new treeNode(value);
			_size++;
		}
		else
			insert(leaf->_right, value);
	}
}
```

**3)** Tree Walk

```C++
void BST::Inorder()
{
	if (_root->_key == NULL)
		cout << "empty" << endl;
	else
		inorder(_root);
}

void BST::inorder(pTreeNode tree)
{
	if (tree != nullptr)
	{
		inorder(tree->_left);
		cout << tree->_key << endl;
		inorder(tree->_right);
	}
}

```
