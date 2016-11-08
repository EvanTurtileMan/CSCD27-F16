# CSCD27 Discussion 8

## Program Insecurity

8.1 What is the difference between a vulnerability and an exploit?
- vulnerability: existence of a bug
- exploit: attack based on a vulnerability

8.2 What is a CVE alert (Common Vulnerability and Exposure) and when is it emitted?
- submission to a database of all known existing vulnerabilities of softwares
- emitted when someone finds out the vulnerability and submit it

8.3 What is a zero-day attack and when does it occurs?
- attack before vulnerability is disclosed

8.4 In a "stack smashing attack",

- what kind of programming error does the attacker want to exploit?
	+ segmentation fault
- what does the attacker aim to overwrite?
	+ return address
- What does the attacker aim to inject?
	+ malicious code (shellcode)
- when the attack succeeds, what privileges does the attacker get?
	+ whatever privileges the running program has

## Operating System Insecurity

8.5 Assuming that the attacker does not have an user account on a machine (nor a physical access to the machine), how can he/she attack it? When the attack succeeds what privileges does the attacker get?
Reverse shell: send a command shell to the attacker; The privileges of the user executing the shell.

8.6 Assuming that the attacker does have an account on the machine (but not a physical access), how can he/she attack it? When the attack succeeds what privileges does the attacker get?


8.7 Assuming that the attacker does have a physical access to the machine, how can he/she attack it? When the attack succeeds what privileges does the attacker get?
