# Java-Interview-Questions

## 1. Why is String immutable in Java?
   - Security : String are heavily used in database URLs, file paths and network connections. </br>
   - Thread Safety : Immutable objects are naturally thread-safe. </br>
   - String pool optimization : Java can reuse String objects efficienly. </br>

## 2. Why does HashMap allow one null key while HashTable does not?
   - HashMap allows one null key because it handles null manually and is not synchronized. so there is no ambiguity during retrieval. it used bucket index 0 for null key.
   - HashTable being synchronized and thread-safe, does not allow null key or value because in concurrent environment a null from get would be ambigous - it would be clear whether the key is absent or mapped to null. To avoid this ambiguity, HashTable prohibits null entrirely.

 ## 3. What is the difference between final, finally, and finalize() in Java?
    - Final is used to define constants, prevent method overriding and prevent inheritance. when a variable is declared ad final, its value can't be changed. A method declared as final can't be overridden by subclass. A class declared as final can't be subclassed.
    - Finally is used in Exception Handling. it contains code that will always be executed after the try block, regardless of whether an exception was thrown or not. This is typically used for resource cleanup like closing files or database connections.
    - Finalize() is a method in the object class that is called by the garbage collector before an object is destroyed.
