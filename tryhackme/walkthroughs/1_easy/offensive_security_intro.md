# Offensive Security Intro
Hack your first website (legally in a safe environment) and experience an ethical hacker's job.

## Task 1 - What is Offensive Security?
"To outsmart a hacker, you need to think like one."

This is the core of "Offensive Security." It involves breaking into computer systems, exploiting software bugs, and finding loopholes in applications to gain unauthorized access. The goal is to understand hacker tactics and enhance our system defences.

### Beginning Your Learning Journey

In this TryHackMe room, you will be guided through hacking your first website in a legal and safe environment. The goal is to show you how an ethical hacker operates.

Our labs can also be reverted to their initial state, so don't be afraid to break the machine. Experiment as much as you like, we got you covered!

### Answer the questions below
Which of the following options better represents the process where you simulate a hacker's actions to find vulnerabilities in a system?
- Offensive Security
- Defensive Security

> Offensive Security

## Task 2 - Starting the Lab
Here at TryHackMe, we use Virtual Machines to create simulated environments that serve as practical complements to rooms.

In this room, we have prepared a fake bank application called FakeBank that you can safely hack. The virtual machine with the application should start automatically for you. If it doesn't, click on the Start Machine button below.

Virtual Machine	
> Start Machine

Your screen should be split in half, showing this content on the left and the newly launched machine on the right. If you hide it later, you can always click on the Show Split View button at the top to display it again. You should see a browser window showing the website below:

![fake bank website](https://tryhackme-images.s3.amazonaws.com/user-uploads/63588b5ef586912c7d03c4f0/room-content/63588b5ef586912c7d03c4f0-1716285774320)

### Answer the questions below
What is your bank account number in the FakeBank web application?
> 8881


## Task 3 - Your First Hack
**Briefing**

Our goal is to find a way to hack the FakeBank application to steal money. For that purpose, they have provided us with an account in the bank, just as if we were a regular user.

One of the easiest ways we can try to hack the application is by finding hidden features in the application. Sometimes, applications will expose sensitive functionality to users via secret URLs. If we can find such URLs, we might be able to perform actions that a regular user is not supposed to do.

To find hidden URLs, we will use a tool called `dirb`. This tool uses a **brute-force** approach, by taking a **list of potential page names** and testing one by one if they exist in your website. This approach works because people use predictable names a lot of times.

**Opening A Terminal**

A terminal, also known as the command line, is a program that allows us to send text-based commands to the computer. A lot of hacking tools, including dirb, need to be executed from a terminal.

On the machine, open the terminal by clicking on the Terminal icon on the right of the screen.

**Using dirb To Find Hidden Website Pages**

Using dirb is quite simple. Using the terminal, write the `dirb` command followed by the URL of the website you want to brute-force. Be sure to press `ENTER` in your keyboard to execute the command:

```bash
dirb http://fakebank.thm
```

The command will take a minute to run and show you an output similar to this:

*Dirb command to brute-force website pages*
```bash
ubuntu@tryhackme:~/Desktop$ dirb http://fakebank.thm 

-----------------
DIRB v2.22    
By The Dark Raver
-----------------

START_TIME: Thu Apr 17 16:29:52 2025
URL_BASE: http://fakebank.thm/
WORDLIST_FILES: /usr/share/dirb/wordlists/common.txt

-----------------

GENERATED WORDS: 4610                                                          

---- Scanning URL: http://fakebank.thm/ ----
+ http://fakebank.thm/bank-deposit (CODE:200|SIZE:4663)                        
+ http://fakebank.thm/images (CODE:301|SIZE:179)                               
                                                                               
-----------------
END_TIME: Thu Apr 17 16:29:59 2025
DOWNLOADED: 4610 - FOUND: 2
```
  
The output of the command might look a bit intimidating, but here's a simple breakdown of what is reported:

- The first section of the output tells us the URL_BASE we scanned, which is just the URL we gave the tool. It also shows the location of the wordlist file used by the tool, which contains common page names that will be tested during the brute-force attack. In this case, the tool uses the default wordlist included with the tool, located at `/usr/share/dirb/wordlists/common.txt`. There's a copy of the `common.txt` file in your desktop as well, if you want to explore it.
- The lines starting with a `+` sign are the results of the scan. In this case, dirb was able to find two URLs for you. Try opening them in the machine's browser! You might find something interesting.

### Answer the questions below
Dirb should have found 2 hidden URLs. One of them is `http://fakebank.thm/images`. What is the other one?

> `http://fakebank.thm/bank-deposit`


## Task 4 - Adding Funds to Your Account
You should have found a secret page that allows you to add funds to a bank account (`http://fakebank.thm/bank-deposit`). Type the hidden page into the FakeBank website using the browser's address bar.

![fake bank website demo - hidden page url](https://tryhackme-images.s3.amazonaws.com/user-uploads/5ed5961c6276df568891c3ea/room-content/5ed5961c6276df568891c3ea-1744913214979.png)

From this page, you should be able to add funds to your bank account (remember your bank account number is 8881). Let's add $2000 to it:

![fake bank website demo - adding funds](https://tryhackme-images.s3.amazonaws.com/user-uploads/5ed5961c6276df568891c3ea/room-content/5ed5961c6276df568891c3ea-1744913360467.png)

If you managed to add $2000 or more to your account, you should be able to see your new balance reflected on your account page. Press the `Return to Your Account` button at the end of the deposit receipt to go there now and confirm you got the money!

### Answer the questions below
If your balance is now positive, a pop-up should appear with some green words in it. Input the green words as the answer to this question (all in uppercase).

(You may need to hit Refresh if you closed the pop-up already)

> BANK-HACKED

---

Ref: [Offensive Security Intro](https://tryhackme.com/room/offensivesecurityintrokK)
