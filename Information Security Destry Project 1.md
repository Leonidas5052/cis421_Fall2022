
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