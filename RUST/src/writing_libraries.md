When building a library, you do not pass data structures with editable/accessible data... 
    - you pass functions
    - functions bundled as traits
    - A struct that only exposes functions ... not data. users should never have to know how data is organized within a struct... their code should never change because you changed some data structures

Point being : expose fuctions ONLY if possible. But never pass an editable/accessible **data** structure


Validate all data coming in. For example, if you are writing a gui library that consumes a html file, make sure the html file is of the right format.  


## Error handling
- Return Results that have the same Mother <Ok, Err<my_library::mod_1_error>>
- Make the error impl the Error trait