## Select Basics
# Used the "world" table from SQL zoo website https://sqlzoo.net/wiki/SELECT_basics

# "Where" clause
( Goal: Show the population of a specific country.
Example: Finding the population of Germany.
)

SELECT population 
FROM world
WHERE name = 'Germany'

# "In" Operator

SELECT name, population FROM world
  WHERE name IN ('Sweden', 'Norway', 'Denmark')

# "Between" operator

SELECT name, area FROM world
  WHERE area BETWEEN 200000 AND 250000

  # Note:
- The WHERE clause allowed us to sshow the population of france and we have to always make sure that that the strings are in single quotes
- The IN operator allows us to check if an item is in the list
- The BETWEEN operator shows range checking
