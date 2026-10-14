Tuan Van Thai \
Computer Science \
Competitive Programming \
Competitive Programming

```cpp
int maxSubarraySum(int arr[], int n) {
    #define min(a, b) ((a) < (b) ? (a) : (b))
    #define max(a, b) ((a) > (b) ? (a) : (b))
    
    int res = arr[0], sum = 0;
    for (int i = 0; i < n; i++){
        sum = max(sum + arr[i], arr[i]);
        res = max(res, sum);
    }
    
    return res;
}
```