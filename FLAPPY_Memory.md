# Flappy Memory

**Points:** 500  

**Category:** Reverse Engineering

**Author** NotOptimus

## Challenge Description

The challenge provides a Flappy Bird-style game where the objective is to achieve a high score of 50000. Also hint was given that you can cheat.


<img width="717" height="868" alt="image" src="https://github.com/user-attachments/assets/fbe4c328-5bd9-400f-9ff0-691c0aa6a157" />


## Solution

At first I downloaded the Challenge.txt file then opened the Google Drive link to install the actual game file. It was a .exe file so I executed it and started the game and thought that the game is here so the score would be controlled locally on my pc.

<img width="1148" height="752" alt="image" src="https://github.com/user-attachments/assets/2ef20aae-9491-4c52-a72d-0880dae6d0f2" />


Then I made use of AI that how can we do so, it told me about CheatEngine. I installed cheat engine, played the game and scanned the changes in score value and figured out the exact variable storing the score.
So I modified the value to 50000 and as I continue to play the game and score reached 50001, it revealed the flag.

<img width="757" height="590" alt="image" src="https://github.com/user-attachments/assets/0d2561e1-5424-40c5-be9e-8a26f2689c59" />

## Challenges

The main difficulty was figuring out where the game's score was stored in memory.

Initially, there were a large number of possible memory addresses, so it was not immediately obvious which one controlled the score. A memory scan produced more than a thousand possible results, which had to be narrowed down by changing the in-game score and rescanning.

After repeatedly filtering the results, only two possible addresses remained. Further investigation identified the relevant address:


## Flag

`EHAX{d1d_y0u_just_ch@ng3_1he_sc0re_values_?}`

## Conclusion

The important takeaway was that the game trusted a client-side score value. Since that value was not properly protected or validated, modifying it allowed the challenge to be solved without achieving the score normally.
