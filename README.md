<h1>ExpNo 9: Solve Wumpus World Problem using Python demonstrating Inferences from Propositional Logic</h1> 
<h3>Name:       IYYAPPAN S </h3>
<h3>Register Number: 212225230108 </h3>
<H3>Aim:</H3>
<p>
    To solve  Wumpus World Problem using Python demonstrating Inferences from Propositional Logic
</p>
<h1>Problem Description</h1>
<hr>
<h2>Wumpus World</h2>
<hr>
The Wumpus world is a simple world example to illustrate the worth of a knowledge-based agent and to represent knowledge representation.

The figure below shows a Wumpus world containing one pit and one Wumpus. There is an agent in room [1,1]. The goal of the agent is to exit the Wumpus world alive. The agent can exit the Wumpus world by reaching room [4,4]. The wumpus world contains exactly one Wumpus and one pit. There will be a breeze in the rooms adjacent to the pit, and there will be a stench in the rooms adjacent to Wumpus.

![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/cd6b68dc-c79f-4dcb-8126-04da90d65912)

<center>Wumpus World Representation</center>
<p>
This is a python program that uses propositional logic sentences to check which rooms are safe. 

It is assumed that there will always be a safe path that the agent can take to exit the Wumpus world. The logical agent can take four actions: Up, Down, Left and Right. These actions help the agent move from one room to an adjacent room. The agent can perceive two things: Breeze and Stench.
</p>
<h1>Code: </h1>

<pre>
row = 1
col = 1

wumpus = (3, 2)
pit = (3, 3)
gold = (4, 4)

print("Wumpus World")

while True:
    print("\npress u to move up")
    print("press d to move down")
    print("press l to move left")
    print("press r to move right")
    move = input()

    if move == 'u':
        if row < 4:
            row += 1
        else:
            print("Cannot move outside the world!")
            continue

    elif move == 'd':
        if row > 1:
            row -= 1
        else:
            print("Cannot move outside the world!")
            continue

    elif move == 'l':
        if col > 1:
            col -= 1
        else:
            print("Cannot move outside the world!")
            continue

    elif move == 'r':
        if col < 4:
            col += 1
        else:
            print("Cannot move outside the world!")
            continue

    else:
        print("Invalid input!")
        continue

    current = (row, col)

    if current == wumpus:
        print("current location: WUMPUS")
        print("You were eaten by the Wumpus!")
        break

    elif current == pit:
        print("current location: PIT")
        print("You fell into the pit!")
        break

    elif current == gold:
        print("current location: GOLD")
        print("GOLD FOUND! You won....")
        print("Your score is: 1000")
        break

    elif abs(row - pit[0]) + abs(col - pit[1]) == 1:
        print("current location: Breeze")

    elif abs(row - wumpus[0]) + abs(col - wumpus[1]) == 1:
        print("current location: Stench")

    else:
        print("current location: Safe")
</pre>

<hr>
<h1>Sample Input and Output:</h1>
<hr>

![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/8696111a-a4a7-47cb-ba4b-43a4ef88573f)
![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/4be5bf06-79fa-4fa0-9334-38a33f06060b)

<h1>Input and Output: </h1>
<img width="1761" height="784" alt="exp9_output_VScode" src="https://github.com/user-attachments/assets/56399cac-24b9-49e4-a75a-ce2c40ba1489" />
