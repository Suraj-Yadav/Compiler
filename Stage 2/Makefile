all:	expression.exe
expression_lex.cpp:	expression.l
		flex  -oexpression_lex.cpp expression.l
expression.cpp:	expression.y 
		bison -d -oexpression.cpp expression.y
expression.o: expression.cpp expression.hpp
		g++ -Wunreachable-code -std=c++11 -Wextra -Wall -c expression.cpp -o expression.o
expression_lex.o: expression_lex.cpp expression.hpp
		g++ -Wunreachable-code -std=c++11 -Wextra -Wall -c expression_lex.cpp -o expression_lex.o
exptree.o: exptree.cpp exptree.h expression.hpp
		g++ -Wunreachable-code -std=c++11 -Wextra -Wall -c exptree.cpp -o exptree.o
expression.exe:	expression.o expression_lex.o exptree.o	
		g++ -o expression.exe expression.o expression_lex.o exptree.o 
clean:
		rm -f expression_lex.cpp
		rm -f expression.cpp
		rm -f expression.hpp
		rm -f expression.o
		rm -f expression_lex.o
		rm -f expression.exe
		rm -f exptree.o