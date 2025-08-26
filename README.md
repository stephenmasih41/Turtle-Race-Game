# 🐍 Day 19 - Part 2: Turtle Race Game 🏁🐢

Welcome to **Day 19 (Part 2)** of my **Python Bootcamp Journey** 🚀  
In this project, I built a fun **Turtle Racing Game** using Python’s `turtle` module. 🎮  

You can **bet on a turtle’s color**, watch them race, and see if you win! 🎲✨  

---

## 📜 Code Explanation

### 🖥️ Screen Setup
```python
screen = Screen()
screen.setup(width=500,height=400)
```
- Creates a race track (screen) of size **500x400**.
---
### 🎨 Turtle Setup
```python
colors = ["red","orange","yellow","green","blue","purple"]
y_positions = [-70,-40,-10,20,50,80]
all_turtles = []
```
- Six turtles 🐢 with different **colors**.
- Each one is placed at a unique **y-position** so they line up at the starting line.
```python
for turtle_index in range(0,6):
    new_turtle = Turtle(shape="turtle")
    new_turtle.penup()
    new_turtle.color(colors[turtle_index])
    new_turtle.goto(x=-230, y=y_positions[turtle_index])
    all_turtles.append(new_turtle)
```
- A loop creates 6 turtles.
- They start at **x = -230** (left side of the screen).
---
### 🏁 User Bet
```python
user_bet = screen.textinput(title="Make your bet",
    prompt="Which turtle will win the race? Enter a color: ")
```
- A popup lets you **place your bet** by entering a turtle’s color. 🎲
- If you enter a color, the race begins! 🟢
---
### 🏎️ The Race Loop
```python
while is_race_on:
    for turtle in all_turtles:
        if turtle.xcor() > 230:
            is_race_on = False
            winning_color = turtle.pencolor()
```
- The race continues until a turtle crosses the **finish line (x=230)**.
---
### 🏆 Declaring the Winner
```python
if winning_color == user_bet:
    print(f"You've won! The {winning_color} turtle is the winner!")
else:
    print(f"You've lost! The {winning_color} turtle is the winner!")
```
- If your bet matches the winner’s color → 🎉 **You win!**
- Otherwise → 😢 **You lose!**
---
### 🎲 Random Movement
```python
rand_distance = random.randint(0,10)
turtle.forward(rand_distance)
```
- Each turtle moves forward by a **random distance (0–10)**.
- This makes the race exciting and unpredictable! 🔮
---
### 🖱️ Exit
```python
screen.exitonclick()
```
- Closes the game when you click on the screen ❌🖱️
---
## 🎯 What I Learned
- How to create **multiple turtle objects** in a loop. 🐢
- How to use `textinput()` to get user input.
- How to simulate a **randomized race** with `random.randint()`. 🎲
- Event-driven programming with the **turtle screen**.
---