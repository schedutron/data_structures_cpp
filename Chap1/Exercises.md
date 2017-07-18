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

2. Most programming languages have a built-in integer data type. Normally this
representation has a fixed size, thus placing a limit on how large a value can
be stored in an integer variable. Describe a representation for integers that
has no size restriction (other than the limits of the computer’s available main
memory), and thus no practical limit on how large an integer can be stored.
Briefly show how your representation can be used to implement the operations
of addition, multiplication, and exponentiation.

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
