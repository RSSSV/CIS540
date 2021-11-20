CIS 540 HMW3

Rahul Vejju	- MID - 76337646
Siddharth Banra - MID - 57150536

Solution 1
----------

MD5: <part 1 f!r5t>

We were able to break this MD5 hash using Hashcat.

hashcat.exe m 0 a 0 givenhash.txt all.txt 

here m 0 indicates that the hashtype is MD5
and a 0 indicates that the attack is of dictionary attack.

"givenhash.txt" has the hashcode which needs to be cracked.

all.txt has the combinations of (rockforyou.txt,pswd.txt,dictionary.txt)which contains combinations of various special characters, numerics and alphabets

result=801338b11e9d13070dc726cbc67ab160 : f!r5t


Solution 2
----------

SHA256: <part 2 Pa55Him>

We were able to break this SHA256 hash over python

python hashcracker.py SHA256 5f22db794e7a7c5219980eb2a492f577804179e30be20c3db28623ed63f19c90 -mode bruteforce -length 7 -chars abcdefghijklmnopqrstuvwxyzABCDEFGHJIKLMNOPQRSTUVWXYZ0123456789 

Output : Pa55Him


Solution 3
----------

BYCRYPT : <part 3 123456789>

We were able to break this BYCRYPT hash by comparing the top commonly used passwords listed in (pswd.txt file) by usung HASHCAT.

The following command was used in hashcat,

hashcat.exe -m3200 -a0 givenhash.txt pswd.txt

Here m is the HASHTYPE,
     a is the ATTACK MODE

$2b$12$2D.0g8MKhJCFNNplEgvWfeGKkk9xy7uq9rZ0KWFrtnX0hMqEpbdQi - Possible algorithms: bcrypt $2*$, Blowfish (Unix)

givenhash.txt has the hashcode which needs to be cracked.
pswd.txt has all the top commonly used passwords list.

We have tried different HASHTYPE like 25600,25800 but we were successfull only at 3200 bcrypt HASHTYPE.

result = $2b$12$O64GAcboleHTqpDeCMwQJe7IwT.6AE1ycBJZGKQGt5EZJv1MoVCt. =  123456789
