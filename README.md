bitkeygen
=========

Bitcoin/Litecoin vanity address generator.
-----------------------------------

Very simple bitcoin/litecoin key/address generator. The objective is to be 
* short: so it can be easily read
* have few dependancies: only needs to be linked to libcrypto (openssl)
* reasonably fast: can be used to generate vanity addresses

Generate a random address and calculate the associated public key.

For linux and mac:

    gcc -o genkey genkey.c -lcrypto -lpthread


To import the private key into the chancoin client:
    
    ./chancoind importprivkey Cxxxxxxxxx "account name"

Usage
-----
````
-C: ChanCoin mode
-s string: generate a public address with the given string
-t number: number of threads to use
-a: allow the string to be anywhere in the public address, not just at the begining
-c: the string should be case sensitive
-l: generate a litecoin key/address pair
-v verbose
examples:
	generate a chancoin private key and its public address
		  ./genkey -C
		  generate a chancoin private key where the public address contains the string 'ToXiC'
		  	   ./genkey -s ToXiC -C -t 8
