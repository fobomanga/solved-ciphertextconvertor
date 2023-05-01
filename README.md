Download Link: https://assignmentchef.com/product/solved-ciphertextconvertor
<br>
You are required to create a program to automatically decrypt cipher text messagesencoded using one of the four encryption algorithms below.

? Caesar cipher

? Columnar transposition cipher

? Modified Caesar cipher

? Diagonal columnar cipher

Modified Caesar cipher

This is a substitution cipher which modifies the Caesar cipher in two steps. In the firststep, a word is chosen and inserted into the beginning of the alphabet. Duplicatedcharacters are deleted to keep the alphabet to 26 letters. For example, with the word”hello” (for simplicity assume everything is lower case), the alphabet is modified by

h e l o a b c d f g i j k m n p q r s t u v w x y z

Note that except the letters appearing in the word “hello” (‘h’,’e’,’l’ and ‘o’), theremaining letters are in the original alphabetic order.

In the second step, the whole modified alphabet is shifted circularly in one directionwith fixed step size. This is the same step as the Caesar cipher. An example of rightshift with step size 3 for the above alphabet is shown below

o a b c d f g i j k m n p q r s t u v w x y z h e l

The random word added to the beginning of the alphabet in the first step adds moreperturbation to the substitution scheme, increasing the search space for breaking thecipher. To achieve best result, the word used should be moderately long and the stepsize should not equal the number of unique letters in the word.

To break the cipher, one needs to determine both the word inserted in step 1 and thestep size for shifting of alphabet in step 2. This can be done by exhaustive or bruteforce search by checking all possible words and shifts. Note that the step size could beeither positive (right shift) or negative (left shift) for different directions of shift forthe alphabet. To make it simple, we only used a few technical words for altering thealphabet in step 1, which will be provided with this assignment in a text file.

Diagonal transposition cipher

Diagonal transposition cipher is a transposition cipher similar to the columnartransposition. Firstly, it rearranges the plaintext message into a block of fixed numberof columns by fitting the input text on each row of the block consecutively. This is thesame step as columnar transposition. However, different from columnar transpositionwhich produces the ciphertext message by scanning the columns of the rearranged text block, the diagonal transposition cipher produces the ciphertext message byscanning along the diagonal directions. An example of diagonal transposition isshown in the figure below with two variants for diagonal and reverse diagonal ciphers,where the red dotted lines show the scanlines along which the ciphertext messagesare produced. For the diagonal version, it starts from the bottom-left corner and scansthe diagonal lines sweeping from top-left to bottom-right corners. For the reversediagonal version, it starts from the top-left corner and scans the reverse diagonal linessweeping from top-right to bottom-left corners. With the illustrated example, for theplaintext message “CRYPT OGRAP HYISF UN” wrapped into 5 columns, theciphertext messages produced by diagonal transformation ciphers are “uhnoycgirr syafp pt” for the diagonal version and “corhg ynyrp niats pt”for the reverse diagonal version(Figure Attached as an attachment)

Program Flow and I/O

You will be provided with a ciphertext file. Each line of the file contains a ciphertextmessage to be hacked. Unlike the decryption exercises you did in lab 3, you are notgiven any information on the types of cipher and the keys used for encryption. Youneed to determine these and obtain the decrypted message automatically with yourprogram. However, the plaintext messages are meaningful English expressionscontaining alphabetical letters only. An English dictionary is also provided in a textfile format for your hacking program. You need to develop an algorithm to effectivelyhack the ciphertext messages in the input file with high accuracy.For a ciphertext message on each line of the input file, your program should outputthe following information in comma separated fields,

PlainText, CipherType, KeyVal

where PlainText is the estimated plaintext message, CipherType is the type ofthe cipher used for encryption, which can take any of the four values ‘C’, ‘T’, ‘M’, ‘D’,corresponding to four different ciphers used, namely Caesar, columnar transposition,modified Caesar, diagonal transformation. KeyVal represents the key value of theencryption algorithm, which is the number of alphabetical shifts (positive for rightshift and negative for left shift) for Caesar and modified Caesar ciphers, number of columns for rearrangement of the text block for columnar transposition and diagonaltransposition (positive for diagonal version and negative for reverse diagonal version)ciphers. The modified Caesar has one more key, the word inserted at the beginning ofthe alphabet for the substitution scheme. Some examples are shown below

Input: dgyzr kcoez nkdo

Output: TWOPH ASEUP DATE,C,10

(Caesar cipher – right shift the alphabet 10 times)

Input: saupw nrsed cesht oi

Output: SWEET ANDSO URCHI PS,T,5

(Columar transposition – fold the text in 5 columns)

Input: bxsyx rnppy hydcy

Output: MAKEA DIFFE RENCE,M,cryptanalysis,-2

(Modified Caesar cipher – insert cryptanalysis in the alphabet, remove duplicates andleft shift the alphabet 2 times)

Input: meanr radsk lcakh s

Output: MARKE RSAND CHALK S,D,-4

(Diagonal transposition – fold the text in 4 columns, scan in reverse diagonal direction)

the ciphertext messages are organised ingroups of five lowercase letters and the output plaintext messages should be organisedin groups of five uppercase letters.

Ideally, your program should read the ciphertext messages from the input file,produce decryption results in above format, and output the results line by line to anoutput text file. You can also display your results at the standard output. Alternatively,you could choose to read ciphertext messages from the keyboard. There’ll be somereduction of mark though for doing so. Apart from keyboard input, your programshould not require any user intervention to perform the decryption steps.

Programming Language : C++ OR JAVA