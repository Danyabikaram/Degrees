
Degrees of Separation Between Actors
# Overview

This project implements a program to compute the shortest connection between two actors based on the movies they have starred in. Inspired by the Six Degrees of Kevin Bacon game, the goal is to find how many “degrees of separation” exist between any two actors in the film industry.

# Problem

Given two actors, the program determines the minimum number of steps connecting them, where each step is a movie in which two actors appeared together. For example, if actor A starred with actor B in a movie, and actor B starred with actor C in another movie, then actor A and actor C are 2 degrees apart

# Dataset

The project uses CSV datasets that include:

1. people.csv – Contains actor information:

id: unique actor ID

name: actor’s full name

birth: year of birth

2. movies.csv – Contains movie information:

id: unique movie ID

title: movie title

year: release year

3. stars.csv – Connects actors and movies:

person_id: actor ID

movie_id: movie ID
This file defines which actors starred in which movies.

Two dataset sizes are provided:

small/ – A subset of data for testing

large/ – Full dataset for real scenarios

# Solution

The program uses Breadth-First Search (BFS) to find the shortest path between two actors:

1. Graph representation:

Nodes: actors

Edges: movies connecting two actors

2. Algorithm steps:

Start from the source actor.

Explore all actors they’ve starred with (neighbors).

Repeat until the target actor is found.

Track the path to reconstruct the movies and intermediate actors

3.Implementation details:

degrees.py – Main program


Functions:

shortest_path(source, target) – Computes the shortest connection

neighbors_for_person(person_id) – Returns actors who starred with a given actor

person_id_for_name(name) – Resolves actor names to IDs

# Results

The program successfully computes degrees of separation between any two actors. For example:

Loading data...
Data loaded.
Name: Jennifer Lawrence
Name: Tom Hanks
2 degrees of separation.
1: Jennifer Lawrence and Felicity Jones starred in Like Crazy
2: Felicity Jones and Tom Hanks starred in Tom Hanks: A League of His Own

Degrees of separation: 2

Shows the chain of actors and the movies connecting them.

#Usage

1.Clone the repository:
git clone https://github.com/yourusername/degrees.git

cd degrees

2.Run the program with a dataset directory (small or large):
python degrees.py small

3.Enter two actor names when prompted.
