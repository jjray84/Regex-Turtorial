# Understanding how REGEX works

A **regex**, which is short for **regular expression**, is a sequence of characters that defines a specific search pattern. When included in code or search algorithms, regular expressions can be used to find certain patterns of characters within a string, or to find and replace a character or sequence of characters within a string. They are also frequently used to validate input.

## Summary

The regex example that I will be using as for everyone to hopefully better understand it is:
      
/^#([a-f0-9]{6}|[a-f0-9]{3})$/

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

# Regex Components

## Anchors     
     
Anchors are used in regex to signify the start and end of the test.  The symbol ^ is used to represent the start of the expression that will be used to search through the code to locate a string of information, where the $ signifies the end of the expression.     
      
For an example: ^T will find all instances within your code were a capitol letter T is used to start a word.  It will NOT, however, find any words that start with a lowercase t.      
            
Using this knowledge, and comparing it to the example regex mentioned in the summary, you should easily deduce that the item(s) we are searching for will begin with the symbal #.  
     

## Quantifiers   
      
Quantifiers set the limits of the string that your regex matches.  These frequently include the minimum and maximum numbers of characters in the string regex searches through.  While quantifiers are greedy by nature, being greedy can be good in some cases as it will match as many occourences of the particular patterns as possible.  Some of the quantifiers that you may see most are:
     
(*) - This matches the pattern zero or more times.     
(+) - This matches the pattern one or more times.     
(?) - This matches the pattern zero or one times.  
{ } - Provides three different ways to set limits for a match. For example, {n} will match the pattern exactly one time. {n,} will match the pattern AT LEAST one time. {n, x} matches the pattern from a minimum of 'n' times to a maximum of 'x' times.
     
(Please Note: the ( ) above are NOT part of the quantifiers. These are used so that the will show up properly in this .md file)
     
Now, using that information, we can look at the example expression and see that the {} are used twice.  Being that both of them contain one number, we can deduce that the the pattern will search for an exact example once that contains 6 of something or 3 of something.  Please keep reading to better understand exatly **what** we are searching for.       
     

## Bracket Expressions     

Bracket Expressions are used to hold values, or ranges of values, that regex uses to search your code.  Anything inside of the Square Brackets [ ] give the code guidance on what to search for.  As an example, if you use [a-z] in your regex, what it is telling the code to search for is anything that contains **only** lowercase letters.  Another example is [0-9].  This will search for a string that only contains a number.  Square Brackets can also contain special characters.  Here is an example that combines all of the examples used here: [A-Za-z0-9_-].  This example searches your code for a string that contains **any** uppercase letter, **any** lowercase letter, **any** number, and can also include an underscore or hyphen.     

Knowing this, when we look back at the example code given at the top, we can now deduce that we are looking for a string that contains **only** lowercase letters or numbers.  When we add the (?) and the # to it, as well as the {6} that we have already learned, we can deduce that for some part of the regex, we are looking for a single instance of a string that contains #, as well as at least six (6) lowercase letters and/or numbers.                     
      

## The OR Operator
The **OR** operator can be handy to use when your regex can have multiple items it is looking for.  For an easy example, if you were looking for [abc], you can rewrite it to (a|b|c). This will search your code for a string that starts with and a, or a b, or a c.  This can be handy for times when the code you are looking through can have multiple ways of typing it out.  

Using the example from the start, we can observe the OR operator used between the {6} and the [] for the second part of the expression.  To better explain, the expression is searching for something in your code that starts with #, contains lowercase letters and/or numbers to equal a total of 6 characters.  **OR** it can contain a combonation of lowercase letters and/or numbers that equal to a total of 3 characters.  
      

## Final Explination
Now that we have gone through all of the parts of the expression, let me explain EXACLTY what it is designed to locate.  The string that this expression is looking for will contain a #, followed by {6} characters that can be lowercase letters and/or numbers, **or** it will contain a #, followed by {3} characters that can be lowercase letters and/or numbers.      

So what do you think it is searching for?  If you thought about a hex code, you are right!  A hex code is written in two different ways.  One example is: #7e0cd6. This hex code can be used to give an element a purple color.  Hex codes can also be written in a 3 digit way when each of the RGB values match.  If you wanted a light peach color, you could write out #ffccbb, *or* you can simplify it by writing #FCB.     
      

## Author
My name is Jonathan Ray and I am a current bootcamp student.  I am attend the Georgia Tech Full Stack bootcamp and will be graduating mid-March of 2023.  Please feel free to take a look at my profile to see all of the repositories I have done during this bootcamp. 

[github](https://github.com/jjray84)