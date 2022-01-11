# Hash Tables

Source: [Code Fellows - Hash Tables](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-30/resources/Hashtables.html)

Hash tables an be used to quickly store and access data with an ideally O(1) storage and lookup time.

They involve using a large array (length 1024 for example) to store key value pairs.

## How does it work?

The index that information is stored within is determined using a **hashing function**. This will use the key to in some way determine a unique(ish) integer value. The integer value from the hash function is then used as the storage index for the information.

A **collision** is when two keys end up pointing to the same index. While generally unlikely in a well implemented hash table, this is dealt with using linked list. Each index is actually a "bucket", or linked list root, that allows for chaining key value pairs together in the case of a collision.

Collisions are not ideal but generally tolerable if all of your key value pairs don't end up in the same index. We can still **cut down drastically in lookup time**, only having to check a handful of nodes, as opposed to thousands of positions within an array.

## How fast is it?

The absolute worst case scenario (all keys on the same index) will result in a lookup time of O(N), since you would have to check every stored value until you find the one you're looking for. On the other hand, in a low-collision hash table lookup time can be O(1) since we can jump straight to a key's containing index using the hash function.

## Internal Methods

Hash tables generally have 4 internal methods during implementation:

* `add()` - Used to add new key/value pairs to a hashtable.
* `find()` - Recieves a key, gets the hash, and goes to the index specified. Iterates through bucket to find requested value.
* `contains()` - Accepts a key, and returns a boolean stating whether or not the key exists within the hash table.
* `gethash()` - Accepts a key as a string, and returns the hashed index value.

## Additional Resources

* [Paul Programming - Intro to Hash Tables](https://www.youtube.com/watch?v=MfhjkfocRR0)
* [hackerearth.com - Basics of Hash Tables](https://www.hackerearth.com/practice/data-structures/hash-tables/basics-of-hash-tables/tutorial/)
* [Wikipedia - Hash Table](https://en.wikipedia.org/wiki/Hash_table)
