# my-repository
def mainmenu():
    while True:
        print("MAIN MENU".center(50))
        print("WELCOME TO TIC TAC TOE".center(50))
        print("TO PLAY THE GAME ENTER 'play' TO EXIT ENTER 'exit'")
        o= input("Enter your choice: ")
        if o== 'play':
            playgame()
        elif o == 'exit':
            print("GAME ENDED")
            break
        else:
            print("Invalid input! Try again.")
def playgame():
    pl1 = input("Player 1 name ---> ")
    pl2 = input("Player 2 name ---> ")
    print(pl1, "what is your symbol ---> ", end="")
    s1 = input()
    print(pl2, "enter your symbol ---> ", end="")
    s2 = input()
    board = [" ", " ", " ", " ", " ", " ", " ", " ", " ",]
    def printboard():
        print()
        print(" ", board[0], "|", board[1], "|", board[2])
        print("----+---+----")
        print(" ", board[3], "|", board[4], "|", board[5])
        print("----+---+----")
        print(" ", board[6], "|", board[7], "|", board[8])
        print()
    def winner(player):
        win = [[0,1,2],[3,4,5],[6,7,8],
               [0,3,6],[1,4,7],[2,5,8],
               [0,4,8],[2,4,6]]
        for condition in win:
            if board[condition[0]] == board[condition[1]] == board[condition[2]] == player:
                return True
        return False
    def isfull():
        return " " not in board
    currentplayer = s1
    while True:
        printboard()
        if currentplayer == s1:
            playername = pl1
        else:
            playername = pl2
        try:
            pos = int(input(f"{playername} ({currentplayer}) choose position (1-9): ")) - 1
        except ValueError:
            print("Please enter a number!")
            continue
        if pos < 0 or pos > 8:
            print("Invalid position! Choose 1-9.")
            continue
        if board[pos] != " ":
            print("Position already taken!")
            continue
        board[pos] = currentplayer
        if winner(currentplayer):
            printboard()
            print(f"{playername} wins!")
            break
        if isfull():
            printboard()
            print("It's a draw!")
            break
        if currentplayer == s1:
            currentplayer = s2
        else:
            currentplayer = s1
    print("!!! THANKS FOR PLAYING !!!")
    input("Press ENTER to return to main menu...")
mainmenu()  
