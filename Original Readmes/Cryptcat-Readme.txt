cryptcat = netcat + encryption

Cryptcat is the standard netcat enhanced with twofish encryption. 

Twofish is courtesy of counterpane, and cryptix. We started with the 
Java version of twofish from cryptix, converted it to C++ (don't ask why), 
and enhanced it by adding CBC mode and the ciphertext stealing technique 
from Applied Cryptography (pg. 196) 

How do you use it?

  Machine A: cryptcat -l -p 1234 < testfile 
  Machine B: cryptcat <machine A IP> 1234 

This is identical to the normal netcat options for doing exactly the 
same thing.  However, in this case the data transferred is encrypted. 



Changes -- been putting these in Changelog file...

Since release alot of people have been submitting changes (many times
for the same thing).  I've been doing my best to keep up, we are trying
to get this up on sourceforge, but there seems to be some sort of 
"approval" process that makes it unclear if that will actually happen.

So, if you have submitted something, and its not here, let me know.  If you've
submitted a change, and its here with someone else's name, that just means 
someone else got the same change in before you.

If you have a change, let me know what name if any to include with
the change.
