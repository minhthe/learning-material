1. Checked Exception vs Unchecked exception
- Checked exception 
    - represents error outside the control of program
    - example: IOException, SQLException
- Unchecked exception
    - represents error inside program's logic
    - example: NullPointerException, IllegalArgumentException
- If a client can reasonably be expected to recover from an exception => 
use Checked Exception
- If a client cannot do anything to recover from the exception => use 
Unchecked Exception

2. Why String is immutable?
- Java designer knows that String is going to be used widely => 
they want to optimize from start: String pool - to reduce the temporary
String object by sharing them => you cannot share a mutable object
with 2 parties
- Make String thread safe
- Security
- Optimization: e.g. cache hashcode() value

3. Heap vs Stack space
- Stack memory is used to store local variable, Heap memory is used to 
store object
- Each thread has its own stack memory, heap memory is shared between threads

4. hashCode() and equals()
- hashCode() return an int hash value corresponding to an object.
- hashCode() is used in hash based collection to determine the bucket
in which the hash value is stored.
- the contract of hashCode(): 
    - if x.equals(y) then x.hashCode() == y.hashCode(),
otherwise thing would go wrong when we use x, y as key of a HashMap
    - if we execute hashCode() again and again on the same object,
    it should return the same value.

=> if we override equals(), we must override hashCode()

