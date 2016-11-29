# CSCD27 Discussion 10

## Protection

10.1 What is the concept of defensive programming?

10.2 Explain why type-safe programming languages are less prone to buffer overflow vulnerabilities?

10.3 What is the difference between testing and penetration testing?

10.4 Explain the fundamental differences between these 4 protection again buffer overflow:

- Secure standard libraries (LibSafe)
	+ software layer that intercepts all function calls made to library functions known to be vulnerable
- Canaries (GCC stack protection)
	+ random canary
	+ terminator canary
- Address Space Layout Randomization (ASRL)
	+ shuffling the stack layout every execution
- Executable space protection (tagged architecture)
	+ add extra executable bit for each address

## Malware

10.5 What is the difference between the payload and the infection vector?
- **payload**: program that performs the malicious operation
- **infection vector**: the method to spread the payload

10.6 What are the common techniques use to make malware undetectable by anti-viruses?
- permutation
- compression
- encryption: good against file-based check
- obfuscation

10.7 Defines these concepts related to modern malware:

- RAT (Remote Administration Tool): payload
- Malware packer: make malware undetectable
- Exploit Bundle: infection vector
- Bulletproof host: hides the attacker
	+ hosted in country with low cyber-security
	+ p2p connection
