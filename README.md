# MorseCodeChallenge
## Goal
Your goal is to write one method - `encode()` - that takes a string as input and 
which returns an English translation of the Morse code contained within.

There are a number of included unit tests; *you may not change any of the tests*.

There are tests of multiple levels of difficulty, from pretty easy to very difficult,
so don't worry if you don't get them all, or even a majority. We're just curious 
about how you attack whatever parameters you choose to include in your model. We know that you 
have a lot on your plate, and nobody's expected to finish!

Have fun!

## Morse Code Background
- In Morse code, characters are represented by short ("dit") and long ("dah") 
sounds. In text, they're often represented by . and -, respectively
- There are short gaps between sounds within a character, longer gaps between 
characters, and even longer gaps between words
## Specifications and Limits
- The absolute length of a sound in Morse code isn't as important as the ratio 
of short to long sounds, and the sizes of the gaps between sounds, characters, and words
- If we define the length of a "dit" as one time unit (1 TU), then:
    - "dah": 3 TU
    - space between sounds in a character: 1 TU
    - space between characters: 3 TU
    - space between words: 7 TU
- Example, with each character representing one time unit: 
    - "HI THERE" -> .\_.\_.\_.\_\_\_.\_.\_\_\_\_\_\_\_---\_\_\_.\_.\_.\_.\_\_\_.\_\_\_.\_---\_.\_\_\_. 
- Only the characters A-Z (there is now case difference in Morse code, so we'll stick 
with uppercase) and 1-9 are present in the encoded text for our tests
## Model Parameters and Assumptions
- The first few start out easy, with more rigorous assumptions. As the assumptions are removed or relaxed, the method becomes more complex. The more general 
your method is in dealing with the possible variations, the more tests it will pass
- At the beginning, "X" indicates a time period during which sound is played, and
"O" is a time interval of silence
    - So, at the beginning, "HI THERE" -> XOXOXOXOOOXOXOOOOOOOXXXOOOXOXOXOXOOOXOOOXOXXXOXOOOX
    - Later tests have different letters for these, 
and your method will need to automatically determine which letters are for which
- At the beginning, there is no extra silence at the beginning or end
    - Extra silence at the end is added early on, and extra silence at the beginning 
    is also added in the advanced tests
- At the beginning, 1 TU = 1 letter
    - Beginning in the moderate tests, that can expand to 
2, 3, 4, or 5 letters for 1 TU
- For (almost) all tests before the last, the only characters present are those for sound 
and silence
    - If non-letter characters are present in the encoded string, the method should throw an appropriate error
    - In the final test, there are randomly-placed "noise" characters in the 
    encoded string. These replace the silence or sound characters in random infrequent spots
