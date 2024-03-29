<!-- for giving heading to text in .md file means Markdown-->

# Headings are total 6 heading

written heading by using # symbol

# Starting Emmit

paragraph of first heading

## Starting Emmit

paragraph of 2nd heading

### Starting Emmit

paragraph of 3rd heading, only for 1 & 2nd heading, paragraph's line is being shown

#### Starting Emmit

paragraph of 4rth heading, only for 1 & 2nd heading, paragraph's line is being shown

##### Starting Emmit

paragraph of 5th heading, only for 1 & 2nd heading, paragraph's line is being shown

###### Starting Emmit

paragraph of 6th heading, only for 1 & 2nd heading, paragraph's line is being shown

####### Starting Emmit, it will not work because 7 times # has been written<!-- can not use 7th heading, heading valid only till 6th Heading-->

<!-- ----------------------------------------------------------------------------------------------------------------------->

<!-- for making boold text using ** (double astrics) and __ (double underscores)-->

# creating bold text using double astricks or double underscore

**Bold text by using double astrics\*\***

**Bold text by using double underscores \_\_**

<!-- --------------------------------------------------------------------------------------------------------------------- -->

<!-- creating italics text by using single underscore _ or single astrics * -->

# italics text using single astricks or single underscore

_italics by using single astrics_

_italics by using single underscore_

<!-- --------------------------------------------------------------------------------------------------------------------- -->

<!-- strike-through by using double tild ~~ -->

# strike throud using double tild ~~word or number~~

price ~~Old Price~~ rs now only New Price rs

<!-- --------------------------------------------------------------------------------------------------------------------- -->
<!-- Order list (Enter and TAB)-->

# order list

1. one
2. two
3. three
   1. one under threee
      - 1 <!--unordered list added using - in ordered list using Enter + TAB-->
      - 2
   2. two under three
      1. sdfkjsd
      2. kasdfksdl
         1. om
         2. mani
         3. padme
4. four
   1. one uder four

<!-- Unorder List -->

# unorder list

- one
- two
- three
  - one under three
    - 1
  - two under three
    - 2
  - three under three
    1. 3 <!-- ordered list added using 1,2,3 in unordered list (using Enter + TAB)-->
    2. 4
    3. 5
- four
  <!-- ----------------------------------------------------------------------------------------------------------------------->

      <!-- how to link [NameOfLink](LinkOfWebsite "HoverNamePutHere") -->

  [googleLinkName](https://www.google.com/ "google Hover Name")

# Links

here are some links arranged in unordered list format (line after heading comes automatically,and after heading, i am writting this sub heading)

- [googleLinkName](https://www.google.com/ "google Hover Name")

- [googleLinkName](https://www.google.com/ "google Hover Name")

    <!-- ----------------------------------------------------------------------------------------------------------------------->

<!-- for showing code on page triple backtick ```code```  -->

# code

code is write using `code` triple backtick

```
//for of loop can be used for array and string

let arr = [1,2,4,"hi","bye"];

for(let elm of arr){
    console.log(`element of array ${elm}`);

    if(typeof elm === "string"){
        for(let strElm of elm){
            console.log(strElm);
        }
    }
}

Output :

element of array 1
element of array 2
element of array 4
element of array hi
h
i
element of array bye
b
y
e
```

````javascript
//if you want to colored code like language then after ``` write programming language name
//eg. ```javascript, ```python, ```java etc. (while starting)

let arr = [1, 2, 4, "hi", "bye"];

for (let elm of arr) {
  console.log(`element of array ${elm}`);

  if (typeof elm === "string") {
    for (let strElm of elm) {
      console.log(strElm);
    }
  }
}
````

```python
print("hello world");
```

<!-- ----------------------------------------------------------------------------------------------------------------------->

<!-- for writting keyword use `keyword` (single backtick) -->

# Keywords

how to write keywords

`let`

`var`

`for`

<!-- ----------------------------------------------------------------------------------------------------------------------->

# Images ![alt text](images url "Hover Text")

![alternativeTextShowsWhenImageNotVisible]("budhha_thought.png" "hoverText")

<!-- ----------------------------------------------------------------------------------------------------------------------->

# blockquote using >

> Hello (blockquote just used > symbol)

<!-- ----------------------------------------------------------------------------------------------------------------------->

# create line (use 3 astric sign \*\*\* or 3 hyphen sign ---)

---

<!-- using --- hyphen -->

---

<!-- using _** astrics-->

# table (: colon is used for indentation)

| Header 1 | Header 2 | Header 3 |
| :------- | :------: | -------: |
| Row 1    |  Data 1  |   Data 1 |
| Row 2    |  Data 2  |   Data 2 |
| Row 3    |  Data 3  |   Data 3 |

## changed alignment to center by using :------:

| Header 1 | Header 2 | Header 3 |
| :------: | :------: | :------: |
|  Row 1   |  Data 1  |  Data 1  |
|  Row 2   |  Data 2  |  Data 2  |
|  Row 3   |  Data 3  |  Data 3  |

## changed alignment to right by using -------:

| Header 1 | Header 2 | Header 3 |
| -------: | -------: | -------: |
|    Row 1 |   Data 1 |   Data 1 |
|    Row 2 |   Data 2 |   Data 2 |
|    Row 3 |   Data 3 |   Data 3 |

## changed alignment to left by using :-------

| Header 1 | Header 2 | Header 3 |
| :------- | :------- | :------- |
| Row 1    | Data 1   | Data 1   |
| Row 2    | Data 2   | Data 2   |
| Row 3    | Data 3   | Data 3   |
