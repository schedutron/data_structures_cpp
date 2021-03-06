1. *Think of a program you have used that is unacceptably slow. Identify the
specific operations that make the program slow. Identify other basic operations
that the program performs quickly enough.*

__A:__ I think of a CLI threaded newsreader I built in Python. It's slow in
organizing all the articles in a newsgroup into threads as it first downloads
all of their subjects and *then* organizes them. It can also get slow in
displaying specific articles as it has to download them first, and the speed of
that depends on the speed of the Internet connection. Operations which are
performed quick enough include formatting an article once it's downloaded and
writing a message to be sent to a local file before it's sent.

2. *Most programming languages have a built-in integer data type. Normally this
representation has a fixed size, thus placing a limit on how large a value can
be stored in an integer variable. Describe a representation for integers that
has no size restriction (other than the limits of the computer’s available main
memory), and thus no practical limit on how large an integer can be stored.
Briefly show how your representation can be used to implement the operations
of addition, multiplication, and exponentiation.*

__A__: A straightforward thing that came to my mind is, of course, *binary*
representation. But even representations which place a cap on the size of
integers to be stored use binary. However, I think of using binary differently.
In this representation, an integer is allocated memory dynamically. If during
some computation, the magnitude of the integer value increases and the existing
number of bits allocated to the integer are unable to store the new value (i.e.,
some sort of overflow occurs), then the computer should reallocate memory for
this integer so as to give it additional bits necessary to store it's value.
In a similar fashion, if the magnitude decreases, the integer can be reallocated
lesser memory to save space.
Addition and multiplication can be performed by the usual rules of binary
addition and multiplication, and exponentiation can be performed by repeated
multiplication.

3. *Define an ADT for character strings. Your ADT should consist of typical
functions that can be performed on strings, with each function defined in
terms of its input and output. Then define two different physical
representations for strings.*

__A__: Character strings are simply a sequence of characters. Strings are
an essential component of almost any computer program as they are the only
means of storing textual information in the program. Strings should support
the following functionalities:
  * concatenation: Given two strings, give back the joined form of the strings.
  For example, given "tea" and "pot", return "teapot".
  * find: Given a string and a character (or even a 'sub-string'), return the
  position of the character (or the substring), if present, within the string.
Following are two physical representation of strings:
  * Assign a byte value (or a block of multiple byte values) to every character
  and then store a string as an array of such byte values. Retrieval of the
  actual textual data from these byte values should be a straightforward task.
  * Can't think of other representation(s)!

4. Define an ADT for a list of integers. First, decide what functionality your
ADT should provide. Example 1.4 should give you some ideas. Then, specify your
ADT in C++ in the form of an abstract class declaration, showing the
functions, their parameters, and their return types.

__A__: Following functionalities should be provided by this ADT:
  * Given an integer and a position index, insert the integer at the
  provided position in the list
  * Given an integer, delete the integer from the list, if present
  * Compute its size (number of integers in the list)
  * Initialize an empty list
  * Given an integer, give the position of the integer in the list,
  if present

  Here's the abstract class declaration:
  ```
  class List{
    public:
      void insert(int num, int pos){

      }


      void delete(int num){

      }

      int size(void){

      }

      
      List(void){

      }


      int find(int num){

      }
  }
  ```
5. Briefly describe how integer variables are typically represented on a computer. (Look up one’s complement and two’s complement arithmetic in an introductory computer science textbook if you are not familiar with these.) Why does this representation for integers qualify as a data structure as defined in Section 1.2?

__A__: Integers are typically stored as an array of bits in a computer's memory. The signed integers (i.e., the ones which have positive or negative values) have their "leftmost" bit as the sign bit - when it's 0 - the integer is positive, otherwise negative. What follows is the binary representation of the number. The unsigned integers don't have this sign bit, so for the same allocated space, an unsigned representation can store a "bigger" value than a signed one. The techniques of 1's and 2's complement are used in the subtraction of multiple integers. The addtion procedure is pretty straightforward - it's just about adding bit by bit. This representation for integers qualifies as a data structure because it's implementing an ADT of integers - it's implementing their representation and behaviour.

6. Define an ADT for a two-dimensional array of integers. Specify precisely
the basic operations that can be performed on such arrays. Next, imagine an application that stores an array with 1000 rows and 1000 columns, where less than 10,000 of the array values are non-zero. Describe two different implementations for such arrays that would be more space efficient than a standard two-dimensional array implementation requiring one million positions.

__A__: A two-dimensional array of integers should have the following functionalities:
 * Given an array of integers, add the entire array to the 2D array.
 * Given an array of integers, remove the entire array from the 2D array, if present.
 * Given a integer, find it's 2D-index in the 2D array if the number is present.
 * Given a 2D-index, find the integer at that index within the array.

One efficient implementation of the 1000 by 1000 array would be to allott memory to the member
integers based on their value, i.e., before adding a number to the array, check whether it's
non-zero or zero. If it's zero, assign a single bit to it within the array, otherwise assign the standard integer bit-size for the number. That way we save space.

Other implementation may have null values for all the majority zero values and the usual integer values for non-zero values. But it may be a bad idea to store different data types (null and integer) within the single array.