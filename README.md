# CSPC Assignment Solutions

## Basic Maths
### Ques 1 : Count Digits

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

### Ques 2 : Reverse Digits

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

### Ques 3 : Palindrome Numbers

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

### Ques 4 : Armstrong Numbers
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

### Ques 5 : All divisors of a Number

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

### Ques 6 : Prime Number

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

### Ques 7 : GCD of two numbers

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

## STL Practice Problems

### Ques 1 : Vector Sort

``` cpp
#include <cmath>
#include <cstdio>
#include <vector>
#include <iostream>
#include <algorithm>
using namespace std;

int main() {
    int n;
    cin >> n;
    
    vector<int> v;
    for(int i = 0; i < n; i++) {
        int x;
        cin >> x;
        v.push_back(x);
    }
    sort(v.begin(), v.end());
    
    for(int i =0; i <n; i++) {
        cout << v[i] << " ";
    }
    cout << endl;
    return 0;
}
```

### Ques 2 : Vector Erase

``` cpp
#include <cmath>
#include <cstdio>
#include <vector>
#include <iostream>
#include <algorithm>
using namespace std;

int main() {
    int n;
    cin >> n;
    vector<int> v(n);
    for(int i =0; i <n; i++) {
        cin >> v[i];
    }
    int p;
    cin >> p;
    v.erase(v.begin() + p - 1);
    
    int a, b;
    cin >> a >> b;
    
    v.erase(v.begin() + a - 1, v.begin() + b - 1);
    cout << v.size() << endl;
    for(int i = 0; i < v.size(); i++) {
        cout << v[i] << " ";
    }
    cout << endl;
    return 0;
}
```

### Ques 3 : Lower Bound STL

``` cpp
#include <cmath>
#include <cstdio>
#include <vector>
#include <iostream>
#include <algorithm>
using namespace std;


int main() {
    int n;
    cin >> n;
    vector<int> v(n);
    for(int i = 0; i < n; i++) {
        cin >> v[i];
    }
    int q;
    cin >> q;
    for(int i = 0; i < q; i++) {
        int query;
        cin >> query;
        auto it = lower_bound(v.begin(), v.end(), query);
        int idx = it - v.begin();
        if(it != v.end() && *it == query) {
            cout << "Yes " << idx + 1 << endl ;
        }
        else {
            cout << "No " << idx + 1 << endl;
        }
    }
    return 0;
}
```

### Ques 4 : Sets STL

``` cpp

```

### Ques 5 : Maps STL

``` cpp

```

### Ques 6 : Dequeue STL

``` cpp

```