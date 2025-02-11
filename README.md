# CSPC Assignment Solutions

## Basic Maths
### Ques1 : Count Digits

``` java
class Solution {
    static int evenlyDivides(int n) {
        int count = 0;
        int num = n;
        while (num > 0) {
            int digit = num % 10;
            num /= 10;
            if (digit == 0) continue;
            if(n % digit == 0) count++;
        }
        return count;
    }
}
```

### Ques2 : Reverse Digits

``` java
class Solution {
    public int reverseDigits(int n) {
        int sign = (n >= 0) ? 1 : -1;
        n = Math.abs(n);
        int reversedDigit = 0;
        while(n > 0) {
            int rem = n % 10;
            n /= 10;
            reversedDigit = (reversedDigit * 10) + rem;
        }
        
        return reversedDigit * sign;
    }
}
```

### Ques3 : Palindrome Numbers

``` java
class Solution{
    static long isPallindrome(long N){
        String binaryNumber = Long.toBinaryString(N); 
        int lo = 0;
        int hi = binaryNumber.length() - 1;
        
        while(lo < hi) {
            if(binaryNumber.charAt(lo) != binaryNumber.charAt(hi)) {
                return 0; 
            }
            lo++;
            hi--;
        }
        
        return 1;
    }
}
```

### Ques4 : Armstrong Numbers
``` java
class Solution {
    static boolean armstrongNumber(int num) {
        int n = num;
        int sum = 0;

        while (n != 0) {
            int digit = n % 10;
            sum += Math.pow(digit, 3);
            n /= 10;
        }

        return sum == num;
    }
}
```

### Ques5 : All divisors of a Number

``` java
class Solution {
    public static void print_divisors(int n) {
        ArrayList<Integer> divisors = new ArrayList<>();
        
        for(int i = 1; i * i <= n; i++) {
            if(n % i == 0) {
                divisors.add(i); 
                if(i != n / i) {
                    divisors.add(n / i); 
                }
            }
        }
        
        Collections.sort(divisors);
        for (int d : divisors) {
            System.out.print(d + " ");
        }
    }
}
```

### Ques6 : Prime Number

``` java
class Solution {
    static boolean isPrime(int n) {
        if(n <= 1) return false;
        for(int  i = 2; i*i <= n; i++) {
            if(n % i == 0) return false;
        }
        return true;
    }
}
```

### Ques7 : GCD of two numbers

``` java
class Solution {
    public static int gcd(int a, int b) {
        while (b != 0) {
            int temp = b;
            b = a % b;
            a = temp;
        }
        return a;
    }
}
```
