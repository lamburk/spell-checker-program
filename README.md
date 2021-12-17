# spell-checker-program
For this project you will implement a relatively simple spell checker for English text. The spell checker will incorporate a database of known words, built from a simple word list and organized for efficient searching

The controller will read words from an input text file, one by one, and pass them to the spell checker for processing. If the spell checker finds an exact match, it will simply indicate the word is spelled correctly. If not, the spell checker will provide the controller with a (possibly empty) list of suggested spellings. To select suggestions, the spell checker will need some rules for deciding whether a match is close enough. Suppose that W is the word whose spelling  is being checked,and that C is a candidate for the suggested spelling list. Your spell checker will add C to the list of suggestions according to the  following rules (in the order given)

If the lengths of W and C differ by more than two, do not suggest C.
If W is a prefix of C, or if C is a prefix of W, then suggest 
Compare the characters of W to those of C, one by one, until reaching the end of one or both strings. If there areno more than two mismatches, and the number of mismatches is less than the lengths of both W and C, suggest C.

These rules are somewhat arbitrary, and certainly too simple for a real spell checker; that's acceptable for this assignment since the primary point is the data structure design, not the matching algorithm

The primary data structures element of this project holds the word list against which spelling will be checked. There are a number of good ways this could be handled. Your implementation is under the following specific requirements:

The spell checker must store the word list in an AVL tree
The spell checker must be an object. It will contain an AVL tree, but it will not simply be an AVL tree.
You must encapsulate the AVL tree, and its nodes, as C++ templates.
The words must be stored in the tree as C++ string objects.
The AVL tree interface must include only functions that are appropriate for a container, such as insert()  and find(). The tree must not take any responsibilities that belong to the controller, such as reading in words to be checked, or to the spell checker itself, such as building the list of suggested alternative words.
For testing and for the demos, your tree must have the ability to display itself to a specified output stream in the manner described in the notes for a BST. 

Your design must make appropriate use of classes. Aside from node objects used only within an encapsulating class, data members of classes must be private.
The use of STL containers, such as the vector, is allowed for this project, for example as a way to encapsulate the list of suggestions when carrying out a spell check

Program execution: 

The program will be invoked with three command-line parameters: 

spellcheck <word list file> <file to check> <log file> 

The program will verify the existence of the two input files; if either is missing, it will print an error message and exit.
