## Print the Asci
```
class A{
    public static void printAsci(String s){
        for(int i = 0 ; i < s.length() ; i++){
            char ch = s.charAt(i);
            System.out.println(ch+"=>"+(int)ch);
        }
    }
    public static void main(String args[]){
        printAsci("Aditya");
    }
}
```

## Count the digit , special character , character in a string
```
class A{
    public static void counttype(String s){
        int letter = 0;
        int digit = 0;
        int special = 0;
        for(int i = 0 ; i < s.length(); i++){
            char ch = s.charAt(i);
            if(Character.isLetter(ch)){
                letter++;
            }
            else if(Character.isDigit(ch)){
                digit++;
            }
            else{
                special++;
            }
        }
        System.out.println("Letter: "+letter);
        System.out.println("Digit: "+digit);
        System.out.println("Special: "+special);
    }
    public static void main(String args[]){
        counttype("a1@b2#");
    }
}
```

## Remove the Extra Space
```
class A{
    public static String remove(String s){
        return s.trim().replaceAll("\\s+"," ");
    }
    public static void main(String args[]){
        System.out.println(remove("  hello   world"));
    }
}
```

