
**Recursion is a way to write a program in which the function call itself
 Applicaltions = Used in Dynamic programing , Divide and Conquer**

> [!NOTE] Print 1 to N
	 def f(n):
	    if n == 0:
	        return
	    f(n - 1)
	    print(n," ")
	f(4)


> [!NOTE] Sum of Digtis
	   def s(n):
	    if n == 0:
	        return 0
	    return n + s(n - 1)
	   print(s(2))


> [!NOTE] String palindrome or Not
		def isPal(str , start , end):
		    if start >= end:
		        return True
		    return (str[start] == str[end] and isPal(str,start+1,end-1))
		str = "abbcbba"
		start = 0
		end = len(str) - 1
		print(isPal(str,start,end))
