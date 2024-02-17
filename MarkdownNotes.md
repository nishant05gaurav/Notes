# Markdown Syntax Notes

## Working of headings:
```markdown
# Heading       (H1)
## Heading      (H2)
### Heading     (H3)
#### Heading    (H4)
##### Heading   (H5)
###### Heading  (H6)
```


---

### Separator 
For separator, we use  ``---`` lines.
Example:

---
### Important
- If we use ``-`` and space then it creates automatic list.
    - Example: 
        - number-one
            - number-one-inside-one
        - number-two
        - number-three
            - number-one-inside-three
    - We can also give numbers, characters, romans, etc.
    - Example:
        1. first
        2. second
            1. first-second
        3. third

- To write keywords, links, important words, code, etc. We use back-ticks. Example: ``printf()``, ``int a = 5;``, etc.
- To bold a word, we use double asterisks. Example: **This is bold**.
- To italicize a word, we use single asterisk. Example: *This is italicized*.
- We can combine both 2 asterisks and 1 asterisk to create bold-italic. Example: ***I am bold and italicized***.
- To write a code, we use triple-backticks i.e. code block markdown. 
    - Example:
        ```c
        printf("Hello, World!");
        ```

        ```cpp
        cout << "Hello world";
        ```

        ```python
        print("Hello world")
        ```

        ```js
        console.log("Hello World");
        ```

        ```c#
        console.write("Hello world");
        ```

        ```java
        System.out.println("Hello world");
        ```
    - If we want to write smaller codes, we can write them in backticks. 
        - Example: Various function of string manipulations are:
            - ``strlen()``
            - ``strcpy()``
            - ``strcmpr()``, etc.
- To insert image, we use ``![]()`` i.e. ``![If image is not shown, what to be shown?-OPTIONAL](image-link)`` together. 
    - Example:
        - ![If image is not shown, what to be shown?](image-1.png)
- To paste a link, we use ``[]()`` combination i.e. ``[name of the link](link)``
    - Example: [Click here to go to GitHub](https://github.com/)

---


