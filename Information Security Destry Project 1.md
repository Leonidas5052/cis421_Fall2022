# Project 1

We both worked on this project independently for a while before teaming up so some of the challenges are the same as each others.


****************** General Skills **************************

Challenge Name: Obedient Cat

Category: General Skills

Point Value: 5

Challenger: Destry

Challenge Description: You are given a file and you need to find the flag.

Steps Taken:

    - I opened the file in the webshell and found the flag in plaintext. 
    
    - Copied and validated.
    
    - Not much to say about this one.
    
    
    
********************************************


Challenge Name: what's a netcat?

Category: General Skills

Point Value: 100

Challenger: Destry

Challenge Description: I was given a website address and a port number and told that in order to get the flag I would have to connect to the website at the port number.

Steps Taken:

    - Looked up netcat online, description was pretty hard to make out but I got that the command started with "nc".
    
    - Looked up "nc" using "man" and read a bit more about it
    
    - Ran "nc jupiter.challenges.picoctf.org 41120" in the terminal and the server responded with the flag


********************************************


Challenge Name: Nice netcat...

Category: General Skills

Point Value: 15

Challenger: Destry

Challenge Description: The command $ nc mercury.picoctf.net 21135 returns seemingly random numbers that have something to do with the flag.

Steps Taken:

    - I ran the command and had a look, random numbers as expected, looks like ascii values
    
    - Redid the command, but set it to dump to a new file called "char.txt"
    
    - Created a simple python program as follows
    
f = open("char.txt","r")
s = f.read().split("\n")
for x in s:
        print(chr(int(x)))
     
     
     - Had to manually remove some spaces, but otherwise the flag worked


********************************************


Challenge Name:Based

Category: General Skills

Point Value: 200

Challenger: Destry

Challenge Description: You are given a netcat connnection and when you connect you get asked to translate a string of numbers into a word in a limited amount of time.

Steps Taken:

    - connected to the address listed in the description, first prompt is asking me to translate a number of 8 digit strings of ones and zeroes. I wasn't prepared to do that in the time limit, so i copied the numbers into notepad and translated them into base 10, looks like ascii values again: 
    0110 0011 64 + 32 + 3   = 99 
0110 1111 64 + 32 + 15  = 111
0110 1101 64 + 32 + 8 + 4 + 1 = 109
0111 0000 64 + 32 + 16 = 112
0111 0101 64 + 32 + 16 + 4 + 1 = 117
0111 0100 64 + 32 + 16 + 4 = 116
0110 0101 64 + 32 + 4 + 1 = 101
0111 0010	64 + 32 + 16 + 2 = 114

    - looked up ascii values online and found a good reference chart to look at @ https://www.asciitable.com/
    
    - I could translate them, but it still took a few tries to do it quick enough (the word changes every time, so knowing the previous word doesn't help)
    
    - beat the first one, another prompt, same as with the binary numbers but the numbers are octal this time
    
    - after a few more tries before beating both the binary and octal challenges consecutively next prompt is the same as the previous two, but with hex
    
    - the main challenge was just reading the code fast enough, But after a few more tries I got all three challenges in a row and the server gave me the flag.


********************************************


Challenge Name: Lets Warm Up

Category: General Skills

Point Value: 50

Challenger: Destry

Challenge Description: Description asks what a word would start with if the hexidecimal code started with 0x70.

Steps Taken:

    - Still had ascii chart up from previous challenge, chart said 'p'
    
    - put the flag in as 'picoCTF{p}'
    
    - just to see what would happen, it worked


## General Skills




Problems 19 and 20 are binary explotation

## Problem 1 What is a Net Cat (100 Points)

The goal of this project is to understand how the nc (NetCat) Command works.  You are given an ip and a port and use those with the nc command to get the key.

### Steps taken
1. Look up the address given in the problem.  It gave a download for the code of a webpage.  The code had nothing of note.

2. Look up what NetCat was.  It is a way to access ip addresses from through specific ports if you know what they are.

3. Try the command.  It worked.  I got a key and gained 100 points!

## Problem 2 Majikarp Ground Mission (30 points)

The goal of this project is to use Linux commands to move between the directories to look for a key in the directories.

### Steps Taken
1. I attempted to log into the ctf-player instance.  I first did it through the initial login space.

2. I then looked up a guide online to see what it was that I was not doing right, then saw that they used the ssh command to log in.  Oops...

3. I used the ssh command and entered the password that was given to me.  This brought me to a place where I was thrown into the middle of a directory.

4. I used ls to look around, and saw a 1of3 file for the key, then copied that down to be used once I found all three parts.

5. I opened an instruction file which said to use the bash command.  After using it, I noticed that I was able to move back through the directories to get to the root as they call it.  But first I moved using cd .. and saw number 3of3.  I opened it and copied it down.  Now to find 2of3.

6. I continued to use cd.. until I hit 2of3 like 5 directories later.  At this point I was able to open and copy the last part of the key and submit it.  30 more points.

## Problem 3 Wave a Flag (10 Points)

The goal of this project is to learn to invoke help tools using the command -h

### Steps taken
1. I looked through the hints to see if there was a way to get some help, and hint 2 gave me a download link to get the file on the webshell.

2. After signing into the webshell, I used wget to get the file on my webshell and then ran the file using a ./

3. It then said to use a -h to invoke some help.  This gave me the key and I scored another 10 points!

## Problem 4 Tab Tab Attack (20 Points)

The Goal of this project was to learn how easy Tabing would make our lives when attempting to move through directories really quickly

### Steps taken
1. I looked at the hints to see if there was a wget link that I could use.  I really needed to figure out how to find those sooner.  That was half the struggle for this project.  

2. There was a link though so I downloaded the zip file onto my own laptop and attempted to make use of it.  I unzipped the file and tabbed through it to learn that the file was an executable only usable on a Linux machine.  Curse my Windows laptop.

3. I then looked up a lot of resources to figure out how to download the file onto my webshell.  Did not go well.  Apparently I am just really bad at downloading files.

4. I then remembered to try rightclicking the link.  That got me a link that I could use wget on.  Right-click the link, then select copy link.  I use it all the time for other things, I do not know why this was so hard.

5. After I used wget on the link I got a corrupted file.  I didn't even know it was corrupted.  I spent like 10 minutes playing around with the file to then look up ls colors and learn that red meant it was probably corrupted.

6. I then redownloaded the file, not corrupted this time.  I then unziped the file and tabbed through the directories to get to the last one.

7. Run the executable and *ZAP!*.  20 points.

## Problem 5 Lets Warm Up (50 Points)

The goal is to be able to convert hex to ascii.  I learned that I do not know how to do this.

### Steps Taken
1. I had a hex code. 0x70.  Now I needed to change it to what it represented.

2. I looked it up and got p so I entered, "picoCTF(p)"...  I was so confused when it was wrong.

3. I then struggled for about 5 minutes and looked up a guide to realize that I entered the flag in the wrong format and that is why I got it wrong...

4. I learned how echo -e worked though.  I did echo -e "\x70" to figure out the ascii code.  It was p

5. I then figued out what I did wrong and entered the right flag... 50 points.

## Problem 6 Serpentine (100 Points)

The Goal is to run a python program that will give you the flag when the program properly runs.  However the program is slightly broken and you have to edit the program to fix it.

## Steps Taken
1. This was a really easy challenge since I have a lot more experience in Python than most any other programming language. My first step was to download the program and run it.

2. I saw three options to more onwards so I tried the get flag option.  It then said that the source code was broken and that I had to fix it.

3. I opened the source code with less.  I then started reading kinda quickly through the program to see where the the error was.

4. There was a print_flag() function which printed the flag with the key enkidu.  I love that.  true nerd stuff.  Also serpentine. Nevermind.

5. From here there are two ways to solve the problem.  The way they want you to solve the problem.  Fix the program so that when you run the get flag option in the program you get the actual flag.  The second way would be to have the program run the print_flag() function immediately.  I did it the way that they wanted you too.

6. After fixing the code, I found the flag by running the program again.  Then with flag in hand on the road more traveled, I earned 100 points.  Easy.

## Problem 7 PW Crack 3 (100 Points)

The goal is to find the password to unencrypt a file through the use of some snooping around.

### Steps Taken
1. The first step was to download all the files.  Right-click, copy link address.  Done.

2. Then I opened the python program, since the problem mentioned that the passwords would be placed somewhere in there.

3. There was a cheeky message saying that the password would not be found in the program, but I scrolled down anyways and found some passwords to try.

4. I copied the passwords down and tried them one at a time until the fourth password worked.  I got the key and 100 points!

## Problem 8 convertme.py (100 Points)

The goal was to run a program and enter the correct conversion of decimal to binary to get the flag.

### Steps Taken
1. I downloaded the code using the right-click, copy link address method.

2. I then ran the program and found out that the number that I would need to convert was 99.

3. I calculated the conversion by hand.  It was good practice and I was wondering how fast I would be at it.  I was kinda slow compared to how fast I would usually be.

4. The conversion equalled 1100011.  I entered that, got the flag, and another 100 points!

## Problem 9 flag_shop (300 Points)

The goal is to go shopping at a flag store.  I don't really know what that means, but if the store asks for my credit card number, I'm leaving.

### Steps Taken
1. So the shop kinda scams you.  The flag cost $1000000 and you only have $1100 to work with.  I also know very little about the C language except the little bit that we have gone over in our arduino class.  This will be tough.

2. The first thing I did was less the c code that they gave so that you could look at the source code without being able to edit it as a cheap solution.  The actual code with the flag is on a server.  Running the code not on the server will not net you a flag, but is a great spot to test things out.

3. I learnt that by trying to scam the server by changing the source code that we were given, did not work, obviously.

4. I then looked at the hint and it said something about how big number are weird for the code.  I did not really understand what they were going for, but I was determined to get this.

5. At this point I was wondering if I was a bit out of my depth, but then I remembered something about ints in the c language.  They can only be a certain number of bits based on the device that it is on.  The server and source code could go up to a 32 bit number which is around 2.2 billion which I found on this website. https://stackoverflow.com/questions/62618142/why-does-c-programs-return-a-code-instead-of-the-answer-when-its-too-big

6. I then opened the server and entered a big number on the option to buy fake flags to try and see if I could go around back to a negative number, then broke the server, was kicked off and had to run it again.

7. I then compiled the source code for a safer testing enviornment.  I ran the code and tried to enter 2200000000 as the number of flags that I wanted to buy but the code wouldn't let me.  It simply would not work.

8. The calculator has to come out now.  I looked back through the source code and found out that the way that it calculates the cost was through multiplying the amount that you want by 900.  The website I had earlier had someone get a negative number by multiplying some numbers together, so I did 2200000000/900 which equals 2444444.444.

9. I then used a slightly higher number as the number of flags that I wanted 2500000.  This then gave me a negative cost of the flags, which then gave me money instead of me paying money.

10. I then used the funds that I acquired legally, and not by hacking, to purhcase the correct flag at the store.  300 points!!! Easy.

## Problem 10 PW Crack 5 (100 Points) 

The goal is to take a very long list of possible passwords and do one of two things.  Sit there for an entire year until you guess the right password, or you use Linux commands to get the password.

### Steps Taken
1. The first thing I did was right-click, copy link address, wget the files.

2. I read through the source code of the password checker to see how they determined if you gave the right password.  Turns out there is a two-step process to check for the password.  The First is a simple if statement.  The second is the fact that the decrypter requires the password as part of the decryption.  No cheating the system by changing the code, unless I'm just that good, which I'm not.

3. Because we had a file with all possible passwords, I tried to pipe in the whole dictionary.txt file into the python code as the input.  Did not work as intended.  Just got a fail from the code.

4. Next I tried to look at the different parts of the code like the hashs for the passwords.  I could not understand those at all.  They made no sense.

5. The passwords were hexcodes.  So I was trying to figure out how to transform decimal form to hex in python with out too much modification to the output.  It did not go well.

6. I finally tried to read the hints, and they basically said that I should open the dictionary file in the python code and run it after striping the white space.

7. Based on the hint I changed the pw_check function to open the password file, and input line by line, after removing whitespace, the different passwords until it gave the right one.  It only gave an output when it had the right password.  I still don't know what the password is, but I had the key. 100 points gathered!



******************* Web Exploitation *************************

## Web Exploitation

## Problem 11 Scavenger Hunt (50 Points)

The goal of this problem is to be able to look around a website and try to look around and find the key for the website.

### Steps Taken
1. The first thing that I looked at was the source code.  It is split into three files.  The first is an html file which hosts the main bulk of the website code.  The second is some javascript which has some formatting in it.  The third is some css which makes the website look nice.

2. The first part of the key is found in the html section.  I copied and pasted that into the answer section.

3. The second part of the key is hidden in the css portion.  I copied and pasted that next to the first part.

4. The last part is what I am having trouble with.  The hint said that there was no need to brute force anything, but I do not know where to look for the last part of the key.  The javascript section of the code talks about how a part of the website might have not been indexed by google.  Which means that it is not seeable on google.

5. I tried to use wget on the website link, but that only got me the index.html file which I already had access too.

6. I looked up how to stop google from indexing a webpage and found robots.txt.  I do not know how it works so I looked up a writeup from Hayden Housen and apparently I just add it to the end of a website url.  Why.

7. From the website that we found we are on an apache server.  The heck does that mean.  Back to the writeup.  The heck is .htaccess.  Okay, a google search later, .htaccess is a second way to access directories of an apache server.  Good to know. Now to enter that in... and now it's talking about macs.  Fun.

8. I still have no idea what is happening.  Back to the writeup.  I looked at the writeup and it said that on macs there is a hidden file system, called DS_store.  It is created everytime you open a folder with finder on a mac.  This service was hacked once by a Chinese hacker because it stores folder names and the files around them.  So a hacker with access to this can get into private files that they shouldn't be able to access.

9. I add .DS_store to the back of the url, find the last part of the key.  This was an interesting experience, but I got another 50 points, thanks to writeups. yay...

## Problem 12 Web Exploitation (100 Points)

The goal of this is to look at a website and see if you can exploit it to get the key somehow.

1. The first thing I did was open the website and look around the source code.  There were hidden files that I could not look at and I wasn't sure how to access them, one was called login.php, but I could not access any of them so I ignored them.

2. The second thing I did was to just try to login with any old password and hope I got lucky, which I didn't.  However, it did expose a js file called secure.js.  Which had the username and password to login to the website. It was very secure.

3. I tried the username and password on the website, misspelled it once, then got it the second time by copy pasting it. Got the key and an easy 100 points!  Spending a semester working on a website really does teach you where vulnerabilities might be.

***********************************

Challenge Name: Cookies

Category: Web Exploitation

Point Value: 40

Challenger: Destry

Challenge Description: The link to a website is given and somehow you are meant to figure out the best "cookie". Presumably this has something to do with getting the flag.

Steps Taken:

    - Opened up the inspect console and poked around, found a tab for cookies, but there's only one called "name" and it's not telling me anything useful.
    
    - Tried using website as intended to see what would happen. Things that aren't cookies provoke a "that's not a valid cookie response". "Chocolate Chip" and "Peanut Butter" change the value of the aformentioned web cookie. "Chocolate Chip" makes it 1, and "Peanut Butter" makes it 5.
    
    - Poked around in the inspect tab for a while. Not much progress.
    
    - Searched online for help  found this page that gave the answer https://github.com/vivian-dai/PicoCTF2021-Writeup/blob/main/Web%20Exploitation/Cookies/Cookies.md
    
    - edited the value of the web cookie to 18 and the webpage displayed the flag.


********************************************



Challenge Name: Some Assembly Required 1

Category: Web Exploitation

Point Value: 70

Challenger: Destry

Challenge Description: There is a link to a webpage with a input that claims to be able to check if you have the correct flag.

Steps Taken:
    - Given the name, I opened inspect to see if I could find a webassembly script or something, there was in fact a js page that looked an awful lot like assembly.
    
    - I copied the code into a text editor and tried to make heads or tails of it, but I wasn't getting anywhere quickly.
   
    - Fortunately with a quick google search I found out I could enable webassembly support in google inspect and that allowed me to js format the code to make it more readable.
    
    - I spent a few hours trying to reverse engineer the code. I thought the flag was somehow encrypted in an array on the page 
    
    - in particular, I knew that this code: 
    
    const _0x478583 = -parseInt(_0x371ac6(0x1eb)) + parseInt(_0x371ac6(0x1ed)) + -parseInt(_0x371ac6(0x1db)) * -parseInt(_0x371ac6(0x1d9)) + -parseInt(_0x371ac6(0x1e2)) * -parseInt(_0x371ac6(0x1e3)) + -parseInt(_0x371ac6(0x1de)) * parseInt(_0x371ac6(0x1e0)) + parseInt(_0x371ac6(0x1d8)) * parseInt(_0x371ac6(0x1ea)) + -parseInt(_0x371ac6(0x1e5));

    was being used to compare user input against what was in this array 

    - const _0x402c = ['value', '2wfTpTR', 'instantiate', '275341bEPcme', 'innerHTML', '1195047NznhZg', '1qfevql', 'input', '1699808QuoWhA', 'Correct!', 'check_flag', 'Incorrect!', './JIFxzHyW8W', '23SMpAuA', '802698XOMSrr', 'charCodeAt', '474547vVoGDO', 'getElementById', 'instance', 'copy_char', '43591XxcWUl', '504454llVtzW', 'arrayBuffer', '2NIQmVj', 'result'];

    
    - I also knew that numbers like these _0x478583 were variables, and numbers like these 0x1eb were hex numbers in the high 400s. 
    
    -  this constant _0x371ac6 referenced a function that subtracted 470 from those big hex numbers, conveniently making all of them within the length of the array, and then returned the array item that the hex number corresponded to after the subtraction
    
    - using a web tool to simulate how parseInt() would work on the different strings, I came up with:
    -       -504454 + 2 + -1195047 * -275341 + -nan * -23 + -1699808 * nan + nan * 43591 + -nan;
    
    - adding all that together doesn't work, it was all a dead end. So I looked online for help
    
    -  found this page explaining it https://github.com/Dvd848/CTFs/blob/master/2021_picoCTF/Some_Assembly_Required_1.md
    
    -  what was described in that link was more than I had to do
    
    -  after you use an online deobfuscator you learn that the code sends the user input to another page for comparison.
    
    - by downloading the assembly code "script.wasm" at the link you can open it using less and the flag is at the bottom of the page
    
    - there was some other steps about converting the "script.wasm" into a .wat file to make it easier to read, but it doesn't do anything except make a blank file, and the flag is in "script.wasm" in plaintext anyways.


********************************************


Challenge Name: Most Cookies

Category: Web Exploitation

Point Value:150

Challenger: Destry

Challenge Description: You are given a link to a website and a link to the source code the server runs on. This challenge is very similar in looks to a previous challenge I did earlier called 'Cookies'.

Steps Taken:

    - looked at the server source code, I can read python but this is harder to decipher because I'm not used to programming python servers. I could tell they added more valid cookies though, and that the best cookie is picked at random, can't tell if it's randomized everytime or just per session.
    
    - Tried every single cookie brute force style, nothing (there were only 28)
    
    - opened inspect, there were three cookies; "_ga", "name", and "session".
    
    - Changing "name" like in the 'Cookies' challenge doesn't seem to do anything
    
    - "session" changes everytime, i figured maybe if I copied one of the sessions and pasted it in after the reset and tried brute forcing the cookie again, it wouldn't reset the random cookie and I would get it eventually, but that ultimately didn't work.
    
    - looked at the python code again, looks like it just gives you the key if it detects the session id is "admin", tried changing the session cookie value to "admin". That didn't work either.
    
    - looked up the solution. Found one by "cleibox" @ https://github.com/vivian-dai/PicoCTF2021-Writeup/blob/main/Web%20Exploitation/Most%20Cookies/MostCookies.md Apparently I was on the right track for the most part about tricking it into think I was the "admin" but i needed to do some complicated stuff with flask encrypting and I ran out of time.
    
    - did not complete

****************** Cryptography **************************
## Cryptopgraphy
## Problem 13 The Numbers (50 Points)

I have a image with some numbers on them and I have to figure out what the key is from the numbers. 

### Steps Taken
1. The first thing I do is open the file that they gave use to download.  The numbers range from 1 to around 20.  That basically tells me what I have to do to solve this.

2. I take out a notepad and write the alphabet down and number each letter to figure out what is what.

3. I compare them and get the key written down.  Easy 50 points.

## Problem 14 Easy1 (100 Points)

You are given a key and the encrypted flag and have to decrypt the flag.

### Steps Taken
1. Already I know that the first thing to do is read the table that we were given which shows how the cryptography pad works.

2. I downloaded the table and look through it to see what is on it, and I have a pretty good idea of what is expected to be done.

3. The next step is to start comparing the key to the garbled mess of letters that we are given, except I decide instead to go to the first website I find when I google, decrypt one time pad, go to this url: https://www.boxentriq.com/code-breaking/one-time-pad, enter the key and the encoded phrase and get the key.  Easy 100 points.

****************************************************

Challenge Name: Pixelated

Category: Cryptography

Point Value: 100

Challenger: Destry

Challenge Description: Two images are given. Somehow you are supposed to get a flag from them.

Steps Taken:

    - Downloaded both to my local device. Opened them both with a text editor and did a quick search for 'picoctf' but nothing came up.
    
    - opened them both with Gimp and tried various thing like stacking them and merging them, or stacking them and making them semitransparent, rotating them and merging them. Nothing worked.
    
    - finally had to look up the solution on https://github.com/Dvd848/CTFs/blob/master/2021_picoCTF/Pixelated.md
    
    - supposedly you are supposed to convert both images into arrays and add them together into a single image.
    
    - didn't matter anyways, I spent two hours trying to figure out how to open up images in the web shell and nothing was working so the solution isn't helping me.
    
    - opened the outputted combined images with less and i'm not even sure it's a valid png file when compared to the other two.
    
    - from this point forward I am going to have to implement a timer because im only 4 challenges deep, one of which I found out afterwards doesn't count towards my total, and Ive already spent nearly 15 hours on this project





**************** Forensics ****************************

## Forensics

## Problem 17 Packets Primer (100 Points)

The goal is to look at a group of packets that are given to you and find the key inside of those packets.

### Steps Taken
1. It said that downloading wireshark is a good way to examine packets in the hint so I downloaded wireshark.

2. I opened the download with wireshark and started to snoop around.  I had very little ideas of what I was looking for.  There were some phrases that I could see that were kinda telling me to look at specific packets.

3. After looking around the packets I found the flag hidden in a set of bytes translated for me to look at and found a key.  100 points acquired.

## Problem 18 So Meta (150 points)

I was given an image and have to find the key hidden in the image somewhere.  The image is a bunch of half circles and circles.

### Steps Taken
1. I watch too many fnaf theory videos.  The first step that I decided to do for the image was turn it into a text file.  I used control-f to search for pico and at the end of the new text file, I found the key.  Easy 150 points.

*****************************************
Challenge Name: Matryoshka doll

Category: Forensics

Point Value: 30

Challenger: Destry

Challenge Description: You are given an image of a Matryoshka doll and have to find some way to get a flag from it.

Steps Taken:

    - Downloaded the image gave it a look in windows photos, nothing out of the ordinary.
    
    - Found an online metadata viewer @ https://www.metadata2go.com/ looked at the metadata for a while, nothing out of the ordinary except even though the file had the jpg extension the metadata viewer said it was png.
    
    - Changed the extension name to png and opened it again in windows photos, nothing changed.
    
    - looked at the image in notepad, searched for the word "pico" but also nothing.
    
    - looked up the solution. Found one by 'ZeroDayTea' and 'Killer Queen' @ https://ctftime.org/writeup/28156
    
    - The solution involved using binwalk to extract compressed files hidden in the image. You would extract the file, descend one level into the directory where there was another image with a file compressed inside of it. I repeated the process four times til i got to 'flag.txt'
    
    - opened 'flag.txt'. The flag was in it.


******************** Binary Exploitation ************************


Challenge Name: Stonks

Category: Binary Exploitation

Point Value: 20

Challenger: Destry

Challenge Description: You are given a server to connect to with nc and a download for C code and told to exploit it somehow to get the flag.

Steps Taken:

    - Looked at the code first, looked like there is a file on the server with the key that gets read into memory when the program is loaded up.

    - Opened a connection with the webserver, first prompt asks if you want to buy stocks, or look at your stocks, i chose to look at my stocks. I had none, and the program ended.

    - Tried buying stocks, no matter what you input it just spits out a ton of random stocks and ends the program. There is no account memory, so nothing I do carries over to the next session.
    - user buffer is 301 memory addresses long, tried sending it +300 characters. Same output as usual, it just ignores everything past the first 301 characters.
    - Looked up a write up. Found one by " Abraxus" and  "kernelarmy" @ https://ctftime.org/writeup/28935
    - They used a script to do it, but what I ended up doing was sending a ton of "%x" and it dumped the memory as hex code
    - threw the hex code into an online decoder @ https://onlinestringtools.com/convert-hexadecimal-to-string
    - had to manually remove some of the useless values and invert the characters in the flag, but otherwise the flag worked.


********************************************


Challenge Name: basic-file-exploit

Category: Binary Exploitation

Point Value: 100

Challenger: Destry

Challenge Description: Given the source code of a file with the flag redacted, and a netcat connection, exploit it to gain the flag.

Steps Taken:

    - looked at the source code first, searched for "flag"
    
    - found a section of code that essentially said if the user entered a "0" under certain circumstances the program would return the flag.
    
    - if ((entry_number = strtol(entry, NULL, 10)) == 0) {
    puts(flag);
    fseek(stdin, 0, SEEK_END);
    exit(0);
  }
    
    - Played with program a bit, you can enter data into a database, read data out of the database, or exit the program.
    
    - Entering data doesn't allow you to use 0 except in a string to be saved.
    
    - Tried to read entry "0" in the program and I got the flag.


*********************Reverse Engineering ***********************

## Reverse Engineering


## Problem 15 Vault-Door Training (50 Points)

You are trying to break into a labratory and you need the passwords that let you through each door.  However, the passwords are not known, only one person managed to get anything, and it was the source code to the doors.  I need to look through the source code to figure out the password.

### Steps Taken
1. I downloaded the code that was given to me.  It was a simple program that would return the key if I found the password.  I think.

2. I dove into the source code and looked to find the password.  I find it.  So I back out, compile the program and try to input the password.  It does not work. I have no idea why.

3. I say forget it, look back through the code and realize that the password is the key that the program will return to you.  I take the password, copy picoCTF{}, paste the password between the curly braces, and hit enter.  50 points gained.

## Problem 16 Safe Opener (100 Points)

The Goal of this problem is to take some code that is meant to help the person remember their password.  It shows if you enter the correct password so it checks if you have the right password.

### Steps Taken
1. I downloaded the code that was given.  It was a Java program so I tried to use less to see the source code.

2. In the source code I found an encrypted key in 64 bit.  I do not really know why it would be in 64 bit, but I copied it down and saved it for later.  I later found that it will take your entered password, encrypt it and check if it works the way it should.

3. I decided to decode the encrypted key with a Base64 decoder.  I used this website: https://www.base64decode.org/ and got the correct key.  I checked it with the program, it worked and I submitted it as a key.
 
 
**********************Hardest Difficulty**************************************************************

Challenge Name:

Category:

Point Value:

Challenger: Destry

Challenge Description:

Steps Taken:

    -
    
    -
    
    -


********************************************


Challenge Name:

Category:

Point Value:

Challenger: Destry

Challenge Description:

Steps Taken:
    -
    
    -
    
    -


********************************************


Challenge Name:
Category:
Point Value:
Challenger: Destry
Challenge Description:
Steps Taken:
    -
    -
    -


********************************************


Challenge Name:
Category:
Point Value:
Challenger: Destry
Challenge Description:
Steps Taken:
    -
    -
    -


********************************************


Challenge Name:
Category:
Point Value:
Challenger: Destry
Challenge Description:
Steps Taken:
    -
    -
    -


********************************************


Challenge Name:
Category:
Point Value:
Challenger: Destry
Challenge Description:
Steps Taken:
    -
    -
    -


********************************************


Challenge Name:
Category:
Point Value:
Challenger: Destry
Challenge Description:
Steps Taken:
    -
    -
    -


********************************************


Challenge Name:
Category:
Point Value:
Challenger: Destry
Challenge Description:
Steps Taken:
    -
    -
    -













