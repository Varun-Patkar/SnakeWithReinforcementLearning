# Snake Game with Reinforcement Learning

The snake game is a basic game in pygame. It startes with a random direction adn aligns a snake of length 3 in that direction. Then it starts the game with all the basic rules. 

## Rules

- Touching the walls will result in game over
- Not eating food for too long will result in game over(Encourages eating food to survive)
- Hitting yourself results in a game over

## LinearQNet

I used a LinearQNet in pytorch to train and play the game. At the start there are random moves to promote exploration and after some time it takes all the moves given by the model.

The model gets an 11 0/1 input and it outputs 3 integers to indicate the move.

The 1st layer of the model is of size 11, 2nd is a hidden layer of size 256 and the output layer is of size 3

### Input
The input consists of 11 0/1 integers. They are:
1. danger straight(checks if there is wall or itself in front of the head)
2. danger right(checks if there is wall or itself to the right of the head)
3. danger left(checks if there is wall or itself to the left of the head)
4. Move left(yes/no)
5. Move right(yes/no)
6. Move up(yes/no)
7. Move down(yes/no)
8. food is to the left of the head
9. food is to the right of head
10. food is above the head
11. food is below the head

### Output
The output is of 3 0/1 integers. The combinations are:
1. [1,0,0] - keep going straight
2. [0,1,0] - Make a right turn
3. [0,0,1] - Make a left turn

## Screenshots
