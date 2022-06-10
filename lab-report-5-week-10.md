# Lab Report 5 Week 10

### Comparing tests with different results


`vimdiff`
can be used to find the difference between the test files..



### Links to the test files I used in this report

1. [Test #194](https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/194.md)
2. [Test #481](https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/481.md)

# For Test File 194
I generated a preview using this website: [CommonMark](https://spec.commonmark.org/dingus/)
<img width="659" alt="Screen Shot 2022-06-10 at 10 09 29 AM" src="https://user-images.githubusercontent.com/103294764/173117128-d6964639-58a9-43cf-ae82-9e3379fe558b.png">

After running `vimdiff`, I got these comparisions.
<img width="911" alt="Screen Shot 2022-06-10 at 10 10 56 AM" src="https://user-images.githubusercontent.com/103294764/173117337-8c416a5c-85e3-42a0-87db-2665944a7193.png">

*My code is running on the left and the given code is on the right*


### Analysis
Both implementations failed to parse the code properly. They need changes in order to produce the correct outputs.

### Bug

The given program returns an incorrect link when it should be returning the expected output the CommonMark demo suggests
The code uses `:` to produce links instead of the conventional `[]()` 
this may produce an error which neither of our codes will be able to parse.
The given code only recognizes `()` mismatches, mine recognizes both `[]`&`()` mismatches
Mine produces slightly more than the given code, although it could be improved.


Given code:
<img width="550" alt="Screen Shot 2022-06-10 at 10 30 31 AM" src="https://user-images.githubusercontent.com/103294764/173120061-10f8da8d-d97d-45c3-93a7-ba13dc8ed318.png">

My code:
<img width="473" alt="Screen Shot 2022-06-10 at 10 31 41 AM" src="https://user-images.githubusercontent.com/103294764/173120263-c30fcc60-8a7b-4324-b045-4d196c8196ee.png">



# Test File 481

CommonMark generated preview:
<img width="491" alt="Screen Shot 2022-06-10 at 10 33 15 AM" src="https://user-images.githubusercontent.com/103294764/173120475-7ef39643-88f7-43ab-8f22-5a1d65a7c51a.png">

After running `vimdiff`, I got these comparisions.

<img width="729" alt="Screen Shot 2022-06-10 at 10 34 58 AM" src="https://user-images.githubusercontent.com/103294764/173120758-f8a7ea5f-e91b-47a0-b970-0e9817289e3b.png">

*My code is running on the left and the given code is on the right*

### Analysis

The given code produces an incorrect output while mine somewhat parses correctly.

### Bug

The given program returns an incorrect link it should return similar to the expected output.
This error may be attributed to this part of the program..

<img width="396" alt="Screen Shot 2022-06-10 at 10 40 27 AM" src="https://user-images.githubusercontent.com/103294764/173121597-5f4482c7-ee7a-4871-9e94-9809b45399ff.png">

It seems to be returning an empty arraylist which causes an error.
