# Robot Fleet Manager (C++)

A C++17 command-line application for managing a fleet of robots, built around
object-oriented design: an abstract `Robot` base class with specialised
`MobileRobot`, `CleaningRobot` and `CookingRobot` types, a `Fleet` that owns
them through smart pointers, and a priority-ordered task queue.

From an interactive menu you can add and remove robots, list the fleet, make
one robot or all robots work, charge the fleet, assign tasks, inspect the task
queue, and start timed work on a background thread.

## Features

- Abstract base class `Robot` with polymorphic `work()` and `type()` methods
- Derived robot classes: `MobileRobot`, `CleaningRobot`, `CookingRobot`
- `Fleet` manages robot lifetimes with smart pointers
- Task queue ordered by priority
- Operator overloading for `Robot`, `Task` and `Fleet`
- Exception handling for invalid operations
- Background thread for timed work
- Interactive menu in `main.cpp`

## Project structure

```
include/
├── robot.hpp
├── mobile_robot.hpp
├── cleaning_robot.hpp
├── cooking_robot.hpp
├── task.hpp
└── fleet.hpp
src/
├── robot.cpp
├── mobile_robot.cpp
├── cleaning_robot.cpp
├── cooking_robot.cpp
├── task.cpp
└── fleet.cpp
main.cpp
compile.sh
```

## Build

```bash
./compile.sh
# or directly:
g++ -std=c++17 -Wall -Wextra src/*.cpp main.cpp -I include -o fleet_app
```

## Run

```bash
./fleet_app
```
