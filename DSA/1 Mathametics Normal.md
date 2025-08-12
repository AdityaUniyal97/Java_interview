**Palindrome**
```
def ispal(n):
    res = 0
    temp = n
    while temp != 0:
        ld = temp % 10
        res = res * 10 + ld
        temp = temp // 10
    if res == n:
        print(True)
    else:
        print(False)
x = int(input("Enter x: "))
ispal(x)
```

**Factorial of a Number**
```
def fact(n):
    res = 1
    for i in range(2 , n + 1):
        res = res * i
    return res
    
n = int(input("Enter the x: "))
print(fact(n))
```

**GCD**
```
def gcd(a , b):
    if b == 0: 
        return a
    return gcd(b , a % b)
    
print(gcd(12,15))
```


**Prime Number**

> [!**Prime Number**] Brute Force
    def isPrime(n):
	    if n == 1:
	        return False
	    i = 2
	    while i * i <= n:
	        if n % i == 0:
	            return False
	        i = i + 1
	    return True
	    print(isPrime(65))


> [!NOTE] Optimsed 
	 def isPrime(n):
		if n == 1:
			return False
		if n == 2 or n == 3:
			return True
		if n % 2 == 0 or n % 3 == 0:
			return False
		i = 5
		while(i * i <= n):
			if n % i == 0 or n % (i + 2) == 0:
				return False
			i = i + 6
		return True
	   print(isPrime(65))


> [!NOTE] Prime Factorization
	   def isPrime(n):
			for i in range(2 , n):
				if n % i == 0:
					return False
			return True
	   def Pf(n):
			for i in range(2 , n + 1):
				if isPrime(i):
					x = i
					while n % x == 0:
						print(i)
						x = x * i
	print(Pf(100))


> [!NOTE] All Divisors of a Number
	def pd(n):
	    i = 1
	    while(i * i < n):
	        if (n % i == 0):
	            print(i)
	        i = i + 1
	    while(i >= 1):
	        if (n % i == 0):
	            print(int(n/i))
	        i = i - 1
	pd(15)


> [!NOTE] Power
	def power(x , n):
	    res = 1
	    while n > 0:
	        if n % 2 != 0:
	            res = res * x
	        x = x * x
	        n = n // 2
	    return res
	print(power(4 , 5))
