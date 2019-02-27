# Blowfish-Algorithm
ALGORITHM:
 
Subkey Generation:
Initialize the values of S box and the P array.
Input key K from the user whose length is between 32 and 448 bits.
Divide K into 32 bit keys. Let number of such keys be n.
For P1 to P18, Pi = Pi exor K(i modulo n)
 
Encryption:
Let the message to be encrypted be a 64 bit number, X.
Divide X into two blocks XL and XR of equal sizes. Thus both XL and XR will consist of 32 bit each
For P=1 to 16
XL = XL XOR Pi
XR = f(XL) XOR XR
Swap XL ,XR
Next i
Swap XL, XR XOR P18
XL = XL XOR P18
XR = XR XOR P17
Merge XL and XL to get ciphertext CT
Function f(X):
Divide 32 bit number X into 4 equal 8 bit parts, a, b, c, d.
val = (s[1][a] + s[2][b])mod 232
val = val exor s[3][c]
val = (val + s[4][d])mod 232
Return val
Decryption:
Inverse the values of the P array, i.e P1,P2...P18 becomes P18,P17...P1
Perform the same process as encryption on the cipher text.
