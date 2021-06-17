from food import Food
import time
from turtle import Screen
from snake import Snake
from scoreboard import Scoreboard

screen = Screen()

screen.bgcolor("green")
screen.title("My Snake Game")
screen.setup(600, 600)

screen.tracer(0)

snake = Snake()
food = Food()
scoreboard = Scoreboard()

screen.listen()
screen.onkey(snake.up, "Up")
screen.onkey(snake.down, "Down")
screen.onkey(snake.left, "Left")
screen.onkey(snake.right, "Right")

is_game_on = True

while is_game_on:
    screen.update()

    time.sleep(0.1)
    snake.move()

    if snake.segments[0].distance(food) < 15:
        food.refresh()
        snake.extend()
        scoreboard.update_scoreboard()
        scoreboard.increase_score()

    if snake.segments[0].xcor() > 290 or snake.segments[0].xcor() < -290 or snake.segments[0].ycor() > 290 or \
            snake.segments[0].ycor() < -290:
        is_game_on = False
        scoreboard.game_over()

    for segments in snake.segments:
        if segments == snake.segments[0]:
            pass
        elif snake.segments[0].distance(segments) < 10:
            is_game_on = False
            scoreboard.game_over()

screen.exitonclick()
