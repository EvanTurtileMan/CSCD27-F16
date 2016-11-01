# CSCD27 Discussion 7

A website requires its users to have passwords with a length of exactly 8 characters long and made of alpha-numeric characters.

7.1 How many passwords are possible?
(26+26+10)^8 = 2.1834e14

7.2 What is the password entropy (n-bit security)?

Now, let assume that we want to crack the password of 1000 users. We want to consider several types of attack:

- dictionary attack on lowercase words and names (~50,000 in english)
	+ 5*10^4
- dictionary attack with a pattern of 4 lowercase words and names (~300,000 in english) followed by a year between 1967 and 2006 (included)
	+ 12*10^6
- brute force attack
	+ (26+26+10)^8 = 22*10^13
- rainbow table attack (when applicable)

## Cracking passwords from the login page

Assuming that we use a password cracking tool that tries different login/password using the login page. We roughly estimates that:

- the login page returns a response in 100ms
- the cracking tool can spawn 100 threads sending such requests

7.3 For all types of attack, how long would it take to:

- speed = 100 threads * (1s/100ms) = 1000 passwords / second

- try one password for all users
	+ (1000/100)steps * 100ms per step = 1 second
- try all passwords for one user
	+ p/1000 seconds
- try all passwords for all users
	+ p/1000*1000 = p seconds

## Cracking unsalted hash passwords

Assuming that we hack into their server and download their (lame) database of unsalted passwords. We roughly estimates that:

- computing a hash takes 10^(-9) seconds
- a table lookup takes 10^(-3) seconds

7.4 For all types of attack, how long would it take to:

- try one password for all users
	+ bruteforce: 10^-9 + 10^-3 seconds
	+ rainbow: 10^-3 seconds
- try all passwords for one user
	+ bruteforce: p * 10^-9 seconds
	+ rainbow: 10^-3 seconds
- try all passwords for all users
	+ bruteforce: p * (10^-9 + 10^-3) seconds
	+ rainbow: 1000*10^-3 = 1 second

## Cracking salted hash passwords

Assuming now that the passwords are salted.

7.5 For all types of attack, how long would it take to:

- try one password for all users
	+ 1000 * 10^-9
- try all passwords for one user
	+ p * 10^-9
- try all passwords for all users
	+ p * 1000 * 10^-9

