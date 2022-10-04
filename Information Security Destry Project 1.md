
1. Each group will complete a total of 10 challenges from the General Skills category.
a. This must include an attempt at one problem > 100 points.
2. Each group will complete two challenges from every other category (Web Exploitation,
Cryptography, Reverse Engineering, Forensics, Binary Exploitation).
a. For each category, one problem can be <100 points, while the second must be >= 100
points.
3. Each group will try ONE problem, from any category, that has less than 500 solves. Label this
clearly as “HIGHEST DIFFICULTY”.




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


********************************************


Challenge Name: Matryoshka doll
Category: Forensics
Point Value: 30
Challenger: Destry
Challenge Description: You are given an image of a Matryoshka doll and have to find some way to get a flag from it.
Steps Taken:
    - Doenloaded the image gave it a look in windows photos, nothing out of the ordinary.
    - Found an online metadata viewer @ https://www.metadata2go.com/ looked at the metadata for a while, nothing out of the ordinary except even though the file had the jpg extension the metadata viewer said it was png.
    - Changed the extension name to png and opened it again in windows photos, nothing changed.
    - looked at the image in notepad, searched for the word "pico" but also nothing.
    - looked up the solution. Found one by 'ZeroDayTea' and 'Killer Queen' @ https://ctftime.org/writeup/28156
    - The solution involved using binwalk to extract compressed files hidden in the image. You would extract the file, descend one level into the directory where there was another image with a file compressed inside of it. I repeated the process four times til i got to 'flag.txt'
    - opened 'flag.txt'. The flag was in it.


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
