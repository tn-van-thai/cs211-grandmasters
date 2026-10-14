Profile: Ibrahim Hanif Ceker \
NetID: ihceke \
Major: Computer Science \
Favorite CS topic: Graph Theory \
Challenging topic: Geometry Algorithms \
Link to the question article: https://www.geeksforgeeks.org/dsa/largest-sum-contiguous-subarray/ \
My solution:

``` cpp
#include <stdio.h>
#include <limits.h>

int maxSubarraySum(int arr[], int n) {
    int max_sums[n]; //memoization array
    max_sums[0] = 0;
    for (int i = 1; i < n; i++) {
        if (max_sums[i - 1] < 0) {
            max_sums[i] = arr[i]; // case 1
        }
        else {
            max_sums[i] = max_sums[i - 1] + arr[i]; // case 2
        }
    }
    int max_sum = INT_MIN;
    // find the maximum of all sums ending at each index
    for (int i = 0; i < n; i++) {
        if (max_sums[i] > max_sum) {
            max_sum = max_sums[i];
        }
    }
    return max_sum;
}

int main() {
    int n;
    scanf("%d", &n);
    int arr[n];
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }
    printf("%d\n", maxSubarraySum(arr, n));
}
```