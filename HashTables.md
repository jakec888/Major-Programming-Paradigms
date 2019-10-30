# Hash Tables

hash table is a data structure that maps keys to values for highly efficient lookup

# What?

A hash table is a data structure that implements an associative array abstract data type, a structure that can map keys to values. A hash table uses a hash function to compute an index, also called a hash code, into an array of buckets or slots, from which the desired value can be found.

# Why?

Hash tabels digest data and generate a fingerprint for that data. Unlike an index, this fingerprint depends ONLY on the data, and should be free of any predictable ordering based on the data. Any change to a single bit of the data should also change the fingerprint considerably.

Long story short, you can check if a key is already stored VERY quickly, and equally rapidly store a new mapping. Otherwise you'd have to keep a sorted list of keys, which is much slower to store and retrieve mappings from.

# When?

Hashing allows O(1) queries/inserts/deletes to the table. OTOH, a sorted structure (usually implemented as a balanced BST) makes the same operations take O(logn) time.

In a well-dimensioned hash table, the average cost for each lookup is independent of the number of elements stored in the table.

Many hash table designs also allow arbitrary insertions and deletions of key-value pairs.

In many situations, hash tables turn out to be more efficient than search trees or any other table lookup structure.

## Node JS Code Sample

```
const hash = (key,
    size) => {
  let hashedKey = 0;
  for (let i = 0; i < key.length; i++) {
    hashedKey += key.charCodeAt(i);
  }
  return hashedKey % size;
};

class HashTable {
  constructor() {
    this.size = 20;
    this.buckets = Array(this.size);

    for (let i = 0; this.buckets.length; i++) {
      this.buckets[i] = new Map();
    }
  }

  insert(key, value) {
    let idx = hash(key, this.size);
    this.buckets[idx].set(key, value);
  }

  remove(key) {
    let idx = hash(key, this.size);
    let deleted = this.buckets[idx].get(key);
    this.buckets[idx].delete(key);
    return deleted;
  }

  search(key) {
    let idx = hash(key, this.size);
    return this.buckets[idx].get(key);
  }
}
```
