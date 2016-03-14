# The 3rd exercise
## Summury:
   In the following program edicted in python language,I try to type some letters in form of #.
   And it could also print letters in the opposite order that I input them.
   Finally,the program will automaticly line feed when the letters are too long for the screen.
## The program is edicted as following:
            import sys
            
            weightChar = 11
            heightChar = 5
            
            weightBoard = 50
            heightBoard = 6
            
            graphs = [["     #     ", \
                       "    # #    ", \
                       "   #####   ", \
                       "  #     #  ", \
                       " #       # "], \
                      ["  ######   ", \
                       "  #     #  ", \
                       "  ######   ", \
                       "  #     #  ", \
                       "  ######   "], \
                      ["   #####   ", \
                       "  #        ", \
                       " #         ", \
                       "  #        ", \
                       "   #####   "], \
                      ["   ####    ", \
                       "   #   #   ", \
                       "   #    #  ", \
                       "   #   #   ", \
                       "   ####    "]]
            
            
            def drawAt(graphBoard, graph, index):
                for i in range(heightChar):
                    for j in range(weightChar):
                        graphBoard[i][index + j] = graph[i][j];
            
            def printBoard(graphBoard):
                for i in range(heightBoard):
                    for j in range(weightBoard+1):
                        sys.stdout.write(graphBoard[i][j])
            
            def initBoard(graphBoard):
                for i in range(heightBoard):
                    graphBoard.append([]);
                    for j in range(weightBoard):
                        graphBoard[i].append('\0')
                    graphBoard[i].append('\n')
            
            def cleanBoard(graphBoard):
                for i in range(heightBoard):
                    for j in range(weightBoard):
                        graphBoard[i][j] = '\0'
            
            graphBoard = []
            initBoard(graphBoard)
            
            command = raw_input("\nenter the string: (ex. abcd)\n")
            length = len(command)
            index = 1
            for i in range(length):
                ch = command[length-1-i]
                drawAt(graphBoard, graphs[ord(ch) - ord('a')], index)
                index += weightChar + 1
                if i % 4 == 3:
                    printBoard(graphBoard)
                    cleanBoard(graphBoard)
                    index = 1
            if i % 4 != 3:
                printBoard(graphBoard)


## The outcome of the program:
Let's run the program on python and see what would happen.
First,we input an 'a'


![1](http://7xrn0b.com1.z0.glb.clouddn.com/860c3d8318b9d867a58e3c8c39db5ab1)

Turned out it print an a in form of #.
Next we input 'abc'

![2](http://7xrn0b.com1.z0.glb.clouddn.com/79c74070988f9933efeccd7e4e0ee30a)

Turned out it print abc in opposite order cba.

And we input enough letters to full the line of the screen,so we input aabbcca

![3](http://7xrn0b.com1.z0.glb.clouddn.com/aa11c2368d25bbb49938611f1af2a70e)

We can see the automatic line feed worked.
## Conclusion:
We have accomplish fashback outputting and automatic line feeding using the python program above.
## Acknowledgment:
The program above is edicted by Yizhe Dong of Shanghai Jiaotong University.
And I don't understand it in some way.
Thank him for his working.
