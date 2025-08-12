
> [!NOTE] **Array**
> **Array is a linear Data Structure which is used to store the multiple items together in one place and these items are of same data type** 
> **In Array elements are stored in a contigues memory**
> **In Array elements can be accessed through indexing**
> **Advantage**
> **- Random Access**
> **- Cache Friendlyness**
> **Types of Array:>**
> **1) Fixed Size Array:= These are the array which dont allow the elements more than the defined size**
>    **int[] = arr{10,20,30}**
> **2) Dynamic Size Array:= These are the array which can resize themselves internally based upon the input provided ,**
>     **ex = Array List**
>  
>     


> [!NOTE] List - Item Printing
	i = [10,20,30,40]
	print(i)
	print(i[1])
	print(i[-1])


> [!NOTE] Separate Even & Odd
	def eo(l):
	    e = []
	    o = []
	    for i in l:
	        if i % 2 == 0:
	            e.append(i)
	        else:
	            o.append(i)
	    return e,o
	l = [10,11,11,16]
	e,o = eo(l)
	print(eo(l))

> [!NOTE] Get Smaller Element than X
	def small(l,x):
	    e = []
	    for i in l:
	        if i < x:
	            e.append(i)
	    return e
	l = [8,100,20,40,3,7]
	e = small(l,10)
	print(e)

> [!NOTE] Greter Element in the List
	def gl(l):
	    if not l:
	        return None
	    else:
	        res = l[0]
	        for i in range(1 , len(l)):
	            if l[i] > res:
	                res = l[i]
	    return res
	l = [10,200,30,400,100]
	print(gl(l))

> [!NOTE] Second largest
	def sl(l):
	    if len(l) <= 1:
	        return None
	    lar = l[0]
	    slar = None
	    for i in l[1:]:
	        if i > lar:
	            slar = lar
	            lar = i
	        elif i != lar:
	            if slar == None or slar < i:
	                slar = i
	    return slar
	l = [1,2,3,100,200]
	print(sl(l))


> [!NOTE] Is List Sorted or Not
			def isSor(l):
			    i = 1
			    while i < len(l):
			        if l[i] < l[i - 1]:
			            return False
			        i = i + 1
			    return True
			l = [10,20,30,15,40]
			print(isSor(l))
		     def isSor(l):
			    sl = sorted(l)
			    if sl == l:
			        return True
			    else:
			        return False
		     l = [10,20,30,15,40]
		     print(isSor(l))
	

> [!NOTE] Reverse the List
	 def rev(l):
	    s = 0
	    e = len(l) - 1
	    while s < e:
	        l[s] , l[e] = l[e] , l[s]
	        s+=1
	        e-=1
	l=[10,20,30]
	rev(l)
	print(l)


> [!NOTE] Remove the Dupplicates form the List
	def rmd(l,n):
	    res = 0
	    for i in range(1 , n):
	        if l[res] != l[i]:
	            l[res] = l[i]
	            res+=1
	    return res
	l = [10,10,10,20,20,30]
	n = len(l)
	print(rmd(l,n))


> [!NOTE] Shift first element to last
	 def isl(l):
	    n = len(l)
	    m = l[0]
	    for i in range(n):
	        l[i - 1] = l[i]
	    l[n-1]=m
	l = [10,20,30]
	isl(l)
	print(l)
