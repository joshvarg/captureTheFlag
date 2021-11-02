# BASIC
Type:  _"reverse engineering"_

## Given Materials:
ti84plus.rom --- A ROM file that can emulate a TI-84 calculator
BASIC.8xp ------ A program that can run on a TI-84 calculator

## First Impression
.rom file indicates the need for an emulator to run. A quick search shows that .8xp files are programs to run on Texas Instrument calculators. Using the emulator from [this site](https://www.cemetech.net/projects/jstified/), I was able to 
    1. run the rom file and 
    2. upload the .8xp file onto the emulated rom

Once the program is loaded, opening it within the TI-84 allows you to edit the program and see the "source code" as shown below.
!["BASIC.8xp program under Edit mode in calculator."](/images/BASIC-1.png)

## Solution
1. Reading the source code reveals that it is a program checking for a specific string. It does this by first establishing two variables:
    a. "F4X67ENQPK0{MTJRHL}O3G59UB-ZAWV8S2YI1CD" -> str2 (string assigned to str2)
    b. {26,25,38,10,6,35,6,12,13,2,14,17,27,38,18,29,23,23,27,30,2,33,27,26,11,16,37,7,22,19} -> L<sub>4</sub> (array of integers assigned to L<sub>4</sub>)

2. Next it runs an if statement within a for loop to check if the substring of str7 (user input) at index i matches the substring of str2 at index L<sub>4</sub>(i).

3. This tells us that the correct input is a string of 30 characters (length of L<sub>4</sub>) with each number of L<sub>4</sub> corresponding to the index of str2. i.e. 1 = F, 2 = 4, 3 = X, etc. The resulting string is represented in the flag format and thus is the flag. 

## Notes
- Writing a python script may have made finding the final string more efficient, however the string wasn't too long to sort out by hand so I just did that instead. 