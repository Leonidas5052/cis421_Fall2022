-----------------------------------------

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





Challenge Name: Lets Warm Up

Category: General Skills

Point Value: 50

Challenger: Destry

Challenge Description: Description asks what a word would start with if the hexidecimal code started with 0x70.

Steps Taken:

    - Still had ascii chart up from previous challenge, chart said 'p'
    
    - put the flag in as 'picoCTF{p}'
    
    - just to see what would happen, it worked



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




