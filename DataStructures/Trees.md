# What?

A tree is a data structure composed of nodes. Each tree has a root node; the root node has zero or more child nodes - each child node has zero or more child nodes, and so on.

# Why?

Tree data structures are often used to organize ordered elements

# When?

Bibary Search Tree - Used in many search applications where data is constantly entering/leaving, such as the map and set objects in many languages' libraries.

Binary Space Partition - Used in almost every 3D video game to determine what objects need to be rendered.

Binary Tries - Used in almost every high-bandwidth router for storing router-tables.

Hash Trees - used in p2p programs and specialized image-signatures in which a hash needs to be verified, but the whole file is not available.

Heaps - Used in implementing efficient priority-queues, which in turn are used for scheduling processes in many operating systems, Quality-of-Service in routers, and A (path-finding algorithm used in AI applications, including robotics and video games). Also used in heap-sort.

Huffman Coding Tree (Chip Uni) - used in compression algorithms, such as those used by the .jpeg and .mp3 file-formats.

GGM Trees - Used in cryptographic applications to generate a tree of pseudo-random numbers.

Syntax Tree - Constructed by compilers and (implicitly) calculators to parse expressions.

Heap - Randomized data structure used in wireless networking and memory allocation.

T-tree - Though most databases use some form of B-tree to store data on the drive, databases which keep all (most) their data in memory often use T-trees to do so.

## Node JS Code Sample

```
class Node {
  constructor(value) {
    this.value = value;
    this.left = null;
    this.right = null;
  }
}

class BST {
  constructor(value) {
    this.root = new Node(value);
    this.count = 1;
  }

  size() {
    return this.count;
  }

  insert(value) {
    this.count++;

    let newNode = new Node(value);

    const searchTree = node => {
      if (value < node.value) {
        if (!node.left) {
          node.left = newNode;
        } else {
          searchTree(node.left);
        }
      } else if (value > node.value) {
        if (!node.right) {
          node.right = newNode;
        } else {
          searchTree(node.right);
        }
      }
    };

    searchTree(this.root);
  }

  min() {
    let currentNode = this.root;

    while (currentNode.left) {
      currentNode = currentNode.left;
    }

    return currentNode.value;
  }

  max() {
    let currentNode = this.root;

    while (currentNode.right) {
      currentNode = currentNode.right;
    }

    return currentNode.value;
  }

  contains(value) {
    let currentNode = this.root;

    while (currentNode) {
      if (value === currentNode.value) {
        return true;
      }
      if (value < currentNode.value) {
        currentNode = currentNode.left;
      } else {
        currentNode = currentNode.right;
      }
    }

    return false;
  }

  dfsInOrder() {
    let result = [];

    const traverse = node => {
      if (node.left) traverse(node.left);
      result.push(node.value);
      if (node.right) traverse(node.right);
    };

    traverse(this.root);

    return result;
  }

  dfsPreOrder() {
    let result = [];

    const traverse = node => {
      result.push(node.value);
      if (node.left) traverse(node.left);
      if (node.right) traverse(node.right);
    };

    traverse(this.root);

    return result;
  }

  dfsPostOrder() {
    let result = [];

    const traverse = node => {
      if (node.left) traverse(node.left);
      if (node.right) traverse(node.right);
      result.push(node.value);
    };

    traverse(this.root);

    return result;
  }

  bfs() {
    let result = [];
    let queue = [];

    queue.push(this.root);

    while (queue.length) {
      let currentNode = queue.shift();

      result.push(currentNode.value);

      if (currentNode.left) {
        queue.push(currentNode.left);
      }
      if (currentNode.right) {
        queue.push(currentNode.right);
      }
    }

    return result;
  }
}
```
