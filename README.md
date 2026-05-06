# Task-1
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
# Task-2
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
