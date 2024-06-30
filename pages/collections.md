# Java Data Structures - Collections

- By **GeorgeFreelanceDeveloper** Updated June 30, 2024
- Reviewed by **LucyFreelanceDeveloper**

## What are data structures?
Data structures are specialized formats for organizing, processing, retrieving, and storing data. They provide a means to manage large amounts of data efficiently for uses such as large databases and internet indexing services. Data structures are critical for designing efficient algorithms and software.

### Importance of Data Structures
* **Efficiency**: Data structures enable efficient data management, which is critical for system performance. For instance, choosing the right data structure can drastically reduce the time complexity of an algorithm.

* **Reusability**: Properly implemented data structures can be reused across multiple programs.

* **Abstraction**: They provide a level of abstraction that allows developers to manage data without needing to understand the intricacies of implementation details.

### Choosing the Right Data Structure
Choosing the right data structure for a specific problem is crucial. The choice depends on several factors, including:

* **Nature of the operation**: For example, use stacks for depth-first traversal or undo functionality, and queues for breadth-first traversal or order processing.
* **Memory usage**: Some data structures, like linked lists, use more memory due to storage of pointers, whereas arrays are more memory efficient but require contiguous memory allocation.
* **Performance**: Different operations (insertions, deletions, traversals) have varying performance implications based on the data structure chosen.

## What is Java collection framework?
The Java Collection Framework (JCF) is a unified architecture for representing and manipulating collections in Java. It provides a set of interfaces and classes for storing and managing groups of objects as a single unit. This framework is a part of the java.util package and is essential for effective data management and manipulation in Java applications.

## Array
### Description
In Java, an array is a data structure that allows you to store multiple values of the same type in a single variable. Arrays are useful for storing lists of data of a defined size, and they provide a way to efficiently access and manipulate this data.

### Key Characteristics of Arrays
* **Fixed Size**: Once an array is created, its size cannot be changed. The size must be specified when the array is instantiated.
* **Homogeneous Elements**: All elements in an array must be of the same data type (e.g., all integers, all doubles, or all objects of a specific class).
* **Zero-based Indexing**: Array indices start at 0, meaning the first element is at index 0, the second at index 1, and so on.

<br>
<div align=center>
<img src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/20230726162247/Array-data-structure.png" width="500"/>
</div>

### Example
```java
public class ArrayExample {
    public static void main(String[] args) {
        // Declare and initialize an array of integers
        int[] numbers = {10, 20, 30, 40, 50};

        // Print each element in the array
        System.out.println("Elements in the array:");
        for (int i = 0; i < numbers.length; i++) {
            System.out.println("Element at index " + i + ": " + numbers[i]);
        }

        // Modify an element in the array
        numbers[2] = 35;

        // Print the modified array
        System.out.println("Modified array:");
        for (int number : numbers) {
            System.out.println("Number: " + number);
        }
    }
}
```

## List
In Java, a `List` is an ordered collection (also known as a sequence) that allows for the storage of elements, including duplicates, and provides precise control over where each element is inserted. The `List` interface is a part of the Java Collections Framework and extends the `Collection` interface.

### Key Characteristics of List

1. **Ordered Collection**: Elements are maintained in the order they are inserted.
2. **Indexed Access**: You can access elements by their integer index (position in the list).
3. **Allows Duplicates**: A `List` can contain duplicate elements.
4. **Resizable**: Lists can dynamically resize, meaning they can grow as needed.

### Common Implementations

1. **ArrayList**:
   - Backed by a dynamic array.
   - Provides fast random access to elements.
   - Good for storing and accessing data.
   - Slower for adding/removing elements (except at the end).

2. **LinkedList**:
   - Implemented as a doubly-linked list.
   - Provides better performance for adding/removing elements (especially at the beginning or middle).
   - Slower random access compared to `ArrayList`.

3. **Vector**:
   - Similar to `ArrayList`, but synchronized.
   - Provides thread-safe operations.
   - Generally slower due to synchronization overhead.

### Common Methods

Some of the common methods provided by the `List` interface include:

- `void add(int index, E element)`: Inserts the specified element at the specified position.
- `boolean add(E element)`: Appends the specified element to the end of the list.
- `E get(int index)`: Returns the element at the specified position.
- `E remove(int index)`: Removes the element at the specified position.
- `int size()`: Returns the number of elements in the list.
- `boolean isEmpty()`: Returns true if the list contains no elements.
- `boolean contains(Object o)`: Returns true if the list contains the specified element.

<br>
<div align=center>
<img src="https://media.geeksforgeeks.org/wp-content/uploads/20240402155140/ArrayList_Integer_Object-768.png" width="500"/>
</div>

<br>
<div align=center>
<img src="https://media.geeksforgeeks.org/wp-content/uploads/20240410135517/linked-list.webp" width="500"/>
</div>


### Example Usage

Here's a short example demonstrating the usage of a `List` in Java using `ArrayList`:

```java
import java.util.ArrayList;
import java.util.List;

public class ListExample {
    public static void main(String[] args) {
        // Creating a List of Strings using ArrayList
        List<String> fruits = new ArrayList<>();
        
        // Adding elements to the List
        fruits.add("Apple");
        fruits.add("Banana");
        fruits.add("Cherry");
        
        // Inserting an element at a specific position
        fruits.add(1, "Blueberry");
        
        // Accessing elements from the List
        System.out.println("First fruit: " + fruits.get(0)); // Output: Apple
        System.out.println("Second fruit: " + fruits.get(1)); // Output: Blueberry
        
        // Removing an element from the List
        fruits.remove(2); // Removes "Banana"
        
        // Iterating over the List
        System.out.println("Fruits in the list:");
        for (String fruit : fruits) {
            System.out.println(fruit);
        }
    }
}
```

### Output

```
First fruit: Apple
Second fruit: Blueberry
Fruits in the list:
Apple
Blueberry
Cherry
```

In this example, an `ArrayList` is used to demonstrate basic `List` operations such as adding, accessing, inserting, removing, and iterating over elements.

### Stack
In Java, a `Stack` is a collection that follows the Last-In-First-Out (LIFO) principle, where elements are added to and removed from the top of the stack. The `Stack` class is a part of the Java Collections Framework and is used to model real-world stack behavior, such as stacking plates or books.

### Key Characteristics of Stack

1. **LIFO Structure**: The last element added is the first one to be removed.
2. **Operations at One End**: All operations (push, pop, peek) are performed at the top of the stack.
3. **Dynamic Size**: The stack grows and shrinks as elements are added and removed.

### Common Implementation

- **Stack Class**:
  - `java.util.Stack` is the standard implementation provided in Java.
  - It extends `Vector`, making it synchronized and thread-safe, but at the cost of performance.

### Common Methods

Some of the common methods provided by the `Stack` class include:

- `E push(E item)`: Pushes an item onto the top of the stack.
- `E pop()`: Removes and returns the item at the top of the stack.
- `E peek()`: Returns the item at the top of the stack without removing it.
- `boolean empty()`: Checks if the stack is empty.
- `int search(Object o)`: Returns the 1-based position of the item on the stack.

<br>
<div align=center>
<img src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/20230726165552/Stack-Data-Structure.png" width="500"/>
</div>

### Example Usage

Here's a short example demonstrating the usage of a `Stack` in Java:

```java
import java.util.Stack;

public class StackExample {
    public static void main(String[] args) {
        // Creating a Stack of integers
        Stack<Integer> stack = new Stack<>();
        
        // Pushing elements onto the Stack
        stack.push(10);
        stack.push(20);
        stack.push(30);
        
        // Peeking at the top element
        System.out.println("Top element: " + stack.peek()); // Output: 30
        
        // Popping elements from the Stack
        System.out.println("Popped element: " + stack.pop()); // Output: 30
        System.out.println("Popped element: " + stack.pop()); // Output: 20
        
        // Checking if the Stack is empty
        boolean isEmpty = stack.empty();
        System.out.println("Is the stack empty? " + isEmpty); // Output: false
        
        // Searching for an element
        int position = stack.search(10);
        System.out.println("Position of 10 in stack: " + position); // Output: 1 (1-based position)
    }
}
```

### Output

```
Top element: 30
Popped element: 30
Popped element: 20
Is the stack empty? false
Position of 10 in stack: 1
```

In this example, a `Stack` of integers is created and demonstrates basic stack operations such as pushing elements onto the stack, peeking at the top element, popping elements from the stack, checking if the stack is empty, and searching for an element within the stack.

### Queue
In Java, a `Queue` is a collection that follows the First-In-First-Out (FIFO) principle, where elements are added to the end of the queue and removed from the front. The `Queue` interface is part of the Java Collections Framework and is used to model real-world queue behavior, such as lines in a supermarket or task scheduling.

### Key Characteristics of Queue

1. **FIFO Structure**: The first element added is the first one to be removed.
2. **Two Ends**: Elements are added at the end (rear) and removed from the beginning (front).
3. **Dynamic Size**: The queue can grow and shrink as elements are added and removed.

### Common Implementations

1. **LinkedList**:
   - Implements the `Queue` interface.
   - Can act as a queue with efficient insertion and removal operations.
   
2. **PriorityQueue**:
   - Implements the `Queue` interface.
   - Elements are ordered according to their natural ordering or by a specified comparator.
   - Useful for priority-based tasks.

3. **ArrayDeque**:
   - Implements the `Deque` (double-ended queue) interface, which extends `Queue`.
   - More efficient than `LinkedList` for queue operations.

### Common Methods

Some of the common methods provided by the `Queue` interface include:

- `boolean add(E e)`: Inserts the specified element into the queue. Throws an exception if the queue is full.
- `boolean offer(E e)`: Inserts the specified element into the queue. Returns `false` if the queue is full.
- `E remove()`: Removes and returns the head of the queue. Throws an exception if the queue is empty.
- `E poll()`: Removes and returns the head of the queue. Returns `null` if the queue is empty.
- `E element()`: Retrieves, but does not remove, the head of the queue. Throws an exception if the queue is empty.
- `E peek()`: Retrieves, but does not remove, the head of the queue. Returns `null` if the queue is empty.

<br>
<div align=center>
<img src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/20230726165642/Queue-Data-structure1.png" width="500"/>
</div>

### Example Usage

Here's a short example demonstrating the usage of a `Queue` in Java using `LinkedList`:

```java
import java.util.LinkedList;
import java.util.Queue;

public class QueueExample {
    public static void main(String[] args) {
        // Creating a Queue of integers using LinkedList
        Queue<Integer> queue = new LinkedList<>();
        
        // Adding elements to the Queue
        queue.add(10);
        queue.add(20);
        queue.add(30);
        
        // Peeking at the head of the Queue
        System.out.println("Head of the queue: " + queue.peek()); // Output: 10
        
        // Removing elements from the Queue
        System.out.println("Removed element: " + queue.poll()); // Output: 10
        System.out.println("Removed element: " + queue.poll()); // Output: 20
        
        // Checking if the Queue is empty
        boolean isEmpty = queue.isEmpty();
        System.out.println("Is the queue empty? " + isEmpty); // Output: false
        
        // Checking the size of the Queue
        int size = queue.size();
        System.out.println("Size of the queue: " + size); // Output: 1
    }
}
```

### Output

```
Head of the queue: 10
Removed element: 10
Removed element: 20
Is the queue empty? false
Size of the queue: 1
```

In this example, a `Queue` of integers is created using a `LinkedList`. The example demonstrates basic queue operations such as adding elements, peeking at the head of the queue, removing elements, checking if the queue is empty, and checking the size of the queue.

### Set
In Java, a `Set` is a collection that does not allow duplicate elements. It models the mathematical set abstraction and is part of the Java Collections Framework. Sets are typically used when you want to store unique elements and care about fast look-up times.

### Key Characteristics of Set

1. **No Duplicates**: A `Set` cannot contain duplicate elements.
2. **Unordered Collection**: The elements are not stored in any particular order, although some implementations may maintain order.
3. **Efficient Membership Tests**: Provides efficient operations for checking if an element is present.

### Common Implementations

1. **HashSet**:
   - Backed by a hash table.
   - Does not maintain any order.
   - Provides constant time performance for basic operations (add, remove, contains).
   
2. **LinkedHashSet**:
   - Backed by a hash table and a linked list.
   - Maintains the insertion order of elements.
   - Slightly slower than `HashSet` due to the added overhead of maintaining order.

3. **TreeSet**:
   - Backed by a Red-Black tree.
   - Maintains elements in sorted order (natural ordering or by a specified comparator).
   - Provides log(n) time cost for basic operations.

### Common Methods

Some of the common methods provided by the `Set` interface include:

- `boolean add(E e)`: Adds the specified element to the set if it is not already present.
- `boolean remove(Object o)`: Removes the specified element from the set if it is present.
- `boolean contains(Object o)`: Returns true if the set contains the specified element.
- `int size()`: Returns the number of elements in the set.
- `void clear()`: Removes all the elements from the set.
- `boolean isEmpty()`: Returns true if the set contains no elements.

<br>
<div align=center>
<img src="https://media.geeksforgeeks.org/wp-content/uploads/20230302132510/s6.png" width="500"/>
</div>

### Example Usage

Here's a short example demonstrating the usage of a `Set` in Java using `HashSet`:

```java
import java.util.HashSet;
import java.util.Set;

public class SetExample {
    public static void main(String[] args) {
        // Creating a Set of Strings using HashSet
        Set<String> fruits = new HashSet<>();
        
        // Adding elements to the Set
        fruits.add("Apple");
        fruits.add("Banana");
        fruits.add("Cherry");
        fruits.add("Apple"); // Duplicate element, will not be added
        
        // Checking if the Set contains a specific element
        boolean hasBanana = fruits.contains("Banana");
        System.out.println("Set contains Banana: " + hasBanana); // Output: true
        
        // Removing an element from the Set
        fruits.remove("Banana");
        
        // Iterating over the Set
        System.out.println("Fruits in the set:");
        for (String fruit : fruits) {
            System.out.println(fruit);
        }
        
        // Checking the size of the Set
        int size = fruits.size();
        System.out.println("Number of fruits in the set: " + size); // Output: 2 (since "Apple" was added only once)
    }
}
```

### Output

```
Set contains Banana: true
Fruits in the set:
Apple
Cherry
Number of fruits in the set: 2
```

In this example, a `HashSet` is used to demonstrate basic `Set` operations such as adding, checking for existence, removing, iterating over elements, and checking the size of the set. Note how the duplicate "Apple" is not added to the set, illustrating the uniqueness property of sets.

## Map
In Java, a `Map` is an object that maps keys to values. A map cannot contain duplicate keys; each key can map to at most one value. The `Map` interface is part of the Java Collections Framework and is used to represent a collection of key-value pairs.

### Key Characteristics of Map

1. **Key-Value Pairs**: Maps store elements in key-value pairs.
2. **No Duplicate Keys**: Each key is unique and maps to exactly one value.
3. **Null Keys and Values**: Some implementations allow null keys and values, while others do not.
4. **Efficient Retrieval**: Maps provide efficient retrieval of values based on keys.

### Common Implementations

1. **HashMap**:
   - Backed by a hash table.
   - Provides constant-time performance for basic operations (add, remove, contains) assuming a good hash function.
   - Allows one null key and multiple null values.
   
2. **LinkedHashMap**:
   - Extends `HashMap` with a linked list running through its entries.
   - Maintains insertion order (or access order if specified).
   - Slightly slower than `HashMap` due to the overhead of maintaining order.
   
3. **TreeMap**:
   - Backed by a Red-Black tree.
   - Maintains keys in sorted order according to their natural ordering or by a specified comparator.
   - Provides log(n) time cost for basic operations.
   - Does not allow null keys.

4. **Hashtable**:
   - Similar to `HashMap`, but synchronized and thread-safe.
   - Does not allow null keys or values.
   - Generally slower due to synchronization overhead.

### Common Methods

Some of the common methods provided by the `Map` interface include:

- `V put(K key, V value)`: Associates the specified value with the specified key in the map.
- `V get(Object key)`: Returns the value to which the specified key is mapped, or `null` if the map contains no mapping for the key.
- `V remove(Object key)`: Removes the mapping for a key from the map if it is present.
- `boolean containsKey(Object key)`: Returns true if the map contains a mapping for the specified key.
- `boolean containsValue(Object value)`: Returns true if the map contains one or more mappings for the specified value.
- `Set<K> keySet()`: Returns a `Set` view of the keys contained in the map.
- `Collection<V> values()`: Returns a `Collection` view of the values contained in the map.
- `Set<Map.Entry<K, V>> entrySet()`: Returns a `Set` view of the mappings contained in the map.

<br>
<div align=center>
<img src="https://media.geeksforgeeks.org/wp-content/uploads/20230306152011/mp1.png" width="500"/>
</div>

### Example Usage

Here's a short example demonstrating the usage of a `Map` in Java using `HashMap`:

```java
import java.util.HashMap;
import java.util.Map;

public class MapExample {
    public static void main(String[] args) {
        // Creating a Map of integers and their corresponding string values
        Map<Integer, String> map = new HashMap<>();
        
        // Adding key-value pairs to the Map
        map.put(1, "One");
        map.put(2, "Two");
        map.put(3, "Three");
        
        // Retrieving a value based on a key
        String value = map.get(2);
        System.out.println("Value for key 2: " + value); // Output: Two
        
        // Checking if a key exists in the Map
        boolean containsKey = map.containsKey(3);
        System.out.println("Map contains key 3: " + containsKey); // Output: true
        
        // Removing a key-value pair from the Map
        map.remove(1);
        
        // Iterating over the Map's key-value pairs
        System.out.println("Remaining entries in the map:");
        for (Map.Entry<Integer, String> entry : map.entrySet()) {
            System.out.println("Key: " + entry.getKey() + ", Value: " + entry.getValue());
        }
    }
}
```

### Output

```
Value for key 2: Two
Map contains key 3: true
Remaining entries in the map:
Key: 2, Value: Two
Key: 3, Value: Three
```

In this example, a `HashMap` is used to demonstrate basic `Map` operations such as adding key-value pairs, retrieving a value by key, checking for key existence, removing a key-value pair, and iterating over the map's entries.

## Notes
### Hash Functions and HashCode in Java

#### Hash Functions

A hash function is a function that takes an input (or "key") and returns a fixed-size string of bytes. The output, typically a hash code, is usually a number which acts as an index to an array of buckets. The idea is to distribute the keys uniformly across the buckets to enable efficient retrieval.

In Java, hash functions are used primarily in hash-based collections like `HashMap`, `HashSet`, and `Hashtable`.

#### HashCode

In Java, the `hashCode()` method is part of the `Object` class and is intended to provide a hash code for objects. The hash code is an integer representation generated by the hash function, and it is used by hash-based collections to quickly locate a bucket where the object is stored.

### Key Characteristics

1. **Uniform Distribution**: A good hash function distributes hash codes uniformly across the hash table to minimize collisions.
2. **Deterministic**: The hash code for a particular object should be consistent and return the same value every time it is called during an execution of a program.
3. **Equality Consistency**: If two objects are considered equal according to the `equals()` method, they must have the same hash code.

### Common Implementations

1. **HashMap**: Uses `hashCode()` to determine the bucket for storing key-value pairs.
2. **HashSet**: Uses `hashCode()` to determine if two objects are identical in terms of their contents.

## Resources
* [Java Collection Tutorial - geeksforgeeks.org](https://www.geeksforgeeks.org/java-collection-tutorial/)
* [Collections in Java - javatpoint.com](https://www.javatpoint.com/collections-in-java)
* [Webinar: Java Data Structures Tutorial - amigoscode](https://www.youtube.com/watch?v=8MmMm2-kJV8)

