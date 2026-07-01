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

## 4. Functional Interface and Maker Interface
   - A Functional Interface contains exactly one abstract method and is designed to support Lambda expression and Method reference.
   - A Maker Interface has no method or field at all and used to attach meta data or runtime capabilities to an object/

## 5. Which collection have we used most in production - HashMap or ConcurrentHashMap?
   - In production, HashMap is used for more frequently because most data staructures are not shared across thread, and it provides better performance.
   - ConcurrentHashMap is used only in scenario where multiple thread need to safely access and modify the map.

## 6. How does java handle memory leaks?
   - Java automatically handles memory leaks through garbage collection. The JVM identifies and frees up memory that is no longer being used by the application.

## 7. Comparable and Comparator Interface
   ### In Java, both Comparable and Comparator are interface used for sorting objects.
   - The Comparable interface is used to define the natural ordering of objects. A class that implement Comparable must override the CompareTo() method, which compares the current object with another object of the same type.
   - The Comparator interface is used to define myltiple ways of sorting objects. Unlike Comparable, we don't need to modify the class whose objects we want to sort. Instead, we create separate class that implements the Comparator interface and override the Compare() method.

## 8. String Builder and String Buffer
   - String Builder is not thread safe, faster and it is not synchronized.
   - String Buffer is thread safe, slower as compared to string Builder and it is synchronized.
   - if we are working with singly thread environment and we don't need thread safety in this case, we can prefer string builder due to its better performance.

## 9. Checked and Unchecked Exception 
   - Checked eexceptions are exceptions that are checked at compile-time. ( IOException, SQLException, ClassNotFoundException )
   - Unchecked exceptions are exceptions that are not checked at compile-time. These exceeptions are subclass of RunTimeException.   ( ArithmeticException, NullPointerException, ArrayIndexOutOfBoundsException )

## 10. User-defined Exceptions
   - User-defined exceptuons are the exceptions created by the programmers to use their own designed exception and those are not present in the java exception library.
   ### To create a user-defined exception :
   - Create a class that extends Exception ( for checked exception ) or RunTimeException ( for unchecked exception ).
   - Provide constructor to initialize the exception with custom messages.

## 11. MYSQL and MongoDB
   - Mysql is a relational database management system (RDMS) based on SQL, with fixed schema and structured data storage. it is suitable for applications with well defined schemas and relationships. Example : An e-commerce website where we need to store information about users, products, orders and payments. we would define tables such as 'users', 'products' and 'payments' with predefined columns like user_id, product_name, order_date etc. we would establish relationships between these tables using foreign keys.
   - MongoDb is NoSQL database that uses a flexible, schema-less document model. it is designed for scalability, high performance and handling unstructured and semi-structured data. Example : A blogging platform where users can create posts with different structures and tags. we would have a collection named 'posts' where each document represents a post. The document structure can vary from post to post; some have additional field like 'tags', 'comments' or 'attachments'. MongoDB allow for flexible schema design with predefined structures.

   - Add methods to provide additional deatails about the exception.

