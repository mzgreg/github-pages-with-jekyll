Flow of execution and variable scope

In my Udemy class, a student asked why the output of the below function is 100 and not 50. Here, I take a stab at answering.

      num = 100
      def scope_practice(num):
         num = 50
         print(f'The number is {num}.')

      print(num)

Python’s flow of execution reads statements from top to bottom, ignoring indented code until it is called to execute the function. Therefore in the above example, it reads line 1, line 2, and then line 6 where it is called to execute. Because the call to execute is print function ‘print(num)’ and not a call to the definition ‘scope_practice(),’ 
Python does not read the indented code, instead returning ‘num’ from the global variable assignment ‘num = 100.’ This ‘num’ is considered a global variable because it is the name at the top-level of a file.

      num = 100
      def scope_practice(num):
        num = 50
        print(f'The number is {num}.')

      scope_practice()

Placing a call to the function ‘scope_practice()’ will return ‘The number is 50.’ Python follows the same flow of execution, but this time it is called to execute the function ‘scope_practice()’, so it will read lines 1, 2, 6 and then will read 3 and 4, where it finds the local variable assignment ‘num = 50;’ it will then return the print statement with ‘num’ being equal to 50. 
