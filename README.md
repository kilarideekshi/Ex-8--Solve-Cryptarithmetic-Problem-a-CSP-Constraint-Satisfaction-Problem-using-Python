<h1>ExpNo 8 : Solve Cryptarithmetic Problem,a CSP(Constraint Satisfaction Problem) using Python</h1> 
<h3>Name:  Deekshitha K  </h3>
<h3>Register Number: 2305002005   </h3>
<H3>Aim:</H3>
<p>
    To solve Cryptarithmetic Problem,a CSP(Constraint Satisfaction Problem) using Python
</p>
<h3>Procedure:</h3>
Input and Output
<br>Input:
This algorithm will take three words.
<br> B A S E<br>
    B A L L<br>
           ----------<br>
           G A M E S<br>

Output:
It will show which letter holds which number from 0 – 9.
For this case it is like this.

              B A S E                         2 4 6 1
              B A L L                         2 4 5 5
             ---------                       ---------
            G A M E S                       0 4 9 1 6
Algorithm
For this problem, we will define a node, which contains a letter and its corresponding values.<br>

isValid(nodeList, count, word1, word2, word3)<br>

Input − A list of nodes, the number of elements in the node list and three words.<br>

Output − True if the sum of the value for word1 and word2 is same as word3 value.<br>

Begin<br>
   m := 1<br>
   for each letter i from right to left of word1, do<br>
      ch := word1[i]<br>
      for all elements j in the nodeList, do<br>
         if nodeList[j].letter = ch, then<br>
            break<br>
      done<br>
      val1 := val1 + (m * nodeList[j].value)<br>
      m := m * 10<br>
   done<br>

   m := 1<br>
   for each letter i from right to left of word2, do<br>
      ch := word2[i]<br>
      for all elements j in the nodeList, do<br>
         if nodeList[j].letter = ch, then<br>
            break<br>
      done<br>

      val2 := val2 + (m * nodeList[j].value)
      m := m * 10
   done<br>

   m := 1<br>
   for each letter i from right to left of word3, do<br>
      ch := word3[i]<br>
      for all elements j in the nodeList, do<br>
         if nodeList[j].letter = ch, then<br>
            break<br>
      done<br>

      val3 := val3 + (m * nodeList[j].value)
      m := m * 10
   done<br>

   if val3 = (val1 + val2), then<br>
      return true<br>
   return false<br>
End<br>

<hr>
<h2>Sample Input and Output:</h2>
CROSS = 96233

ROADS = 62513
<hr>
MONEY = 10652<br>

## PROGRAM
```Python

from itertools import permutations
def solve_cryptarithmetic():
    for perm in permutations(range(10), 9):  
        C, R, O, S, A, D, N, G, E = perm

        if C == 0 or R == 0 or D == 0:
            continue

        CROSS = 10000 * C + 1000 * R + 100 * O + 10 * S + S
        ROADS = 10000 * R + 1000 * O + 100 * A + 10 * D + S
        DANGER = 100000 * D + 10000 * A + 1000 * N + 100 * G + 10 * E + R

        if CROSS + ROADS == DANGER:
            return CROSS, ROADS, DANGER

    return None
solution = solve_cryptarithmetic()

if solution:
    CROSS, ROADS, DANGER = solution
    print(f'CROSS = {CROSS}')
    print(f'ROADS = {ROADS}')
    print(f'DANGER = {DANGER}')
else:
    print("No solution found.")
```

## output

<img width="278" height="78" alt="image" src="https://github.com/user-attachments/assets/f4e5d5fd-5af2-4029-bea3-1d41d1980986" />



<hr>
<h2>Result:</h2>
<p> Thus a Cryptarithmetic Problem was solved using Python successfully</p>
