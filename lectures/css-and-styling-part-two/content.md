# CSS and Styling (Part Two)








-
-
## Pseudo-Classes
* Some elements can be targeted with special "pseudo" or dummy classes that often deal with a temporary state of being.
* Pseudo-classes are used to define a special state of an element
* Links are an example
* The syntax of a psuedo-class is as follows:

```CSS
  selector:pseudo-class {
    property:value;
  }
```


-
-
### Link Styles
* Links have four states
  * a:link - a normal, unvisited link
  * a:visited - a link the user has visited
  * a:hover - a link when the user has the cursor over the link
  * a:active - a link the moment it is clicked
* Each state is known as a psuedo-class



-
-
### Example
```CSS
  /* unvisited link */
  a:link {
  color: #FF0000;
  }

  /* visited link */
  a:visited {
  color: #00FF00;
  }

  /* mouse over link */
  a:hover {
  color: #FF00FF;
  }

  /* selected link */
  a:active {
  color: #0000FF;
}
```


-
-
### Important Note
* a:hover MUST come after a:link and a:visited in the CSS definition in order to be effective! a:active MUST come after a:hover in the CSS definition in order to be effective! Pseudo-class names are not case-sensitive.



-
-
### Topic 1
* Sub-topic 1A
* Sub-topic 1B
* Sub-topic 1C

-
#### Sub-topic 1A
* Discussion point 1A.1
* Discussion point 1A.2
* Discussion point 1A.3


-
#### Sub-topic 1B
* Discussion point 1B.1
* Discussion point 1B.2
* Discussion point 1B.3


-
#### Sub-topic 1C
* Discussion point 1C.1
* Discussion point 1C.2
* Discussion point 1C.3











-
-
### Topic 2
* Sub-topic 2A
* Sub-topic 2B
* Sub-topic 2C

-
#### Sub-topic 2A
* Discussion point 2A.1
* Discussion point 2A.2
* Discussion point 2A.3


-
#### Sub-topic 2B
* Discussion point 2B.1
* Discussion point 2B.2
* Discussion point 2B.3


-
#### Sub-topic 2C
* Discussion point 2C.1
* Discussion point 2C.2
* Discussion point 2C.3













-
-
### Topic 3
* Sub-topic 3A
* Sub-topic 3B
* Sub-topic 3C



-
#### Sub-topic 3A
* Discussion point 3A.1
* Discussion point 3A.2
* Discussion point 3A.3


-
#### Sub-topic 3B
* Discussion point 3B.1
* Discussion point 3B.2
* Discussion point 3B.3


-
#### Sub-topic 3C
* Discussion point 3C.1
* Discussion point 3C.2
* Discussion point 3C.3













-
-
## Lecture Summary
* Topic 1 Summary
* Topic 2 Summary
* Topic 3 Summary
