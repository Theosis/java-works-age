Congratulations! You've just been commissioned to do your first Java project!



Your client wants a Java program to determine her clients' ages. 

She's OK with running it in the command line for now, but she's very 

picky about her requirements. 



She says each client will have to enter the day, month and year of birth. 

Since she has about 50 clients, she wants the program to ask 

the following after each entry: 



"Would you like to enter details for another client?"



When the user presses the Y key, the program will start over again

asking for details of the user's day, month and year of birth. 



When the user presses the N key ,the program will end, saying 

"Thanks for using the age calculator!"



So...

You've been tasked to write this program, but you have to: 



1. Provide an IPO diagram and an algorithm

2. Develop pseudocode for this project 

3. Develop the code (and make sure it works!!!)

_____________________________________________________________


1. IPO + Algorithm

INPUT
Prompt for and get user to enter birthDay, birthMonth, birthYear.
Once done with client ask "Would you like to enter details for another client?" 
and get user to enter Y/N to continue. 

OUTPUT
Display calculated age.
On exit, program should print "Thanks for using the age calculator!".

PROCESS


Algorithm

Obtain current year, month and day of the month.
Get user input and validate it. If it's invalid, notify user and repeat.
Calculate age by substracting birth year from current year, then 
if current day in year is before birth day in birth year, substract one.
Display age.
Confirm user wants to continue, otherwise bid farewell and end program.


Pseudocode

PRINT Greeting
REPEAT

  REPEAT 
    PROMPT user to enter and INPUT birthDay, birthMonth, birthYear
    LET birthDate = DATE(birthDay, birthMonth, birthYear)
    LET validDate = VALIDATE(birthDate)
    IF NOT validDate THEN PRINT "Invalid birth data - Try again"
  UNTIL validDate

  LET currYear  = YEAR(TODAY)
  LET currMonth = MONTH(TODAY)
  LET currDay   = DAY(TODAY)

  LET age = currYear - birthYear
  IF (currMonth  < birthMonth) OR 
     ( (currMonth == birthMonth) AND (currDay < birthDay) ) 
     THEN
          age = age - 1
  ENDIF

  PRINT "Age = ", age

  PROMPT "Would you like to enter details for another client? "

  REPEAT
    INPUT userConfirm
  UNTIL userConfirm in [YN]

UNTIL userConfirm = "N"

PRINT "Thanks for using the age calculator!"
END

