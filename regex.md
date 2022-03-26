# cheatsheet for regular expressions

match 5 digit number

    ^[0-9]{5}$

match any number

    ^[0-9]+$

do not match numbers

    ^[^0-9]+$

match phone number with optional dashes. e.g. 850-555-2345

    ^[0-9]{3}-?[0-9]{3}-?[0-9]{4}$

match an email. e.g. bob.smith@example.org

    ^[a-zA-Z0-9._-]+@[a-zA-Z0-9]+\.[a-zA-Z]{2,3}$
    ^[\w\d._-]+@[\w\d]+\.[\w]{2,3}$  

\w and \d also match numbers in foreign languages and little bit more
