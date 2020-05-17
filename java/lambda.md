## method references    

As you can see from these examples, the :: operator separates the method name
from the name of an object or class. There are three principal cases:  

• object::instanceMethod    
• Class::staticMethod   
• Class::instanceMethod   

In the first two cases, the method reference is equivalent to a lambda expression
that supplies the parameters of the method. As already mentioned, System.out::println
is equivalent to x -> System.out.println(x) . Similarly, Math::pow is equivalent to (x, y) ->
Math.pow(x, y) .

In the third case, the first parameter becomes the target of the method. For
example, String::compareToIgnoreCase is the same as (x, y) -> x.compareToIgnoreCase(y).    

