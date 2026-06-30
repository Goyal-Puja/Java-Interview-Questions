# Java-Interview-Questions

## 1. Why is String immutable in Java?
   - Security : String are heavily used in database URLs, file paths and network connections. </br>
   - Thread Safety : Immutable objects are naturally thread-safe. </br>
   - String pool optimization : Java can reuse String objects efficienly. </br>

## 2. Why does HashMap allow one null key while HashTable does not?
   - HashMap allows one null key because it handles null manually and is not synchronized. so there is no ambiguity during retrieval. it used bucket index 0 for null key.
   - HashTable being synchronized and thread-safe, does not allow null key or value because in concurrent environment a null from get would be ambigous - it would be clear whether the key is absent or mapped to null. To avoid this ambiguity, HashTable prohibits null entrirely.
