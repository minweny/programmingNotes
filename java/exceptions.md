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

