# String Match

1. Match Once
re:  /ninja/


| Strings     | Result         | Note                       |
| ------------| ---------------|----------------------------|
| :---        |     :---:      |          :---              |
| ninja       |     match      |                            |
| ninjawahwah |     match      |                            |
| ninja ninja |     match      | only match the FIRST ninja |



2. Global Match: g
re: /ninja/g


| Strings                 | Result         | Note                                                     |
| ------------------------| ---------------|----------------------------------------------------------|
| :---                    |     :---:      |     :---                                                 |
| ninja ninja ninja ninja |     match      | match all 4 ninja                                        |
| ninja ninja ninja Ninja |     match      | match first 3 ninja, except the last one, case-sensitive |
   

3. Case-insenstive Match: i
re: /ninja/i


| Strings                 | Result         | Note                              |
| ------------------------| ---------------|-----------------------------------|
| :---                    |     :---:      |     :---                          |
| ninja Ninja NiNjA NINJA |     match      | match all 4 ninja                 |


# Pattern Match
## Character Set: []
1. re: /[ng]inja/g


| Strings                 | Result         | Note                                |
| ------------------------| ---------------|-------------------------------------|
| :---                    |     :---:      |     :---                            |
| ninja ninja ninga ginga |     match      | match all 4 ninja                   |



2. re: /[abc123]/g


| Strings                 | Result         | Note                                |
| ------------------------| ---------------|-------------------------------------|
| :---                    |     :---:      |     :---                            |
| abc3                    |     match      | match the whole string              |
| ab3e                    |     match      | match "ab3"                         |
| abcdef3                 |     match      | match "abc3"                        |


3. re: /[abc123]000/g


| Strings                 | Result         | Note                                |
| ------------------------| ---------------|-------------------------------------|
| :---                    |     :---:      |     :---                            |
| ab3e                    |     No         |                                     |
| a000  b000  c000  2000  |     match      | match all the 4 strings             |
| e000                    |     No         |                                     |


## Exclusive Set: [^]
1. re: /[^p]000/g


| Strings                      | Result         | Note                              |
| -----------------------------| ---------------|-----------------------------------|
| :---                         |     :---:      |     :---                          |
| a000  b000  c000  2000  e000 |     match      | match the whole string            |


2. re: /[^pe]000/g


| Strings                      | Result         | Note                               |
| -----------------------------| ---------------|------------------------------------|
| :---                         |     :---:      |     :---                           |
| a000  b000  c000  2000       |     match      | match all the 4 strings            |
| e000                         |     No         |                                    |


3. re: /[^pe2]000/g


| Strings                      | Result         | Note                                |
| -----------------------------| ---------------|-------------------------------------|
| :---                         |     :---:      |     :---                            |
| a000  b000  c000             |     match      | match all the 3 string              |
| 2000  e000                   |     No         |                                     |


## Ranges: -
1. +: match at least once (1 or more times)
re: /[0-9]+/


| Strings                      | Result         | Note                                   |
| -----------------------------| ---------------|----------------------------------------|
| :---                         |     :---:      |     :---                               |
| 0  01   02839483             |     match      | match all 3 strings                    |
| 0  01   02839483             |     match      | match all 3 strings                    |

2. {}: Specify the specific match times
re: /[0-9]{10}/ 
match [0-9] 10 times


| Strings                      | Result         | Note                                      |
| -----------------------------| ---------------|-------------------------------------------|
| :---                         |     :---:      |     :---                                  |
| 0123456789                   |     match      | match [0-9] 10 times  consecutively       |


re: /[a-z]{5}/ 
match [a-z] 10 times


| Strings                      | Result         | Note                                      |
| -----------------------------| ---------------|-------------------------------------------|
| :---                         |     :---:      |     :---                                  |
| ninja  hello                 |     match      | match [a-z] twice                         |


re: /[a-z]{5, 8}/ 
match [a-z] 5 to 8 times


| Strings                            | Result         | Note                                |
| -----------------------------------| ---------------|-------------------------------------|
| :---                               |     :---:      |     :---                            |
| ninja  hello  hellowow  ninjas     |     match      | match [a-z] 3 times                 |


re: /[0-9]{5, 8}/ 
match [0-9] 5 to 8 times


| Strings                       | Result             | Note                                |
| ------------------------------| -------------------|-------------------------------------|
| :---                          |     :---:          |     :---                            |
| 012345                        |     match          | match [0-5]  6 times                |
| 01234567                      |     match          | match [0-9]  8 times                |
| 012345678                     |  Partially match   | match 0123457 except 8              |


re: /[0-9]{5,}/ 
match [0-9] at least 5 times, i.e., the string is at least 5 characters long


| Strings                       | Result             | Note                                |
| ------------------------------| -------------------|-------------------------------------|
| :---                          |     :---:          |     :---                            |
| 012345678                     |   match            | match [0-9] 9 times                 |
| 0123456782384748              |   match            |                                     |


# Metacharacters


| Metacharacter  | Note                                                                  |
| ---------------|-----------------------------------------------------------------------|
| :---           |     :---                                                              |
| \d             | match any digit character, same as [0-9]                              |
| \w             | match any word character, same as a-z, A-Z, 0-9, and _ (underscore)   |
| \s             | match a whitespace character (space, tab, etc)                        |
| \t             | match a tab character                                                 |


1. re: /\d/


| Strings                       | Result             | Note                                |
| ------------------------------| -------------------|-------------------------------------|
| :---                          |     :---:          |     :---                            |
| 0  1  5   6  9                |   match            |                                     |


re: /\w/


| Strings                       | Result             | Note                                |
| ------------------------------| -------------------|-------------------------------------|
| :---                          |     :---:          |     :---                            |
| a   v   z   A  W              |   match            |    match all the characters         |
| 0   6   7   9  _              |   match            |    match all the characters         |
| @                             |   No               |                                     |


re: /\s/


| Strings                       | Result             | Note                                |
| ------------------------------| -------------------|-------------------------------------|
| :---                          |     :---:          |     :---                            |
| SPACE  TAB                    |   match            |    match SPACE, TAB                 |


| RE                            | Note                                                         |
| ------------------------------|--------------------------------------------------------------|
| :---                          |   :---                                                       |
| /\d\s\w/                      |   match a string of (a digit + some whitespace + a word)     |
| /\d{3}\s\w/{5}                |   match a string of (3 digits + 1 whitespace + 5 words)      |


# Special Characters


| Character  | Note                                                      |
| -----------|-----------------------------------------------------------|
| :---       |     :---                                                  |
| +          | match at least once (>=1 times)                           |
| \          | escape character                                          |
| []         | match any characters in the character set                 |
| [^]        | match characters not in the character set                 |
| ?          | match 0 or 1  time, make the preceding character optional |
| .          | match any character except a newline                      |    
| *          | match 0 or more times                                     |


1. ?
re: /hello?/
making character 'o' optional


| Strings                       | Result             | Note                                |
| ------------------------------| -------------------|-------------------------------------|
| :---                          |     :---:          |     :---                            |
| hello  hell                   |   match            |    match the 2 strings              |


re: /he?llo?/
making character 'o' optional


| Strings                       | Result             | Note                                |
| ------------------------------| -------------------|-------------------------------------|
| :---                          |     :---:          |     :---                            |
| hello   hllo   hell  hll      |   match            |    match the 4 strings              |


re: /a[a-z]?/
making character [a-z] optional


| Strings                       | Result             | Note                                |
| ------------------------------| -------------------|-------------------------------------|
| :---                          |     :---:          |     :---                            |
| a    ab    az                 |   match            |    match the 3 strings              |


2. dot (.)
re: /car./
making character [a-z] optional


| Strings                       | Result             | Note                                |
| ------------------------------| -------------------|-------------------------------------|
| :---                          |     :---:          |     :---                            |
| car                           |   no               |  needs to be 4-character long       |
| cars   card   car@            |   match            |  match the 3 strings                |



re: /.+/
any character except a newline, can be any length.


| Strings                       | Result             | Note                                |
| ------------------------------| -------------------|-------------------------------------|
| :---                          |     :---:          |     :---                            |
| a389^$#!F~934j###@#***        |   match            |                                     |


3. *
re: /a[a-z]*/
any character except a newline, can be any length.


| Strings                       | Result             | Note                                |
| ------------------------------| -------------------|-------------------------------------|
| :---                          |     :---:          |     :---                            |
| a  abeid                      |   match            |                                     |
| a  abeid1234                  |   Partially match  |  match alphabets except digits      |



4. Escape character: \
re: /abc\*/
any character except a newline, can be any length.


| RE                       |                                |
| -------------------------| -------------------------------|
| :---                     |  :---                          |
| abc\*                    |   abc*                         |             
| abc\+                    |   abc+                         |             
| abc\.                    |   abc.                         |


## Start and Ending Characters
re: /[a-z]{5}/


| String                      |      Result      | Note                          |
| ----------------------------|------------------|-------------------------------|
| :---                        |  :---:           | :---                          |           
| ninjaninjaninjaninja        |   match          | match  ninja once             |


re: /[a-z]{5}/g


| String                      |      Result      | Note                          |
| ----------------------------|------------------|-------------------------------|
| :---                        |  :---:           | :---                          |
| hello   ninja   world       |   match          | match the 3 strings           |
| ninjaninjaninjaninja        |   match          | match 5 times of ninja        |


1. ^ and $
re: /^[a-z]{5}$/g
the string must have 5 characters


| String                      |      Result      | Note                          |
| ----------------------------|------------------|-------------------------------|
| :---                        |  :---:           | :---                          |
| hello   ninja   world       |   match          | match the 3 strings           |
| ninjaninjaninjaninja        |   No             |                               |


re: /[a-z]{5}$/g
the string must have 5 characters


| String                      |      Result         | Note                                  |
| ----------------------------|---------------------|---------------------------------------|
| :---                        |  :---:              | :---                                  |
| ninjaninjaninjaninja        |  Partially match    |  Only match the last 5-characters     |


## Alternative Character: |  and Group ()


| RE                          | Note                                                     |
| ----------------------------|----------------------------------------------------------|
| :---                        |  :---                                                    |
| /p|t/                       |  Match  p or t                                           |
| /p|tyre/                    |  Match  p or tyre                                        |
| /pyre|tyre/                 |  Match  pyre or tyre                                     |
| /(p|t)yre/                  |  Match  pyre or tyre                                     |
| /(pet|toy|crazy) rabbit/    |  Match  pet rabbit, toy rabbit, crazy rabbit             |
| /(pet|toy|crazy)? rabbit/    |  Match  pet rabbit, toy rabbit, crazy rabbit, rabbit    |


ref: https://www.youtube.com/watch?v=m6iggPLGSMc&list=PL4cUxeGkcC9g6m_6Sld9Q4jzqdqHd2HiD
