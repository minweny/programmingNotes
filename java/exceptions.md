## declare multiple checked exceptions  
If a method might throw more than one checked exception type, you must list
all exception classes in the header. Separate them by commas, as in the following
example:    
```
class MyAnimation
{
    . . .
    public Image loadImage(String s) throws FileNotFoundException, EOFException
    {
        . . .
    }
}
```

## unchecked exceptions = Error + RuntimeException  
unchecked exceptions include Error, RuntimeException. They are all exceptions.   

## declare all checked exceptions in method,  examine all of the codes in unchecked exceptions(Error + RuntimeException)    
However, you do not need to advertise internal Java errors—that is, exceptions
inheriting from Error . Any code could potentially throw those exceptions, and
they are entirely beyond your control.    

Similarly, you should not advertise unchecked exceptions inheriting from
RuntimeException.   
```
class MyAnimation
{
    . . .
    void drawImage(int i) throws ArrayIndexOutOfBoundsException // bad style
    {
        . . .
    }
}
```

These runtime errors are completely under your control. If you are so concerned
about array index errors, you should spend your time fixing them instead of
advertising the possibility that they can happen.   

In summary, a method must declare all the checked exceptions that it might throw.
Unchecked exceptions are either beyond your control ( Error ) or result from condi-
tions that you should not have allowed in the first place ( RuntimeException ). If your
method fails to faithfully declare all checked exceptions, the compiler will issue
an error message.   

## catch multiple exception types in the same catch clause      
```
try
{
    code that might throw exceptions
}
catch (FileNotFoundException | UnknownHostException e)
{
    emergency action for missing files and unknown hosts
}
catch (IOException e)
{
    emergency action for all other I/O problems
}
```

## finally  
Let us look at the three possible situations in which the program will execute the
finally clause. 

1. The code throws no exceptions. In this case, the program first executes all
the code in the try block. Then, it executes the code in the finally clause. After-
wards, execution continues with the first statement after the finally clause.
In other words, execution passes through points 1, 2, 5, and 6. 

2. The code throws an exception that is caught in a catch clause—in our case, an
IOException . For this, the program executes all code in the try block, up to the
point at which the exception was thrown. The remaining code in the try block
is skipped. The program then executes the code in the matching catch clause,
and then the code in the finally clause.    

If the catch clause does not throw an exception, the program executes the first
line after the finally clause. In this scenario, execution passes through points
1, 3, 4, 5, and 6.  

If the catch clause throws an exception, then the exception is thrown back to
the caller of this method, and execution passes through points 1, 3, and 5 only.    

3. The code throws an exception that is not caught in any catch clause. Here, the
program executes all code in the try block until the exception is thrown.
The remaining code in the try block is skipped. Then, the code in the finally
clause is executed, and the exception is thrown back to the caller of this
method. Execution passes through points 1 and 5 only.   

## try with resources   
```
try (Scanner in = new Scanner(new FileInputStream("/usr/share/dict/words"), "UTF-8"))
{
    while (in.hasNext())
    System.out.println(in.next());
}
```
