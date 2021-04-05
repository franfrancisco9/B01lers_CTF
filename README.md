# B01lers_CTF
Write ups of the challenges I solved at the B01lers CTF from 3 to 5 of April, 2021
I will add more write ups later.

Great description of the competition can be found in the official competition website: <https://ctf.b01lers.com/home>

We ended up in the 33rd place!

## Miscelaneous
>Category for out of the ordinary stuff

#### **Bars, Windchests, Vocals (497/500 Points)**
The main challenge I solved (7 hours before any other team) was in the misc section and about music.
Here was the description:

>Help, guys! 
>I heard puzzles of this sort are practically music to your ears. 
>The secret is broken into 12 parts, and I have all the clues. 
>Yet, I cannot figure it out :/ I can only recognize the very last one because that is super famous...

And we got a file for 12 sheets of music in a single pdf file.

The last one was this:

![Image of Bars, Windchests, Vocals](https://github.com/franfrancisco9/B01lers_CTF/blob/main/Bars,%20Windchests,%20Vocals.png)

Which by a quick search is the famous Toccata BWV 565 by Bach and in the lower right corner is a code:
```python3
I + VII + 1 = 700			
V – VI = ?00
XI – XII = 200     
V + IX = 900
```
Which at first was really confusing and I tried to check the keys of the different pieces.

Only later after researching some of the other pieces by the name and confirming my suspicious that they were all Bach, that I thought about the BWV number, a numeric system used to catalogue the bach pieces!
And what would you knwo, it worked, by doing the 565 + 200 = 765 and searching online for Bach BWV 765 I found music number 11 as suspected.

I did this for all sheets and got this:
```python3
I = 510
II = 862
III = 272
IV = 870
V = 546
VI = 146
VII = 189
VIII = 563
IX = 354 
X = 996
XI = 765
XII = 565
```
So now, funny enough is where I spent most time, and since no one was yet to solve by the second day they gave us two hints:

>Hint! The problem gives you an actual flag, it is not just a long number.
>Hint! The long number you get *is* the flag (in a form that computers love). It is in bctf{...} format, all bells and whistles are included in it.

Alright, so we put all numbers together:

```python3
  510862272870546146189563354996765565
```
What do computers love? (Took me way too much to find this) Hex! Which is actually how most cipher act.

```python3
  626374667B4A53422F724F634B737D
```

Then convert to unicode and voila:

```python3
 bctf{JSB/rOcKs}
```
Really clever and perfect for the misc section!
