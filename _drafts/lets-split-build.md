---
layout: post
title: Let's Split Build Guide or: How I Learned to Stop Worrying and Love the Process
---
#Act I
##Scene i
I was ensnared by the world of keyboards. I fell in love with the combination of
utility and creative activity involved in the hobby. So it began.

##Scene ii
I knew I wanted a split keyboard. I researched and the options were few and far
between. The only real contenders were these:
- Ergodox
- Diverge 3
- Let's Split

###Ergodox
I had heard things about the thumb cluster being unpleasant to reach, but more
importantly it would be hard to find a kit and even harder to purchase it for a
reasonable price. The Ergodox EZ comes fully assembled, but that felt too much
like cheating and would have denied me the experience of building my own
electronics - which I so highly desired. I may well end up with one of these the
next time it drops, but I needed to get my hands on something in a more timely
fashion as I was eager to begin my journey, and I knew it would involve testing 
many boards.

###Diverge 3
For a few short days I really thought I would be ending up with this one. The
layout is similar to the Ergodox, while seeming to solve the thumb cluster
issues. One thing a number of reviewers disliked was the more aggressive column
staggering present on this board, though I don't know that it would have
bothered me much. What really ended up turning me off of this board was that it
seems to run solely on some proprietary firmware. I did a cursory search of the
site and couldn't find any mention of QMK, so I assumed that I would be
handicapped in some ways by programming the keyboard solely through the provided
UI. I would absolutely consider this one again if that turned out not to be the
case...

###Let's Split
This seemed the most approachable. It's basically a Planck cut in half. The
board is made up of two halves each with 24 keys arranged in four (4) rows of
six (6) keys. The boards are connected using a TRRS 3.5mm cable (some builds can
get away with a standard TRS cable) and connect to your machine using a
micro-USB port on either half. It has support for both Cherry MX and Alps style
switches, which was great because I wanted to try out Matias QuietClick switches
to see what all the fuss was about - though I still wasn't sure if I wanted to
go that route, given the difficulty of finding keycaps. This board doesn't
really have a switch lighting option, and the RGB underglow module requires you
to forego using i2c to connect the boards, which means you have to flash each
half with a half-specific `.hex` file and you have to choose ahead of time which
board will be the master board. I liked the flexibilty provided by i2c and the
Alps/MX compatibility option so I decided I'd go with this. I was also really
excited to try something that would force me to learn a significantly different
layout - mostly just to see how long it would take to make the switch.

I went onto [switchtop](http://www.switchtop.com) and ordered myself the PCBs,
some Gateron brown switches (since I hadn't yet decided on Matias I figured I
could easily resell or reuse them for another project). I already had a few 5v
Pro Micros because I'd ordered a 3pk when I got the one for my (macropad)[], and
I had a bunch of diodes leftover from that as well, so all I needed was a couple
of [TRRS jacks from Digikey](), [a TRRS cable](), and 2x 4.7KΩ resistors (which
I forgot to order and bought at a local Radio Shack).

##Scene iii
Parts were ordered - there was only to wait. Decisions were made regarding the
switches and keycaps and now a cold soldering iron waited to begin its work.

#Act II
This is the part where beginners should pay attention and learn from my
mistakes. Check your work. Check. Your. Work. Twice. If you can test your
circuit, do so, but visually check the fit of your parts as well. Now, as much
as you'd like to listen to that advice - and you *will* try - you'll find that
there's some aspect that you didn't think about, some little tidbit that doesn't
seem like it should matter but it does.

I was 

#Act III

_No microcontrollers were harmed in the building of this keyboard._
