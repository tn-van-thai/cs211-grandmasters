# Profile: Mykyta Holovko

- NetID: mholo
- Major: Computer Science
- Question that I chose from the memoization exercise: Climbing stairs to reach the top
- Link to the question article: https://www.geeksforgeeks.org/dsa/count-ways-reach-nth-stair/
- My solution:

#include <stdio.h>



int climbStairs(int n) {

    if (n <= 2) {

        return 1;

    }



    return climbStairs(n - 1) + climbStairs(n - 2);

}



int main() {

    int n = 4;

    printf("Ways: %d\n", climbStairs(n));

    return 0;

}

