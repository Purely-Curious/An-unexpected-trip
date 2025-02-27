As of now the solution is written in a bullet point form.

Blurb:
"You find yourself in a strange room after a wild night. Although unfamilar with your environment, you find an old computer called sherlock at a desk. After booting it up, you notice an odd file in your desktop. Perhaps it'll give an explanation to this situation."

Different format: 
> -> image 
   >> flag-part-1.txt + (ciphered text)  
   >> -> Zip 
    >>>    -> flag-part-2.txt

## Challenge overview
The flag for this challenge is separated into 2 halves, one is provided to the contestant and the other is stored in a password protected zip file. Therefore the majority of this challenge consists of:
> * Finding the password parts.
> * Reconstructing the password.

This section is just the introduction for starting off the challenge.
* Check the image via stegsolve or other programs.
* find zip folder and flag part 1
* find clues towards the github account and use sherlock

## Finding the scattered parts of the password
This will be arranged in the expected order that contestants find the password parts.


### For part 2 of password:
* after looking into the first flag txt file, use sherlock to find the github user.
* download the repo
* investigate the data file
* rename it from data to data.raw as it's just raw data.
* look through the code to find the sample rate, channels and precision. (those being 8000, 1 and 8 respectively)

* use sox -r 8000 -e unsigned -b 8 -c 1 data.raw input.wav to convert it back into a wav file.
* after playing it, the contestant should recognise it's morse code.
* put input.wav into a audio morse decoder. get info from it.


### For part 3 of the password

* reverse the hex, decode it via a hex translator, base64 (in that order)
* use sherlock again to find the imgur account.
* look through the posts until you find the password part in one of the photos.


### For part 1 of the password.
* look through the repo commit using git log.
* Find the vigenere key
* decrypt the code.
* after decryption, the contensant will receive the first section of the password.

## Reconstructing the password. 
* look at the image again as it contains the part order to recreate the password.
* unzip the file with the password to find the second part of the flag.
* construct the flag.

Password Parts: \
Part 1: a]AHrtgI(. \
Part 2: necessarily \
Part 3: $|"YQuyuF9 \

312
new password.
$|"YQuyuF9a]AHrtgI(.necessarily

Actual flag: \
Part 1: CompSoc{4_14r6 \
Part 2: 3_r48817_H013} 

flag: CompSoc{4_14r63_r48817_H013}

