# Mongodb_Queries_Practice

insert the following documents into a movies collection.
([
{title : “Fight Club”,
writer : “Chuck Palahniuk”
year : 1999,
actors : [
  “Brad Pitt”,
  “Edward Norton”
]
},
{
title : “Pulp Fiction”,
writer : “Quentin Tarantino”,
year : 1994,
actors : [
  “John Travolta”,
  “Uma Thurman”
]
},
{
title : “Inglorious Basterds”,
writer : “Quentin Tarantino”
year : 2009,
actors : [
  “Brad Pitt”
  “Diane Kruger”
  “Eli Roth”
]
},
{
title : “The Hobbit: An Unexpected Journey”,
writer : “J.R.R. Tolkein”,
year : 2012,
franchise : “The Hobbit”
},
{
title : “The Hobbit: The Desolation of Smaug”,
writer : “J.R.R. Tolkein”,
year : 2013,
franchise : “The Hobbit”
},
{
title : “The Hobbit: The Battle of the Five Armies”,
writer : “J.R.R. Tolkein”,
year : 2012,
franchise : “The Hobbit”
synopsis : “Bilbo and Company are forced to engage in a war against an array of combatants and keep the Lonely Mountain from falling into the hands of a rising
darkness.”}])





	1.	get all documents?
      Ans: db.movies.find()
	2.	get all documents with writer set to "Quentin Tarantino"

     Ans: db.movies.find({writer:"Quentin Tarantino"})
	3.	get all documents where actors include "Brad Pitt"
     Ans: db.movies.find({actors:"Brad Pitt"})
	4.	get all documents with franchise set to "The Hobbit"
     Ans: db.movies.find({franchise:"The Hobbit"})
	5.	get all movies released in the 90s
     Ans: db.movies.find({year:{$gt:1990, $lt:2000}})
	6.	get all movies released before the year 2000 or after 2010?
     Ans: db.movies.find({$or:[{year:{$gt:"2010"}},{year: {$lt:"2000"}}]})
	7.	count the number of writer from the movie collection?
     Ans: db.movie.distinct('writer').length
                                or
              db.movie.distinct('writer')
	8.	update an actor named "Samuel L. Jackson" to the movie "Pulp Fiction"?
     Ans: db.movies.update({title : “Pulp Fiction” )}, {$push:{actors:"Samuel L.  Jackson"}})
	9.	find all movies that have a synopsis that contains the word "Gandalf"?
     Ans: db.movies.find({synopsis:{$regex:"Gandalf"}})
	10.	display the movie collection  based on year in descending order?
      Ans: db.movie.find().sort({year:-1}) 

	11.	Display last two recent movie ?
      Ans:  db.movie.find().sort({year:-1}).limit(2) 


