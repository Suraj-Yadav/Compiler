all:	Interpreter.exe
Interpreter_lex.cpp:	Interpreter.l
		flex  -oInterpreter_lex.cpp Interpreter.l
Interpreter.cpp:	Interpreter.y 
		bison -d -oInterpreter.cpp Interpreter.y
Interpreter.o: Interpreter.cpp Interpreter.hpp
		g++ -Wunreachable-code -std=c++11 -Wextra -Wall -c Interpreter.cpp -o Interpreter.o
Interpreter_lex.o: Interpreter_lex.cpp Interpreter.hpp
		g++ -Wunreachable-code -std=c++11 -Wextra -Wall -c Interpreter_lex.cpp -o Interpreter_lex.o
syntaxTree.o: syntaxTree.cpp syntaxTree.h Interpreter.hpp
		g++ -Wunreachable-code -std=c++11 -Wextra -Wall -c syntaxTree.cpp -o syntaxTree.o
Interpreter.exe:	Interpreter.o Interpreter_lex.o syntaxTree.o
		g++.exe -o Interpreter.exe Interpreter.o Interpreter_lex.o syntaxTree.o
clean:
		rm -f Interpreter_lex.cpp
		rm -f Interpreter.cpp
		rm -f Interpreter.hpp
		rm -f Interpreter.o
		rm -f Interpreter_lex.o
		rm -f Interpreter.exe
		rm -f syntaxTree.o