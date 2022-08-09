# Expiration Manager - Dependency Injection

This is a small program that checks whether a list of files has expired, 
or reached its 30-day limit. It's based on Dependency Injection.

If any of the input files are expired, the program prints out their file names so you can delete them. 
In a real-world context, this technique is known as a [TTL](https://en.wikipedia.org/wiki/Time_to_live), 
or "Time to Live". 

TTLs are a common way for large systems to manage limited disk space 
and make sure it's not all being taken up by very old files that are never used. 
In the real world. In this example, the TTL is checked manually, 
but in many systems it happens as part of an automatic process.

The code is designed so that the class `ExpirationChecker` and `ExpirationCheckerTest` 
use `Dependency Injection`. 
This way will allow to inject real implementations of dependencies when running the program for real, 
and to use fake dependencies when running unit tests.

For this exercise, I use [Guice](https://github.com/google/guice), 
which is an open source dependency injection framework for Java.


## Compiling and Running

    javac -cp ".;lib/*" *.java
    java -ea -cp ".;lib/*" ExpirationCheckerTest

The test should pass, which means nothing will be printed to the command-line. 
If the test fail, it will throw an AssertionError.




