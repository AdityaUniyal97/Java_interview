**DRY(Dont Repeat Yourself)**
- Avaoiding repeation of the Logic or the Code
- Instead write the logic in the function or in a class to use in multiple places
- Ex = BAD Approch
```
int area1 = l1 * w1;
int area2 = l2 * w2;
```
- GOOD Approch
```
int solve(int l , int w){
	return l * w;
}
```
**Importance of the DRY**
- Reduce the Redundency
-  Easier to Maintain
- Single point of change
**How to Apply**
- Extract the Code which seem to be apperaing multiplt places
- And than write it in a separate function or in a class
Ex = Storing URL in specific function and claling it , instead of writing everytime
### When Not to use DRY
- Premature Abstraction = Combining code too early , which makes common code base huge and hard to manage
- Performace Ciritical Code = is that part of the code , where speed and memory matters a lot . Even a small slowdown here can affect the whole system. Ex TUF
- Legacy Code = Breaking the existiing behaviuor code

## KISS = Keep it Simple , Stupid
- Keeping the design in the simplest and in stupid form for readability , only make it complex when needed it(like in OOPS)
**WHY**
- easy to read
- easy to debug
- faster to write
EX => **BAD**
```
boolean isEven(int n){
	boolean result;
	if(n % 2 == 0){
		result = true;
	}
	else{
		result = false;
	}
	return result;
}
```
**GOOD CODE**
```
boolean isEven(int n){
	return n % 2 == 0;
}
```

## YAGNI(You Aren't Gonna Need it)
**Always implement things when you actually needed it.**
**Importance**
- Save time
- avoid unnecessary complexity
- keep code clean
### When to use it
- When a feature is confirmed and coming soonlll  
- Performance C