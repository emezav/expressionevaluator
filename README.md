# Arithmetic expression evaluator
Arithmetic expression evaluator based on the Shunting Yard Algorithm

C++ implementation of the Shunting Yard  Algorithm by E.W. Dijkstra.

Implementación en C++ del algoritmo Shunting Yard propuesto por E. W. Dijkstra.

Adaptado para aceptar variables, funciones personalizadas y el operador unario de negación "~"


# Shunting Yard Algorithm by Edsger Wybe Dijkstra (E. W. Dijkstra)
 (Wikipedia Version)
  https://en.wikipedia.org/wiki/Shunting_yard_algorithm

	while there are tokens to be read:
	  read a token
	  if the token is:
	  - a number:
	    put it into the output queue
	  - a function:
	    push it onto the operator stack 
	  - an operator o1:
	   while (
	     there is an operator o2 at the top of the operator stack which is not a left parenthesis, 
	     and (o2 has greater precedence than o1 or (o1 and o2 have the same precedence and o1 is left-associative))
	    ):
	       pop o2 from the operator stack into the output queue
	   push o1 onto the operator stack
	  - a left parenthesis (i.e. "("):
	    push it onto the operator stack
	  - a right parenthesis (i.e. ")"):
	    while the operator at the top of the operator stack is not a left parenthesis:
	      {assert the operator stack is not empty}
	       // If the stack runs out without finding a left parenthesis, then there are mismatched parenthesis. 
	        pop the operator from the operator stack into the output queue
	        {assert there is a left parenthesis at the top of the operator stack}
		pop the left parenthesis from the operator stack and discard it
		if there is a function token at the top of the operator stack, then:
			pop the function from the operator stack into the output queue
		
	// After the while loop, pop the remaining items from the operator stack into the output queue. 
	while there are tokens on the operator stack:
		// If the operator token on the top of the stack is a parenthesis, then there are mismatched parenthesis. 
	    {assert the operator on top of the stack is not a (left) parenthesis}
        pop the operator from the operator stack onto the output queue
