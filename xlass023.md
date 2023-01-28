# Hash Tables

[Sources](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-30/resources/Hashtables.html)

`Hashtables` are a data structure that utilize key value pairs.

The basic idea of a hashtable is the ability to store the key into this data structure, and quickly retrieve the value. This is done through what we call a hash. A `hash` is the ability to encode the key that will eventually map to a specific location in the data structure that we can look at directly to retrieve the value.

## Terminologies

* Hash - A hash is the result of some algorithm taking an incoming string and converting it into a value that could be used for either security or some other purpose. In the case of a hashtable, it is used to determine the index of the array.

* Buckets -  A bucket is what is contained in each index of the array of the hashtable. Each index is a bucket. An index could potentially contain multiple key/value pairs if a collision occurs.

* Collisions -  A collision is what happens when more than one key gets hashed to the same location of the hashtable.

Since we are able to hash our key and determine the exact location where our value is stored, we can do a lookup in an `O(1)` time complexity. This is ideal when quick lookups are required.

Hash maps take advantage of an array’s `O(1)`.  Instead of adding elements to an array from beginning to end, a hash map uses a “hash function” to place each item at a precise index location, based off it’s key.

Basically, the hash function takes a key and returns an integer. We use the integer to determine where the key/value pair should be placed in the array. The hash code is calculated in constant time and writing to an array at one index is O(1) so the hash map has O(1) access.

The hash code is used again to read something from the hash map. Take the key, run it through the hash code to get a number, use that number to index the array. Calculating the hash code and reading an array at that index is all constant time to the hash map has O(1) read access!

Calculating the hash code and reading an array at that index is all constant time to the hash map has O(1) read access!

## Hashing

Basically, a hash code turns a key into an integer. It’s very important that hash codes are deterministic: their output is determined only by their input. Hash codes should never have randomness to them. The same key should always produce the same hash code.

## Creating a Hash

A hashtable traditionally is created from an array. I always like the size 1024. this is important for index placement. After you have created your array of the appropriate size, do some sort of logic to turn that “key” into a numeric number value. Here is a simplistic hashing algorithm:

```
Add or multiply all the ASCII values together.
    Multiply it by a prime number such as 599.
    Use modulo to get the remainder of the result, when divided by the total size of the array.
    Insert into the array at that index.
```
    


## Collisions

A collision occurs when more than one key hashes to the same index in an array. As mentioned earlier, a “perfect hash” will never have any collisions. To put this into perspective, the worst possible hash is one that hashes every single key to the same exact index of an array. The more keys you have hashed to a specific index, the more key/value pair combos you can potentially have.

## Bucket Sizes

Hash Maps can have any number of buckets. If a hash map has only a few buckets it will be densely full and have many collisions. If a hash map has more buckets it will be more sparsely populated, there will be less collisions, but there may be a lot of extra empty space.

## Methods

1. set()

When adding a new key/value pair to a hashtable:

```
    send the key to the hash() method.
    Once you determine the index of where it should be placed, go to that index
    Check if something exists at that index already, if it doesn’t, add it with the key/value pair.
    If something does exist, add the new key/value pair to the data structure within that bucket.
```

2. get()

The get() method takes in a key, gets the Hash, and goes to the index location specified. Once at the index location is found in the array, it is then the responsibility of the algorithm the iterate through the bucket and see if the key exists and return the value.

3. has()

The has() method will accept a key, and return a bool on if that key exists inside the hashtable. The best way to do this is to have the contains call the hash() method and check the hashtable if the key exists in the table given the index returned.

4. keys()

The keys() method returns a collection (array) of unique hash keys.

5. hash()

The hash() method will accept a key as a string, conduct the hash, and then return the index of the array where the key/value should be placed.