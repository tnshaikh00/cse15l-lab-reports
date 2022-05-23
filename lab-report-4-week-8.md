# Lab Report 4

[Link to my markdown-parse repository](https://github.com/tnshaikh00/Markdown-Parser)


[Reviewed markdown-parse repository](https://github.com/Pgerardocastaneda/markdown-parser)


I made 6 test cases in order to compare my outputs vs the reviewed outputs

![Screen Shot 2022-05-22 at 11 09 13 PM](https://user-images.githubusercontent.com/103294764/169755040-60e06cfa-2e17-4f37-bbe0-17583d3850fb.png)


## Snippet 1

```
`[a link`](url.com)
[another link](`google.com)`
[`cod[e`](google.com)
[`code]`](ucsd.edu)
```

It should produce the output:

![Screen Shot 2022-05-22 at 10 31 31 PM](https://user-images.githubusercontent.com/103294764/169749916-d08ea563-68f3-47f5-a954-895a484ed27c.png)


The passing test for my Markdown Parser:

![Screen Shot 2022-05-22 at 11 21 40 PM](https://user-images.githubusercontent.com/103294764/169756190-fcd50b3c-62c0-49f1-a289-4ff69429e23c.png)


The passing test for the reviewed one:

![Screen Shot 2022-05-22 at 11 24 24 PM](https://user-images.githubusercontent.com/103294764/169756523-8237326a-ac63-47f0-8c9a-df9a2df1acf2.png)


 For both my implementation & the code I reviewed I passed the test cases. So far no changes needed to fix the code...




## Snippet 2


```
[a [nested link](a.com)](b.com)
[a nested parenthesized url](a.com(()))
[some escaped \[ brackets \]](example.com)
```

It should produce the output:

![Screen Shot 2022-05-22 at 11 25 45 PM](https://user-images.githubusercontent.com/103294764/169757652-6bb94b55-e895-4ffb-b10f-21520c15a64b.png)


The failing test for my Markdown Parser:

![Screen Shot 2022-05-22 at 11 28 03 PM](https://user-images.githubusercontent.com/103294764/169757090-da8a3ac6-bfc1-41fd-8788-560f0776a6e4.png)


The failing test for the reviewed one:

![Screen Shot 2022-05-22 at 11 30 11 PM](https://user-images.githubusercontent.com/103294764/169757347-c435ea4e-1317-4e39-8be8-5f0fa9173da5.png)



I don't think there would be a small code change that could make either mine or my peer's program work properly to parse Snippet 2. 
I tried printing the stack to figure out where parenthesis and brackets are opening or closing. 
It proved to be trivial, We would need to figure out the contents inside the parenthesis and links that are valid for markdown files, 
It would require tons of If/Else statements in order to fight all the tiny edge cases...


## Snippet 3


```
[this title text is really long and takes up more than 
one line
and has some line breaks](
    https://www.twitter.com
)
[this title text is really long and takes up more than 
one line](
https://sites.google.com/eng.ucsd.edu/cse-15l-spring-2022/schedule
)
[this link doesn't have a closing parenthesis](github.com
And there's still some more text after that.
[this link doesn't have a closing parenthesis for a while](https://cse.ucsd.edu/
)
And then there's more text
```


It should produce the output:

![Screen Shot 2022-05-22 at 11 39 04 PM](https://user-images.githubusercontent.com/103294764/169758645-b3c639f1-bcab-425a-99e5-1322848555e4.png)


Added Test

<img width="775" alt="Screen Shot 2022-05-21 at 2 59 09 AM" src="https://user-images.githubusercontent.com/103089880/169646401-0d71634d-9772-4f69-bc6b-d12abc65f235.png">


The failing test for my Markdown Parser:

![Screen Shot 2022-05-22 at 11 42 41 PM](https://user-images.githubusercontent.com/103294764/169759142-5f714ec8-3d9f-4dfb-8a78-a77e6a7ff03a.png)


The failing test for the reviewed one:

![Screen Shot 2022-05-22 at 11 41 38 PM](https://user-images.githubusercontent.com/103294764/169759171-1cae0821-5a7c-45ee-a17c-1452ffbc6e45.png)


I don't think there would be a small code change that could make either mine or my peer's program work properly to parse Snippet 3. 
Mine tends to run out of memory parsing the content, his manages to read it but gets stuck with parenthaesis and brackets mismatching which produces incorrect outputs. 
In order to fix it, we would have to make a method to remove all extra blank spaces in between links. 
We would also have to check for open parenthesis or bracket that shouldn't close, but do have a close because of a later link, 
so this would take over multiple lines of If/Else statements in order to fight all the tiny edge cases as well

