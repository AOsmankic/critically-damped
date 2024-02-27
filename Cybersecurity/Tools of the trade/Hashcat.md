# Hashcat

## Summary
Hashcat is a terminal based password cracker that offers several methods of cracking including: Dictionary, Combinator, Bruteforce, Hybrid, and tons more. 

It is very extensible and has a large commuinty that helps support the tool by supporting custom settings and implementations to provide additional functionality and customizability. 

#### Modes
* Straight
	* Uses a user-supplied wordlist and iterates through the passwords in that wordlist. If the word matches the password exactly, it returns the password.
	* Note: Poplular wordlists include rockyou and sqlmap
* Combination/combinator
	* Takes each word in a user supplied word list and appends every other word in the list one at a time to increase the total number of guessed passwords
	* Can be customized with rules to change how words are combined
* Brute-force
	* Iterates thorugh every possible combination of characters until the password is guessed
	* Takes a very long time
	* Similar to mask-attack which is liek a brute-force, but lets you designate the characters (which chars should be used, min number of special chars, etc)
* Hybrid Wordlist + mask
	* Defines a user defined ranche of characters(mask) to words in a wordlist
	* Syntax - https://hashcat.net/wiki/doku.php?id=mask_attack
* Hybrid Mask + wordlist
	* Same as Hybrid Wordlist + Mask, but prepends the mask instead of appending


##### The corrisponding attack code for each attack
[ Attack Modes ]
  0 | Straight
  1 | Combination
  3 | Brute-force
  6 | Hybrid Wordlist + Mask
  7 | Hybrid Mask + Wordlist


#### Important Files
Hashcat uses some important files that are important to know about, such as **~/.hashcat/hashcat.profile** that contains a cache of any passwords cracked by hashcat and **~/.hashcat/hashcat.dictstat2** that is a cache that contains the dictionary of words used by hashcat (its a performance thing)

#### Common Hash Indicators
Since hash cat is commonly used to help crack files containing password hashes, linux shadow files are a common target. It helps to understand the format of this file. The hashes are seperated by username and contain a hash indicator (\$#$) indicating what type of hashing algorithim is used for the corrisponding hash. The following are common hash indicators
* \$1$ - MD5
* \$5$ - SHA-256
* \$6$ - SHA-512

## Requirements
Modern GPU

## Usage

Usage: `hashcat -m {hash_type_num} -a {attack_type_num} -o {output_file} {hash_file} {wordlist}`
Descirption: Attempts to crack the hashes in file {hash_file} using the attack type associated with the number {attack_type_num} and the wordlist {wordlist} then outputs any results to {output_file}. To view the passwords, simply view the {output_file} when the program completes (cat {output_file})

Usage: `hashcat -m {hash_type_num} -r {custom_rules} -a {attack_type_num} -o {output_file} {hash_file} {wordlist}`
Descirption: Same as the prior command, but using a custom rules file {custom_rules}


## Tool Tags

Tag Name | Tag Value
-------- | --------
Classification | Cracking
Cost | Free
Type | Open Source
Compatibility | Linux, Windows
Usage | Terminal
Website | https://hashcat.net/hashcat/