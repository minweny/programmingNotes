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
However, you do not need to advertise internal Java errors—that is, exceptions
inheriting from Error . Any code could potentially throw those exceptions, and
they are entirely beyond your control.    

Similarly, you should not advertise unchecked exceptions inheriting from
RuntimeException.   

