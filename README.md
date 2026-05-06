# Task-1 (Java code)
```java
public class Harshad {
    public static void main(String[] args) {
        if(args.length == 0) { // No input value
            System.out.println("No input provided");
            return;
        }
        for(int i = 0; i < args.length; i++) { // Input from cmd
            int x = Integer.parseInt(args[i]);
            int sum = 0, temp = x;
            // Calculate digit sum
            while (temp > 0) { 
                sum += temp % 10;
                temp /= 10;
            }
            // Check Harshad number
            if (sum != 0 && x % sum == 0) System.out.println("YES");
            else System.out.println("NO");
        }
    }
}
```
# Task-2 (Java code)
```java
class Solution {
public:
    int sumOfTheDigitsOfHarshadNumber(int x) {
        int sum = 0, temp = x;
        // Calculate digit sum
        while (temp > 0) {
            sum += temp % 10;
            temp /= 10;
        }
        // Check Harshad number
        if (x % sum == 0) return sum;
        else return -1;
    }
};
```
# Task-3 (C++ code)
```java
#include<bits/stdc++.h>

#define int long long
#define endl '\n'
#define asc(x) (x).begin(), (x).end()
#define des(x) (x).rbegin(), (x).rend()

using namespace std;
#undef int

void solve(vector<int>& Devlali, int tc) {

    int a, b;
    cin >> a >> b;
    if(a > 0) a -= 1;
    cout << Devlali[b] - Devlali[a];
    cout << endl;

}

int main() {

#ifndef ONLINE_JUDGE
    freopen("input.txt", "r", stdin);
    freopen("output.txt", "w", stdout);
#endif

    ios::sync_with_stdio(false); 
    cin.tie(0);

    // Calculate Digit Sum
    set<int> DigitSum;
    for(int i = 0; i <= 1000000; i++) {
        int temp = i, sum = 0;
        while(temp > 0) {
            sum += temp % 10;
            temp /= 10;
        }
        DigitSum.insert(i + sum);
    }
    // Find Prime Numbers with Sieve
    int n = 1000001;
    vector<bool> primes(n, 1);
    primes[0] = 0; 
    primes[1] = 0;
    for(int i = 2; i * i < n; i++) {
        if(primes[i] == 1) {
            for(int j = i * i; j <= n; j += i) primes[j] = 0;
        }
    }
    // Find Devlali Numbers
    int cnt = 0;
    vector<int> Devlali(n);
    for(int i = 0; i < n; i++) {
        if(primes[i]) {
            if(DigitSum.count(i) != 1) cnt++;
        }
        Devlali[i] = cnt;
    }
    int t = 1;
    cin >> t;
    for(int c = 1; c <= t; c++) solve(Devlali, c);

}
```
