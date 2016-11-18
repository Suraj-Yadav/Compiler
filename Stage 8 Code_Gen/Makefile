all:	compiler.exe
compiler_lex.cpp:	compiler.l
		flex  -ocompiler_lex.cpp compiler.l
compiler.cpp:	compiler.y 
		bison -d -ocompiler.cpp compiler.y
compiler.o: compiler.cpp compiler.hpp
		g++ -Wunreachable-code -std=c++11 -Wextra -Wall -c compiler.cpp -o compiler.o
compiler_lex.o: compiler_lex.cpp compiler.hpp
		g++ -Wunreachable-code -std=c++11 -Wextra -Wall -c compiler_lex.cpp -o compiler_lex.o
symbolTable.o: symbolTable.cpp symbolTable.h compiler.hpp
		g++ -Wunreachable-code -std=c++11 -Wextra -Wall -c symbolTable.cpp -o symbolTable.o
syntaxTree.o: syntaxTree.cpp syntaxTree.h compiler.hpp symbolTable.h 
		g++ -Wunreachable-code -std=c++11 -Wextra -Wall -c syntaxTree.cpp -o syntaxTree.o
compiler.exe:	compiler.o compiler_lex.o syntaxTree.o symbolTable.o
		g++ -o compiler.exe compiler.o compiler_lex.o syntaxTree.o symbolTable.o 
clean:
		rm -f compiler_lex.cpp
		rm -f compiler.cpp
		rm -f compiler.hpp
		rm -f compiler.o
		rm -f compiler_lex.o
		rm -f compiler.exe
		rm -f syntaxTree.o
		rm -f symbolTable.o