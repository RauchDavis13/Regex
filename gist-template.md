# REGEX expression for email search - How it works


## ***`Summary`***

>The following outlines the code used for a REGEX based expression used for searching for an email address within a string. 

>REGEX expression... 
***`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`***

## ***`Table of Contents`***

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)

## ***`Regex Components`***
> A REGEX expression is comprised of different components that allow for very targeted searches.  These components include Anchors, Quantifiers, Character Classes, etc.  Each component targets specific attributes of the search expression.<br>
Please read further to understand how each component is used the REGEX expression.

________________________________________________

>Both the first and last character, or starting and ending characters of the REGEX expression use the ***`/`*** character.  The content between the beginning and ending ***`/`*** chracters is where the search criteria is defined.

>All character spacing references are assumed to be inside the beginning and ending ***`/`*** characters and are not included as part of the character positioning.



### ***`Anchors`***
>The 1st chararacter used is the carrot ***`^`***, denoting that the search will begin at first line of the start of the string.

***`^`***[a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$



### ***`Quantifiers`***

>The ***`+`*** Quantifier used is twice.  First, at the 15th character position. 

>^([a-z0-9_\.-]***`+`***)@([\da-z\.-]+)\.([a-z\.]{2,6})$

>This is used to identify one or more of the preceding token, which would be Character Class ***`[a-z0-9_\.-]`***.  This part of the expression identifies the first part of the email string, the user's idenifier.<br>
Example: ***`user1`***@company.com.


>The second use of the ***`+`*** Quantifier, is at the 29th character position.

>^([a-z0-9_\.-]+)@([\da-z\.-]***`+`***)\.([a-z\.]{2,6})$

>Again, this is used to identify one or more of the preceding token, which would be Character Class ***`[\da-z\.-]`***.  This part of the expression identifies the organization/company, or higher hierarchical level of the email adress.<br>
Example: user1@***`company`***.com

__________________

>The Quantifier of ***`{2,6}`*** is used between the 41st and 45th character positioning.

>^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.***`{2,6}`***$

>This looks at the preceeding Character Class of ***`[a-z\.]`*** and limits the amount of characters to between 2 & 6.  This would typically be the ***`com`***, ***`org`*** or other at the end of the email string.<br>
Example: user1@company.***`com`***.


### ***`Character Classes`***
>The first Character Class instance is located between the 3rd and 14th character positions.

>^(***`[a-z0-9_\.-]`***+)@([\da-z\.-]+)\.([a-z\.]{2,6})$

>t defines 5 criteria for the user's id portion of the email string
- ***`a-z`*** allows for the range of characters from lowercase `a` to lowercase `z`
- ***`0-9`*** allows for the range of numbers from `0` to `9`
- ***`_`*** allows for the use of the underscore character `_`
- ***`\.`*** allows for the use of a `.` as a text literal
- ***`-`*** allows for the use of the hyphen character `-`


>Following the `@` symbol is the next Character class, between character positions 19 and 28  ***`[\da-z\.-]`***

>^([a-z0-9_\.-]+)@(***`[\da-z\.-]`***+)\.([a-z\.]{2,6})$

>It defines 4 criteria for the company/organization portion of the email address
- ***`\d`*** allows for any digit character, or `0-9`
- ***`a-z`*** allows for the range of characters from lowercase `a` to lowercase `z`
- ***`\.`*** allows for the use of a `.` as a text literal
- ***`-`*** allows for the use of the hyphen character `-`


>The final Character Class is used between characters 35 and 41 ***`[a-z\.]`***

>^([a-z0-9_\.-]+)@([\da-z\.-]+)\.(***`[a-z\.]`***{2,6})$


>This Character Class defines 2 critera for the last part of the email address
- ***`a-z`*** allows for the range of characters from lowercase `a` to lowercase `z`
- ***`\.`*** allows for the use of a `.` as a text literal


### ***`Flags`***
>In testing, the ***`g`*** Flag was used for "global search"

>/^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/***`g`***



### `Grouping and Capturing`
>`Capture Group 1` is between the 2nd and 16th character positions.  ***`([a-z0-9_\.-]+)`***

^***`([a-z0-9_\.-]+)`***@([\da-z\.-]+)\.([a-z\.]{2,6})$

This grouping starts with the Character Class `[a-z0-9_\.-]`, followed with the `+` Operator.


>`Capture Group 2` is between the 18th and 30th character positions.  ***`([\da-z\.-]+)`***

^([a-z0-9_\.-]+)@***`([\da-z\.-]+)`***\.([a-z\.]{2,6})$

This grouping starts with the Character Class `[\da-z\.-]`, followed with the `+` Operator.


>`Capture Group 3` is between the 33rd and 46th character positions.  ***`([a-z\.]{2,6})`***

^([a-z0-9_\.-]+)@([\da-z\.-]+)\.***`([a-z\.]{2,6})`***$

This grouping starts with the Character Class `[\da-z\.-]`, and then the Quantifier `{2,6}`.



### ***`Bracket Expressions`***

>Much like the Character Class, the [] expression defines the the characters to be matched for the search.

See Character Class for definitions of how characters are matched


## ***`Author`***

>I'm Ken Rauch Davis.  I'm just starting my path down to the road of coding.  My career has so far been in the food industry (distribution and CPG) since 1991.  During my last few years, I've found opportunity in identifying reporting gaps that I've been able to fill using Excel.  I've seen these same gaps at multiple companies.  Excel is a stopgap until my coding becomes proficient enough to develop front end/back end apps to fill these gaps.  One of my goals is to become adept at Fullstack Development to development my own software related to the food industry.

>I'd also like to explore other coding avenues.  While I've in the food industry for over 30 years, I'd also like to explore more creative ventures.

## ***`Ken Rauch Davis `***
GiHub Profile https://rauchdavis13.github.io/Challenge-2a/<br>
GitHub Repository https://github.com/RauchDavis13