
# CSCD27 Assignment 2

The primary goals of this assignment are to improve your understanding of how an attacker could

- Part 1. Eavesdrop communications (Lab 7)
- Part 2. Hijack communications (Lab 8)

Good Luck!

## Instructions

### Submission

Submit on the `mathlab.utsc.utoronto.ca` system your solutions:

- for Part 1: `raw_http.txt` and `raw_https.txt`
- for Part 2: `dos.txt`, `spoof.txt` and `mitm.txt`

```shell
submit -c cscd27f16 -a a2 raw_http.txt raw_https.txt dos.txt spoof.txt mitm.txt
```

### Academic Integrity

___

## Overview and guidelines

In this assignment, we will use our [virtual penetration testing environment](https://github.com/ThierrySans/CSCD27-F16/blob/master/assignments/02/VAGRANT.md)) to demonstrate various attacks on a LAN network (broadcast network). As Mallory, you will first eavesdrop (Part 1) and eventually hijack (Part 2) the communication between Alice, located on the LAN, and Bob (mathlab.utsc.utoronto.ca), located outside the LAN. Alice and Bob exchange login, passwords and sensitive information over HTTP and HTTPS.

As Mallory, you will run your attacks as if you were in a real environment. This means that:

- you do not have access to Alice VM and its files (beyond the initial setup described below)
- you do not have access to the Gateway VM and its files
- you cannot modify the setup of the network

To setup the communication between Alice and Bob, *as Alice*, run the following program:

```shell
vagrant@alice:~$ nodejs /vagrant/alice/client.js
body: Welcome thierry
body: Welcome jing
body: Welcome thierry
body: Welcome jing
...
```

This program never terminates. As described previously, you are not allowed to read nor modify this file. From now on, you will exclusively act *as Mallory*.

## Part 1. Eavesdropping the communication

For this part, make sure that you are able to complete [Lab 7](https://github.com/ThierrySans/CSCD27-F16/tree/master/labs/07).

**Task 1.1 (20 points):** As Mallory, eavesdrop the HTTP traffic sent between Alice and Bob. Isolate the TCP stream that contains login/password and other information. Export it as `raw_http.txt` and submit it as your answer.

**Task 1.2 (20 points):** As Mallory, eavesdrop the HTTPS traffic sent between Alice and Bob. Isolate the TCP stream that contains encrypted content. Export it as `raw_https.txt` and submit it as your answer.

___

## Part 2. Hijacking the communication

For this part, make sure that you are able to complete [Lab 8](https://github.com/ThierrySans/CSCD27-F16/tree/master/labs/08).

**Task 2.1 (20 points):** As Mallory, perform a denial of service attack to disrupt the communication between Alice and Bob. Isolate one or several **relevant** TCP streams that shows the attack and its effect. Export it as `dos.txt` and submit it as your answer.

**Task 2.2 (20 points):** As Mallory, spoof the HTTP communication to return fake information to Alice. Isolate the TCP stream that shows the fake HTTP response. Export it as `spoof.txt` and submit it as your answer.

**Task 2.3 (20 points):** As Mallory, execute a man-in-the-middle attack on the HTTPS communication to obtain the server's response in plaintext. Isolate the two TCP streams that shows your man-in-the-middle attack. Export it as `mitm.txt` and submit it as your answer.

## Part 3. Securing the communication

**coming soon**. This is a bonus points question.