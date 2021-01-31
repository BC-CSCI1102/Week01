# CSCI 1102 Computer Science 2

### Spring 2021

------

## Lecture Notes

### Week 1: Getting Started

#### Topics:

1. What is CSCI 1102 about?
2. Course Administration

---

**Notes:**

  1. Course home page: https://github.com/BC-CSCI1102/s21
   2. Syllabus under the `resources` link in `pdf/`. We expect you to read the syllabus and follow the protocols laid out there.
     3. You can find a video recording of the week 1 lecture on the class Canvas site.

---

## 1. What is CSCI 1102 about?

This course has two main themes:

1. **Cover a range of classical data structures and algorithms** including stacks, queues, deques, priority queues, trees of various sorts,   including binary search trees and balanced binary search trees, binary heaps, hash tables, sorting algorithms and graphs.

   In lecture, we considered [Huffman Coding](https://en.wikipedia.org/wiki/Huffman_coding) as an example. See the video recording on the Canvas site.

   We considered compression of the string  `"ALABAMA"`,  a string of length 7. In the standard fixed-length 8-bit ASCII code, 7 x 8 = 56 bits would be required. Looking at the string from a statistical perspective, the letter `'A'` occurs 4 times while the letters `'B'`, `'L'` and `'M'` occur just once. We think of `'A'` as being run-of-the-mill or ordinary with little information. Since the others are unusual (occurring just once), they're considered to convey more information.

   Huffman's algorithm uses a [priority queue](https://en.wikipedia.org/wiki/Priority_queue), with weighted entries. A low frequency confers a high priority while a high frequency confers a low priority. If the letters are inserted into the queue in alphabetical order, i.e., first `'A'`, then `'B'` etc, we would have the following priority queues. The front of the queue is to the left. Ties are broken in favor of the existing entries.

   ```
   A4
   B1 A4
   B1 L1 A4
   B1 L1 M1 A4
   ```

   Once the priority queue is constructed, Huffman's algorithm processes the queue by removing the first two elements, combining them and reinserting the result.

   ```
   B1 L1 M1 A4
   
   M1  2   A4
      / \
     B   L
   
       3   A4
      / \ 
     M   2
        / \
       B   L
   
         7
        / \
       3   A
      / \
     M   2
        / \
       B   L
   ```

   A binary code is then given with a left traversal assigned 0 and a right traversal assigned 1.

   ```
         .
       0/ \1
       .   A
     0/ \1         M = 00; B = 010; L = 011; A = 1
     M   .
       0/ \1
       B   L
   ```

   With this coding, the input string would code as

   ```
   A  L  A  B  A M  A
   1 011 1 010 1 00 1
   ```

   Twelve bits rather than 56. The algorithm made essential use of 3 data structures:

   1. A frequency table
   2. A priority queue
   3. A full binary tree.

   We'll learn about all of these and many interesting algorithms like this in this course.

   ---

2. **Further develop your ability to design and develop software.**

   In this course we're going to work on developing *good* code. What do we mean by "good"? Good code is

   + correct — it does what it is supposed to do;
   + performant — both with respect to time and space;
   + easy to read;
   + maintainable.

  + Devising ways to structure data and their related algorithms can be seen as *developing new* *types*.
    
+ a central activity of coding, and the focus of this course
    
  + new types should be *modular* and *compositional*

    + modular:
      + types are packaged up — think lego blocks; 
      + build new types out of old types by plugging them together

    + compositional:
      + what things are plug-compatible
      + *types mediate the composition*.

  + Methodology: Abstract Data Types (ADTs)
    + Barbara Liskov (~1974, 2009 Turing Award winner)
      1. introduce a named type
      2. introduce named operations (functions) acting on the type
      3. separate:
         + specification (or signature)
         + implementation
      4. client/user knows only the specification, the implementation is opaque.

    
    
    

