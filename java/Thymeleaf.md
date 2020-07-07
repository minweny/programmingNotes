https://www.thymeleaf.org/doc/tutorials/3.0/usingthymeleaf.html#introducing-thymeleaf       

## Simple expressions:
Variable Expressions: ${...}        
Selection Variable Expressions: *{...}      
Message Expressions: #{...}     
Link URL Expressions: @{...}        
Fragment Expressions: ~{...}        

## Expressions on selections (asterisk syntax)
Not only can variable expressions be written as ${...}, but also as *{...}.

There is an important difference though: the asterisk syntax evaluates expressions on selected objects rather than on the whole context. That is, as long as there is no selected object, the dollar and the asterisk syntaxes do exactly the same.

And what is a selected object? The result of an expression using the th:object attribute. Let’s use one in our user profile (userprofile.html) page:

  <div th:object="${session.user}">
    <p>Name: <span th:text="*{firstName}">Sebastian</span>.</p>
    <p>Surname: <span th:text="*{lastName}">Pepper</span>.</p>
    <p>Nationality: <span th:text="*{nationality}">Saturn</span>.</p>
  </div>
Which is exactly equivalent to:

<div>
  <p>Name: <span th:text="${session.user.firstName}">Sebastian</span>.</p>
  <p>Surname: <span th:text="${session.user.lastName}">Pepper</span>.</p>
  <p>Nationality: <span th:text="${session.user.nationality}">Saturn</span>.</p>
</div>

