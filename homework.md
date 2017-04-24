# SQL Homework

The Dominion Cinema are having a Marvel Movie Marathon! They have asked you to help maintain their database of movies with times and attendees.

## To access the database:

First, create a database called 'marvel'
```
# terminal
createdb marvel
```

Next, run the provided SQL script to populate your database:
```
# terminal
psql -d marvel -f marvel.sql
```

Use the supplied data as the source of data to answer the questions.  Copy the SQL command you have used to get the answer, and paste it below the question, along with the result they gave.

## Questions

1. Return ALL the data in the 'movies' table.

  SELECT * FROM movies;

2. Return ONLY the name column from the 'people' table

  SELECT name FROM people;

3.Oops! Someone at CodeClan spelled Johnny's name wrong! Change it to reflect the proper spelling (change 'Jnny Watson' to 'Johnny Watson').

 UPDATE people SET name = 'Johnny Watson' WHERE name = 'Jnny Watson';
 SELECT name FROM PEOPLE; 

4. Return ONLY your name from the 'people' table.

  SELECT name FROM people WHERE name = 'Alex Berry'

5. The cinema is showing 'Batman Begins', but Batman is DC, not Marvel! Delete the entry from the 'movies' table.

  DELETE FROM movies WHERE title = 'Batman Begins';
  SELECT * FROM movies;

6. Create a new entry in the 'people' table with the name of one of the instructors.

 INSERT INTO people (name) VALUES 'Matthew';

7. Craig Morton, has decided to hijack our movie evening, Remove him from the table of people.

  DELETE FROM people WHERE name = 'Craig Morton';

8. Somehow the list of people includes two people named 'Simon'. Change these entries to the proper names ('Jack Jarvis' and 'Victor McDade')

  UPDATE people SET name = 'Jack Jarvis' WHERE id = 8;
  UPDATE people SET name = 'Victor McDade' WHERE id = 9;

9. The cinema has just heard that they will be holding an exclusive midnight showing of 'Guardians of the Galaxy 2'!! Create a new entry in the 'movies' table to reflect this.

  INSERT INTO movies (title, year, show_time) VALUES ('Guardians of the Galaxy 2', 2017, '00:00');

10. The cinema would also like to make the Guardian movies a back to back feature. Update the 'Guardians of the Galaxy' show time from 12:10 to 21:30

  UPDATE movies SET show_time = '21:30' WHERE title = 'Guardians of the Galaxy'

## Extension

1. Research how to delete multiple entries from your table in a single command.

If you need to delete based on a list, you can use IN:

delete from your_table
where id in (value1, value2, ...);
If you need to delete based on the result of a query, you can also use IN:

delete from your_table
where id in (select aColumn from ...);
(Notice that the subquery must return only one column)

If you need to delete based on a range of values, either you use BETWEEN or you use inequalities:

delete from your_table
where id between bottom_value and top_value;
or

delete from your_table
where id >= a_value and id <= another_value;
