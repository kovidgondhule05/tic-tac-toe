# GAME OF STONE, PAPER AND SCISSORS 
def mainmenu():<br>
    while True:<br>
        print("MAIN MENU".center(50))<br>
        print("WELCOME TO TIC TAC TOE".center(50))<br>
        print("TO PLAY THE GAME ENTER 'play' TO EXIT ENTER 'exit'")<br>
        o= input("Enter your choice: ")<br>
        if o== 'play':<br>
            playgame()<br>
        elif o == 'exit':<br>
            print("GAME ENDED")<br>
            break<br>
        else:<br>
            print("Invalid input! Try again.")<br>
def playgame():<br>
    pl1 = input("Player 1 name ---> ")<br>
    pl2 = input("Player 2 name ---> ")<br>
    print(pl1, "what is your symbol ---> ", end="")<br>
    s1 = input()<br>
    print(pl2, "enter your symbol ---> ", end="")<br>
    s2 = input()<br>
    board = [" ", " ", " ", " ", " ", " ", " ", " ", " ",]<br>
    def printboard():<br>
        print()<br>
        print(" ", board[0], "|", board[1], "|", board[2])<br>
        print("----+---+----")<br>
        print(" ", board[3], "|", board[4], "|", board[5])<br>
        print("----+---+----")<br>
        print(" ", board[6], "|", board[7], "|", board[8])<br>
        print()<br>
    def winner(player):<br>
        win = [[0,1,2],[3,4,5],[6,7,8],<br>
               [0,3,6],[1,4,7],[2,5,8],<br>
               [0,4,8],[2,4,6]]<br>
        for condition in win:<br>
            if board[condition[0]] == board[condition[1]] == board[condition[2]] == player:<br>
                return True<br>
        return False<br>
    def isfull():<br>
        return " " not in board<br>
    currentplayer = s1<br>
    while True:<br>
        printboard()<br>
        if currentplayer == s1:<br>
            playername = pl1<br>
        else:<br>
            playername = pl2<br>
        try:<br>
            pos = int(input(f"{playername} ({currentplayer}) choose position (1-9): ")) - 1<br>
        except ValueError:<br>
            print("Please enter a number!")<br>
            continue<br>
        if pos < 0 or pos > 8:<br>
            print("Invalid position! Choose 1-9.")<br>
            continue<br>
        if board[pos] != " ":<br>
            print("Position already taken!")<br>
            continue<br>
        board[pos] = currentplayer<br>
        if winner(currentplayer):<br>
            printboard()<br>
            print(f"{playername} wins!")<br>
            break<br>
        if isfull():<br>
            printboard()<br>
            print("It's a draw!")<br>
            break<br>
        if currentplayer == s1:<br>
            currentplayer = s2<br>
        else:<br>
            currentplayer = s1<br>
    print("!!! THANKS FOR PLAYING !!!")<br>
    input("Press ENTER to return to main menu...")<br>
mainmenu()<br>
