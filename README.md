# User-Based-Collaborative-Filtering-Recommender-system
Implements a simple user-based collaborative filtering recommender system for predicting the ratings of an item using the data given. The prediction would be done using k nearest neighbors and Pearson Correlation.  Finally using the similarity of the k nearest neighbors, predict the ratings of the new item for the given user


Format of ratings file
-------------------------
 The input file consists of one rating event per line. Each rating event is of the form:
user_id\trating\tmovie_title
 The user_id is a string that contains only alphanumeric characters and hyphens and spaces (no tabs).
 The rating is one of the float values 0.5, 1.0, 1.5, 2.0, 2.5, 3.0, 3.5, 4.0, 4.5, and 5.0.
 The movie_title is a string that may contain space characters (to separate the words).
 The three fields -- user_id, rating, and the movie_title -- are separated by a single tab character (\t).


Input
------
python Subramanya_Suhas_collabFilter.py ratings-dataset.tsv Kluver ‘The Fugitive’ 10

ratings-dataset.tsv: input file
Kluver: User id
Movie: The Fugitive
K: 10


The program will output:
-------------------------
 K nearest neighbors with their user ids and similarity values separated by space as per the output
file
 Rating prediction for item.



Sample Ratings File - ratings-dataset.tsv
-----------------------------------------

Kluver	3.5	Pirates of the Caribbean: The Curse of the Black Pearl
Kluver	4.0	Finding Nemo
Kluver	4.5	The Dark Knight
Kluver	4.5	Batman Begins
Kluver	4.0	The Incredibles
Kluver	3.5	Men in Black
Kluver	4.0	Minority Report
Kluver	4.0	The Lord of the Rings: The Return of the King
Kluver	4.0	Back to the Future
Kluver	4.0	The Lord of the Rings: The Two Towers
Kluver	2.5	Star Wars: Episode II - Attack of the Clones
Kluver	4.5	Aladdin
Kluver	3.0	Batman
Kluver	4.0	Crouching Tiger, Hidden Dragon
Kluver	4.5	Monsters, Inc.
Kluver	4.0	Shrek
Kluver	3.0	The Mask
Kluver	3.5	The Matrix Reloaded
Kluver	4.0	Ocean's Eleven
Kluver	4.0	Star Wars: Episode IV - A New Hope
Kluver	4.0	Star Wars: Episode V - The Empire Strikes Back
Kluver	4.0	Memento
Kluver	4.5	The Matrix
Kluver	4.0	Star Wars: Episode VI - Return of the Jedi
Kluver	4.0	Catch Me If You Can
Kluver	4.0	The Sixth Sense
Kluver	4.0	Toy Story
Kluver	4.0	Raiders of the Lost Ark
hi mom	3.5	Meet the Parents
hi mom	2.5	The Mask
hi mom	4.5	Se7en
hi mom	4.5	The Matrix
hi mom	3.0	The Lion King
hi mom	4.0	Raiders of the Lost Ark
hi mom	3.0	Catch Me If You Can
hi mom	4.0	Charlie's Angels
hi mom	4.5	Die Hard: With a Vengeance
hi mom	1.5	Dumb and Dumber
k279	4.0	Beauty and the Beast
k279	5.0	The Dark Knight
k279	5.0	The Lord of the Rings: The Return of the King
k279	5.0	Forrest Gump
k279	4.0	Clear and Present Danger
k279	3.5	Jurassic Park
k279	4.0	Star Wars: Episode VI - Return of the Jedi
8ccfa5d6-6f0b-407f-a463-0e1f745f9dad	4.0	Shrek
8ccfa5d6-6f0b-407f-a463-0e1f745f9dad	3.0	The Fugitive
k279	3.5	The Shawshank Redemption
k279	3.0	The Bourne Identity
k279	4.5	Shrek 2
8ccfa5d6-6f0b-407f-a463-0e1f745f9dad	3.0	The Incredibles
k279	3.0	Star Wars: Episode IV - A New Hope
k279	2.5	Mrs. Doubtfire
k279	3.0	Stargate
8ccfa5d6-6f0b-407f-a463-0e1f745f9dad	3.5	Finding Nemo
8ccfa5d6-6f0b-407f-a463-0e1f745f9dad	4.0	Back to the Future
k279	1.0	Dances with Wolves
8ccfa5d6-6f0b-407f-a463-0e1f745f9dad	3.0	Harry Potter and the Chamber of Secrets
k279	3.0	The Lion King
8ccfa5d6-6f0b-407f-a463-0e1f745f9dad	4.5	Saving Private Ryan
k279	5.0	Harry Potter and the Chamber of Secrets
8ccfa5d6-6f0b-407f-a463-0e1f745f9dad	3.5	The Matrix
8ccfa5d6-6f0b-407f-a463-0e1f745f9dad	4.0	Fight Club
k279	3.0	Spider-Man
8ccfa5d6-6f0b-407f-a463-0e1f745f9dad	4.5	The Lord of the Rings: The Fellowship of the Ring
k279	3.0	Spider-Man 2
k279	4.5	Star Wars: Episode V - The Empire Strikes Back
k279	3.5	Finding Nemo
k279	5.0	Men in Black
k279	5.0	The Lord of the Rings: The Fellowship of the Ring
k279	3.5	Twister
k279	3.5	Gladiator
k279	5.0	Pirates of the Caribbean: The Curse of the Black Pearl
k279	3.0	Crouching Tiger, Hidden Dragon
k279	4.0	The Matrix Reloaded
k279	1.5	Fight Club
k279	4.5	Braveheart
k279	2.5	Chicken Run
k279	4.5	Star Wars: Episode II - Attack of the Clones
k279	2.5	E.T. the Extra-Terrestrial
k279	4.0	Raiders of the Lost Ark
k279	4.5	O Brother, Where Art Thou?
k279	5.0	The Matrix
k279	5.0	Shrek
k279	3.0	Titanic
k279	4.5	The Lord of the Rings: The Two Towers
k279	3.0	Cast Away
k279	5.0	Back to the Future
8ccfa5d6-6f0b-407f-a463-0e1f745f9dad	2.0	Shrek 2
8ccfa5d6-6f0b-407f-a463-0e1f745f9dad	5.0	Star Wars: Episode IV - A New Hope
8ccfa5d6-6f0b-407f-a463-0e1f745f9dad	3.5	The Patriot
8ccfa5d6-6f0b-407f-a463-0e1f745f9dad	3.0	The Lion King
8ccfa5d6-6f0b-407f-a463-0e1f745f9dad	5.0	Pulp Fiction
8ccfa5d6-6f0b-407f-a463-0e1f745f9dad	4.0	X-Men
8ccfa5d6-6f0b-407f-a463-0e1f745f9dad	3.0	Chicken Run
8ccfa5d6-6f0b-407f-a463-0e1f745f9dad	4.0	Toy Story
8ccfa5d6-6f0b-407f-a463-0e1f745f9dad	5.0	The Dark Knight
8ccfa5d6-6f0b-407f-a463-0e1f745f9dad	4.5	Forrest Gump
8ccfa5d6-6f0b-407f-a463-0e1f745f9dad	4.5	The Bourne Identity
8ccfa5d6-6f0b-407f-a463-0e1f745f9dad	4.0	The Bourne Supremacy
8ccfa5d6-6f0b-407f-a463-0e1f745f9dad	4.5	Star Wars: Episode V - The Empire Strikes Back
04bf3522-4cac-4579-999a-bdffd4c7d22f	5.0	The Lord of the Rings: The Fellowship of the Ring
04bf3522-4cac-4579-999a-bdffd4c7d22f	2.0	Star Wars: Episode II - Attack of the Clones
8ccfa5d6-6f0b-407f-a463-0e1f745f9dad	1.5	Star Wars: Episode II - Attack of the Clones
04bf3522-4cac-4579-999a-bdffd4c7d22f	5.0	The Lord of the Rings: The Two Towers
8ccfa5d6-6f0b-407f-a463-0e1f745f9dad	4.5	Star Wars: Episode VI - Return of the Jedi
8ccfa5d6-6f0b-407f-a463-0e1f745f9dad	5.0	AmAlie
04bf3522-4cac-4579-999a-bdffd4c7d22f	3.5	Shrek
8ccfa5d6-6f0b-407f-a463-0e1f745f9dad	2.5	Ace Ventura: Pet Detective
04bf3522-4cac-4579-999a-bdffd4c7d22f	4.0	Toy Story
04bf3522-4cac-4579-999a-bdffd4c7d22f	3.0	Titanic
04bf3522-4cac-4579-999a-bdffd4c7d22f	4.0	Dumb and Dumber
04bf3522-4cac-4579-999a-bdffd4c7d22f	5.0	Schindler's List
04bf3522-4cac-4579-999a-bdffd4c7d22f	4.0	Catch Me If You Can
04bf3522-4cac-4579-999a-bdffd4c7d22f	5.0	Pulp Fiction
8ccfa5d6-6f0b-407f-a463-0e1f745f9dad	5.0	The Lord of the Rings: The Two Towers
8ccfa5d6-6f0b-407f-a463-0e1f745f9dad	5.0	Donnie Darko
04bf3522-4cac-4579-999a-bdffd4c7d22f	3.0	Mission: Impossible
04bf3522-4cac-4579-999a-bdffd4c7d22f	4.0	Aladdin
04bf3522-4cac-4579-999a-bdffd4c7d22f	4.5	Star Wars: Episode VI - Return of the Jedi
04bf3522-4cac-4579-999a-bdffd4c7d22f	3.0	Monsters, Inc.
04bf3522-4cac-4579-999a-bdffd4c7d22f	4.5	The Lion King
04bf3522-4cac-4579-999a-bdffd4c7d22f	4.5	The Dark Knight
04bf3522-4cac-4579-999a-bdffd4c7d22f	4.0	Star Wars: Episode V - The Empire Strikes Back
04bf3522-4cac-4579-999a-bdffd4c7d22f	4.0	Pirates of the Caribbean: The Curse of the Black Pearl
8ccfa5d6-6f0b-407f-a463-0e1f745f9dad	3.5	The Mask
04bf3522-4cac-4579-999a-bdffd4c7d22f	4.0	Crouching Tiger, Hidden Dragon
04bf3522-4cac-4579-999a-bdffd4c7d22f	5.0	The Lord of the Rings: The Return of the King
8ccfa5d6-6f0b-407f-a463-0e1f745f9dad	4.5	The Lord of the Rings: The Return of the King
04bf3522-4cac-4579-999a-bdffd4c7d22f	3.5	Harry Potter and the Chamber of Secrets
04bf3522-4cac-4579-999a-bdffd4c7d22f	1.0	Chicken Run
04bf3522-4cac-4579-999a-bdffd4c7d22f	2.5	Meet the Parents
04bf3522-4cac-4579-999a-bdffd4c7d22f	3.5	Forrest Gump
04bf3522-4cac-4579-999a-bdffd4c7d22f	4.0	Finding Nemo
04bf3522-4cac-4579-999a-bdffd4c7d22f	3.0	Harry Potter and the Philosopher's Stone
04bf3522-4cac-4579-999a-bdffd4c7d22f	3.0	Apollo 13
04bf3522-4cac-4579-999a-bdffd4c7d22f	1.5	Shrek 2
04bf3522-4cac-4579-999a-bdffd4c7d22f	2.0	Spider-Man
04bf3522-4cac-4579-999a-bdffd4c7d22f	5.0	The Shawshank Redemption
04bf3522-4cac-4579-999a-bdffd4c7d22f	3.5	Se7en
04bf3522-4cac-4579-999a-bdffd4c7d22f	4.0	Star Wars: Episode IV - A New Hope
04bf3522-4cac-4579-999a-bdffd4c7d22f	4.5	Gladiator
b12051fa-28e8-4e29-91b0-8cc2aed96d8c	4.5	The Bourne Identity
04bf3522-4cac-4579-999a-bdffd4c7d22f	3.0	Batman Begins
b12051fa-28e8-4e29-91b0-8cc2aed96d8c	5.0	The Dark Knight
b12051fa-28e8-4e29-91b0-8cc2aed96d8c	4.0	Toy Story
What makes you think I'm not?	4.0	Harry Potter and the Philosopher's Stone
What makes you think I'm not?	3.5	Shrek
04bf3522-4cac-4579-999a-bdffd4c7d22f	4.0	The Silence of the Lambs
What makes you think I'm not?	3.0	Star Wars: Episode II - Attack of the Clones
04bf3522-4cac-4579-999a-bdffd4c7d22f	3.0	The Incredibles
What makes you think I'm not?	4.0	E.T. the Extra-Terrestrial
What makes you think I'm not?	4.0	Spider-Man 2
What makes you think I'm not?	4.0	Crouching Tiger, Hidden Dragon
What makes you think I'm not?	4.0	The Lord of the Rings: The Return of the King
b12051fa-28e8-4e29-91b0-8cc2aed96d8c	4.5	The Shawshank Redemption
b12051fa-28e8-4e29-91b0-8cc2aed96d8c	4.0	Mission: Impossible
b12051fa-28e8-4e29-91b0-8cc2aed96d8c	3.5	Dances with Wolves
b12051fa-28e8-4e29-91b0-8cc2aed96d8c	4.0	Mission: Impossible II
What makes you think I'm not?	4.5	Star Wars: Episode V - The Empire Strikes Back
b12051fa-28e8-4e29-91b0-8cc2aed96d8c	2.5	Chicken Run
b12051fa-28e8-4e29-91b0-8cc2aed96d8c	3.5	Finding Nemo
b12051fa-28e8-4e29-91b0-8cc2aed96d8c	4.0	The Bourne Supremacy
What makes you think I'm not?	4.5	Star Wars: Episode IV - A New Hope
What makes you think I'm not?	4.0	Beauty and the Beast
What makes you think I'm not?	3.0	Shrek 2
b12051fa-28e8-4e29-91b0-8cc2aed96d8c	3.0	Shrek
What makes you think I'm not?	4.5	Toy Story
b12051fa-28e8-4e29-91b0-8cc2aed96d8c	5.0	Minority Report
b12051fa-28e8-4e29-91b0-8cc2aed96d8c	4.5	Men in Black
b12051fa-28e8-4e29-91b0-8cc2aed96d8c	4.0	Batman Begins
b12051fa-28e8-4e29-91b0-8cc2aed96d8c	4.0	Mrs. Doubtfire
b12051fa-28e8-4e29-91b0-8cc2aed96d8c	3.5	The Incredibles
b12051fa-28e8-4e29-91b0-8cc2aed96d8c	4.0	Cast Away
b12051fa-28e8-4e29-91b0-8cc2aed96d8c	4.0	Ocean's Eleven
b12051fa-28e8-4e29-91b0-8cc2aed96d8c	3.5	Monsters, Inc.
b12051fa-28e8-4e29-91b0-8cc2aed96d8c	4.5	Apollo 13
04bf3522-4cac-4579-999a-bdffd4c7d22f	2.5	Fight Club
What makes you think I'm not?	4.0	The Lord of the Rings: The Fellowship of the Ring
04bf3522-4cac-4579-999a-bdffd4c7d22f	2.5	Ocean's Eleven
b12051fa-28e8-4e29-91b0-8cc2aed96d8c	4.5	Star Wars: Episode IV - A New Hope
04bf3522-4cac-4579-999a-bdffd4c7d22f	4.0	V for Vendetta
04bf3522-4cac-4579-999a-bdffd4c7d22f	3.0	Ace Ventura: Pet Detective
b12051fa-28e8-4e29-91b0-8cc2aed96d8c	3.5	Catch Me If You Can
What makes you think I'm not?	4.5	Monsters, Inc.
04bf3522-4cac-4579-999a-bdffd4c7d22f	3.0	Beauty and the Beast
b12051fa-28e8-4e29-91b0-8cc2aed96d8c	4.0	Batman
04bf3522-4cac-4579-999a-bdffd4c7d22f	3.5	Saving Private Ryan
What makes you think I'm not?	4.0	Spider-Man
What makes you think I'm not?	4.5	The Incredibles
b12051fa-28e8-4e29-91b0-8cc2aed96d8c	4.5	Gladiator
04bf3522-4cac-4579-999a-bdffd4c7d22f	4.0	Cast Away
b12051fa-28e8-4e29-91b0-8cc2aed96d8c	3.5	Shrek 2
What makes you think I'm not?	4.5	Pirates of the Caribbean: The Curse of the Black Pearl
b12051fa-28e8-4e29-91b0-8cc2aed96d8c	4.5	Raiders of the Lost Ark
b12051fa-28e8-4e29-91b0-8cc2aed96d8c	4.0	Batman Forever
04bf3522-4cac-4579-999a-bdffd4c7d22f	2.0	Spider-Man 2
What makes you think I'm not?	4.0	The Lord of the Rings: The Two Towers
04bf3522-4cac-4579-999a-bdffd4c7d22f	3.5	Raiders of the Lost Ark
b12051fa-28e8-4e29-91b0-8cc2aed96d8c	4.0	Harry Potter and the Chamber of Secrets
What makes you think I'm not?	4.5	Back to the Future
What makes you think I'm not?	4.5	The Matrix
b12051fa-28e8-4e29-91b0-8cc2aed96d8c	4.5	The Lion King
b12051fa-28e8-4e29-91b0-8cc2aed96d8c	4.5	Star Wars: Episode II - Attack of the Clones
What makes you think I'm not?	4.5	Raiders of the Lost Ark
b12051fa-28e8-4e29-91b0-8cc2aed96d8c	4.5	Meet the Parents
What makes you think I'm not?	4.0	Aladdin
b12051fa-28e8-4e29-91b0-8cc2aed96d8c	4.5	The Matrix
What makes you think I'm not?	4.5	The Lion King
b12051fa-28e8-4e29-91b0-8cc2aed96d8c	4.0	X-Men
What makes you think I'm not?	4.5	Jurassic Park
What makes you think I'm not?	4.5	Finding Nemo
b12051fa-28e8-4e29-91b0-8cc2aed96d8c	4.0	X2: X-Men United
What makes you think I'm not?	4.5	Kill Bill: Vol. 1
What makes you think I'm not?	4.0	Harry Potter and the Chamber of Secrets
What makes you think I'm not?	4.5	Star Wars: Episode VI - Return of the Jedi
What makes you think I'm not?	4.0	Batman
Connor M	4.5	The Bourne Identity
Connor M	3.5	Pirates of the Caribbean: The Curse of the Black Pearl
Connor M	4.0	Forrest Gump
Connor M	2.0	Star Wars: Episode II - Attack of the Clones
Connor M	4.0	Star Wars: Episode VI - Return of the Jedi
Connor M	4.0	Mission: Impossible
Connor M	4.5	The Lord of the Rings: The Fellowship of the Ring
Connor M	3.5	Die Hard: With a Vengeance
Connor M	5.0	The Dark Knight
Connor M	3.0	The Matrix Reloaded
Connor M	3.5	Mrs. Doubtfire
Connor M	4.0	Jurassic Park
Connor M	3.5	Shrek 2
Connor M	5.0	Raiders of the Lost Ark
Connor M	4.5	The Lord of the Rings: The Return of the King
Connor M	3.5	Mission: Impossible II
Connor M	4.0	The Lord of the Rings: The Two Towers
Connor M	3.5	X2: X-Men United
Connor M	4.5	Fargo
Connor M	5.0	Pulp Fiction
Connor M	4.5	Cast Away
Connor M	4.5	Catch Me If You Can
Connor M	4.0	Spider-Man 2
Connor M	4.5	The Bourne Supremacy
Connor M	5.0	Twelve Monkeys
Connor M	4.0	Shrek
Connor M	3.5	Aladdin
Connor M	4.5	Monsters, Inc.
Connor M	3.0	X-Men
Connor M	3.0	Spider-Man
Connor M	4.5	The Lion King
Connor M	2.5	Titanic
Connor M	4.0	Back to the Future
Connor M	5.0	Star Wars: Episode V - The Empire Strikes Back
Connor M	4.0	True Lies
Connor M	3.0	Harry Potter and the Chamber of Secrets
Connor M	4.0	Batman Begins
Connor M	4.0	E.T. the Extra-Terrestrial
Connor M	4.5	Star Wars: Episode IV - A New Hope
Connor M	5.0	Terminator 2: Judgment Day
Connor M	4.0	Men in Black
Connor M	4.0	The Incredibles
Connor M	3.0	Harry Potter and the Philosopher's Stone
Connor M	4.0	Apollo 13
Connor M	4.5	Finding Nemo
Connor M	4.5	Unbreakable
Connor M	4.0	Independence Day
Connor M	5.0	Toy Story
Connor M	4.0	Beauty and the Beast
duder21	3.5	Harry Potter and the Philosopher's Stone
duder21	3.5	X2: X-Men United
duder21	3.5	The Lion King
duder21	4.5	Twelve Monkeys
duder21	4.0	Batman Begins
duder21	4.5	O Brother, Where Art Thou?
duder21	4.0	The Dark Knight
duder21	4.0	Apollo 13
duder21	4.5	The Shawshank Redemption
duder21	3.0	Shrek 2
duder21	3.5	Finding Nemo
duder21	4.0	Aladdin
duder21	2.5	Lost in Translation
duder21	4.5	The Incredibles
duder21	3.0	Spider-Man
duder21	3.5	X-Men
duder21	5.0	Fight Club
duder21	4.0	Donnie Darko
duder21	3.5	Ocean's Eleven
duder21	2.5	Spider-Man 2
duder21	4.0	Toy Story
duder21	4.0	Men in Black
duder21	4.5	Snatch
duder21	5.0	The Departed
duder21	3.0	Requiem for a Dream
duder21	4.5	Forrest Gump
duder21	4.5	The Matrix
duder21	3.5	Shrek
duder21	5.0	Memento
duder21	3.0	Meet the Parents
duder21	4.0	Pulp Fiction
duder21	4.5	Titanic
duder21	4.0	Harry Potter and the Chamber of Secrets
duder21	4.0	Eternal Sunshine of the Spotless Mind
duder21	5.0	Catch Me If You Can
duder21	5.0	The Usual Suspects
duder21	4.0	V for Vendetta
duder21	4.5	Monsters, Inc.
duder21	2.5	Chicken Run
Molly73	2.0	The Usual Suspects
Molly73	2.5	The Matrix
Molly73	2.0	The Rock
Molly73	5.0	Braveheart
Molly73	5.0	E.T. the Extra-Terrestrial
Molly73	4.0	The Departed
Molly73	3.0	X2: X-Men United
Molly73	3.5	The Godfather
Molly73	4.5	Finding Nemo
Molly73	4.0	Apollo 13
Molly73	3.0	Raiders of the Lost Ark
Molly73	5.0	Beauty and the Beast
Molly73	3.5	Aladdin
Molly73	4.0	Toy Story
Molly73	3.5	Pulp Fiction
Molly73	5.0	The Lion King
Molly73	2.5	Back to the Future
Molly73	4.0	Forrest Gump
Molly73	4.0	Star Wars: Episode V - The Empire Strikes Back
Molly73	2.5	Mission: Impossible II
Molly73	4.0	Ocean's Eleven
Molly73	4.0	Titanic
Molly73	2.5	Spider-Man 2
Molly73	2.0	The Bourne Supremacy
Molly73	5.0	The Lord of the Rings: The Two Towers
Molly73	3.5	Harry Potter and the Philosopher's Stone
Molly73	5.0	The Dark Knight
Molly73	5.0	The Lord of the Rings: The Return of the King
Molly73	5.0	The Lord of the Rings: The Fellowship of the Ring
Molly73	3.5	Mrs. Doubtfire
Molly73	3.0	Pirates of the Caribbean: The Curse of the Black Pearl
Molly73	3.5	Cast Away
Molly73	3.5	Jurassic Park
Molly73	3.0	Mission: Impossible
Molly73	2.0	Catch Me If You Can
Molly73	1.5	Stargate
Molly73	2.0	The Bourne Identity
Molly73	3.0	Harry Potter and the Chamber of Secrets
Molly73	3.0	Chicken Run
Molly73	2.5	Spider-Man
Molly73	5.0	Saving Private Ryan
Molly73	5.0	Gladiator
Molly73	5.0	A Beautiful Mind
Molly73	3.5	O Brother, Where Art Thou?
Molly73	4.0	Star Wars: Episode VI - Return of the Jedi
Molly73	4.5	Monsters, Inc.
Molly73	3.0	Batman Begins
Molly73	3.0	Independence Day
Molly73	2.5	X-Men
Molly73	3.5	Shrek
Molly73	4.0	Star Wars: Episode IV - A New Hope
Molly73	4.0	Star Wars: Episode II - Attack of the Clones
Molly73	3.0	Shrek 2
Molly73	3.0	Men in Black
Molly73	4.5	The Incredibles
Molly73	2.5	Dumb and Dumber
baca3a93-43e1-4171-b12f-50e32cd7e96b	3.5	Independence Day
baca3a93-43e1-4171-b12f-50e32cd7e96b	3.0	Titanic
baca3a93-43e1-4171-b12f-50e32cd7e96b	4.0	Star Wars: Episode V - The Empire Strikes Back
baca3a93-43e1-4171-b12f-50e32cd7e96b	4.0	Crouching Tiger, Hidden Dragon
baca3a93-43e1-4171-b12f-50e32cd7e96b	3.5	Shrek 2
baca3a93-43e1-4171-b12f-50e32cd7e96b	4.0	Raiders of the Lost Ark
baca3a93-43e1-4171-b12f-50e32cd7e96b	3.5	The Lord of the Rings: The Fellowship of the Ring
baca3a93-43e1-4171-b12f-50e32cd7e96b	3.0	Meet the Parents
baca3a93-43e1-4171-b12f-50e32cd7e96b	3.0	Men in Black
baca3a93-43e1-4171-b12f-50e32cd7e96b	3.0	Harry Potter and the Chamber of Secrets
baca3a93-43e1-4171-b12f-50e32cd7e96b	3.0	Spider-Man
baca3a93-43e1-4171-b12f-50e32cd7e96b	4.0	Star Wars: Episode IV - A New Hope
baca3a93-43e1-4171-b12f-50e32cd7e96b	4.0	Star Wars: Episode VI - Return of the Jedi
baca3a93-43e1-4171-b12f-50e32cd7e96b	5.0	Forrest Gump
baca3a93-43e1-4171-b12f-50e32cd7e96b	3.5	The Incredibles
baca3a93-43e1-4171-b12f-50e32cd7e96b	3.5	The Dark Knight
baca3a93-43e1-4171-b12f-50e32cd7e96b	3.5	Shrek
baca3a93-43e1-4171-b12f-50e32cd7e96b	3.0	Chicken Run
baca3a93-43e1-4171-b12f-50e32cd7e96b	4.0	Finding Nemo
baca3a93-43e1-4171-b12f-50e32cd7e96b	3.0	Cast Away
baca3a93-43e1-4171-b12f-50e32cd7e96b	3.0	Apollo 13
baca3a93-43e1-4171-b12f-50e32cd7e96b	4.5	Saving Private Ryan
baca3a93-43e1-4171-b12f-50e32cd7e96b	2.5	Star Wars: Episode II - Attack of the Clones
baca3a93-43e1-4171-b12f-50e32cd7e96b	3.0	Toy Story
baca3a93-43e1-4171-b12f-50e32cd7e96b	3.0	Jurassic Park
baca3a93-43e1-4171-b12f-50e32cd7e96b	3.0	The Lion King
baca3a93-43e1-4171-b12f-50e32cd7e96b	3.5	A Beautiful Mind
baca3a93-43e1-4171-b12f-50e32cd7e96b	4.0	The Lord of the Rings: The Two Towers
baca3a93-43e1-4171-b12f-50e32cd7e96b	3.5	The Lord of the Rings: The Return of the King
baca3a93-43e1-4171-b12f-50e32cd7e96b	3.0	X-Men
baca3a93-43e1-4171-b12f-50e32cd7e96b	3.0	Pirates of the Caribbean: The Curse of the Black Pearl
baca3a93-43e1-4171-b12f-50e32cd7e96b	2.5	Beauty and the Beast
baca3a93-43e1-4171-b12f-50e32cd7e96b	2.5	Aladdin
baca3a93-43e1-4171-b12f-50e32cd7e96b	2.5	Harry Potter and the Philosopher's Stone
baca3a93-43e1-4171-b12f-50e32cd7e96b	2.0	Gladiator
baca3a93-43e1-4171-b12f-50e32cd7e96b	3.0	Monsters, Inc.
51b10128-ab19-4f0a-a408-32d5041b88fa	3.5	Batman Begins
51b10128-ab19-4f0a-a408-32d5041b88fa	4.0	Finding Nemo
51b10128-ab19-4f0a-a408-32d5041b88fa	3.5	Shrek
51b10128-ab19-4f0a-a408-32d5041b88fa	3.5	Spider-Man
51b10128-ab19-4f0a-a408-32d5041b88fa	4.0	Ace Ventura: Pet Detective
51b10128-ab19-4f0a-a408-32d5041b88fa	3.0	Die Hard: With a Vengeance
51b10128-ab19-4f0a-a408-32d5041b88fa	3.0	Back to the Future
51b10128-ab19-4f0a-a408-32d5041b88fa	3.5	Beauty and the Beast
51b10128-ab19-4f0a-a408-32d5041b88fa	5.0	Raiders of the Lost Ark
51b10128-ab19-4f0a-a408-32d5041b88fa	5.0	Saving Private Ryan
51b10128-ab19-4f0a-a408-32d5041b88fa	4.0	Harry Potter and the Philosopher's Stone
51b10128-ab19-4f0a-a408-32d5041b88fa	4.0	Minority Report
51b10128-ab19-4f0a-a408-32d5041b88fa	4.0	The Bourne Supremacy
51b10128-ab19-4f0a-a408-32d5041b88fa	5.0	Memento
51b10128-ab19-4f0a-a408-32d5041b88fa	5.0	Toy Story
51b10128-ab19-4f0a-a408-32d5041b88fa	3.0	V for Vendetta
51b10128-ab19-4f0a-a408-32d5041b88fa	4.0	Fargo
51b10128-ab19-4f0a-a408-32d5041b88fa	4.0	The Matrix
51b10128-ab19-4f0a-a408-32d5041b88fa	4.5	Star Wars: Episode V - The Empire Strikes Back
51b10128-ab19-4f0a-a408-32d5041b88fa	2.5	Dances with Wolves
51b10128-ab19-4f0a-a408-32d5041b88fa	3.5	Cast Away
51b10128-ab19-4f0a-a408-32d5041b88fa	4.5	Star Wars: Episode VI - Return of the Jedi
51b10128-ab19-4f0a-a408-32d5041b88fa	2.5	Star Wars: Episode II - Attack of the Clones
51b10128-ab19-4f0a-a408-32d5041b88fa	5.0	The Lion King
51b10128-ab19-4f0a-a408-32d5041b88fa	4.5	Pirates of the Caribbean: The Curse of the Black Pearl
51b10128-ab19-4f0a-a408-32d5041b88fa	3.5	The Fugitive
51b10128-ab19-4f0a-a408-32d5041b88fa	3.0	Spider-Man 2
51b10128-ab19-4f0a-a408-32d5041b88fa	4.0	Star Wars: Episode IV - A New Hope
51b10128-ab19-4f0a-a408-32d5041b88fa	4.0	The Bourne Identity
51b10128-ab19-4f0a-a408-32d5041b88fa	4.5	The Lord of the Rings: The Return of the King
51b10128-ab19-4f0a-a408-32d5041b88fa	4.0	Se7en
51b10128-ab19-4f0a-a408-32d5041b88fa	3.5	Clear and Present Danger
51b10128-ab19-4f0a-a408-32d5041b88fa	4.5	The Departed
51b10128-ab19-4f0a-a408-32d5041b88fa	4.0	Harry Potter and the Chamber of Secrets
51b10128-ab19-4f0a-a408-32d5041b88fa	2.5	The Patriot
51b10128-ab19-4f0a-a408-32d5041b88fa	3.0	Chicken Run
51b10128-ab19-4f0a-a408-32d5041b88fa	4.0	The Dark Knight
51b10128-ab19-4f0a-a408-32d5041b88fa	4.0	Ocean's Eleven
51b10128-ab19-4f0a-a408-32d5041b88fa	4.5	The Lord of the Rings: The Two Towers
51b10128-ab19-4f0a-a408-32d5041b88fa	4.5	A Beautiful Mind
51b10128-ab19-4f0a-a408-32d5041b88fa	2.5	Titanic
51b10128-ab19-4f0a-a408-32d5041b88fa	3.0	Forrest Gump
51b10128-ab19-4f0a-a408-32d5041b88fa	3.5	Aladdin
51b10128-ab19-4f0a-a408-32d5041b88fa	3.5	AmAlie
51b10128-ab19-4f0a-a408-32d5041b88fa	4.0	O Brother, Where Art Thou?
51b10128-ab19-4f0a-a408-32d5041b88fa	4.0	Snatch
51b10128-ab19-4f0a-a408-32d5041b88fa	2.5	The Matrix Reloaded
51b10128-ab19-4f0a-a408-32d5041b88fa	3.5	Monsters, Inc.
51b10128-ab19-4f0a-a408-32d5041b88fa	2.0	Shrek 2
51b10128-ab19-4f0a-a408-32d5041b88fa	3.5	Catch Me If You Can
51b10128-ab19-4f0a-a408-32d5041b88fa	5.0	The Lord of the Rings: The Fellowship of the Ring
51b10128-ab19-4f0a-a408-32d5041b88fa	4.0	The Incredibles
Flesh	1.5	Twister
Flesh	4.0	A Beautiful Mind
Flesh	2.0	Mrs. Doubtfire
Flesh	3.0	The Sixth Sense
Flesh	2.0	Shrek 2
Flesh	2.0	Harry Potter and the Philosopher's Stone
Flesh	2.0	Finding Nemo
Flesh	4.0	The Bourne Supremacy
Flesh	5.0	Titanic
Flesh	2.5	Spider-Man
Flesh	2.5	Shrek
Flesh	1.0	Monsters, Inc.
Flesh	3.0	Fight Club
Flesh	0.5	The Incredibles
Flesh	4.0	The Silence of the Lambs
Flesh	3.0	Saving Private Ryan
Flesh	4.0	Beauty and the Beast
Flesh	2.5	Harry Potter and the Chamber of Secrets
Flesh	3.5	The Lion King
Flesh	0.5	The Mask
Flesh	3.0	The Bourne Identity
Flesh	4.0	Aladdin
Flesh	4.0	The Dark Knight
13d30151-838e-44e5-bfab-32abaa1dd99e	4.0	Star Wars: Episode VI - Return of the Jedi
13d30151-838e-44e5-bfab-32abaa1dd99e	3.0	Spider-Man
13d30151-838e-44e5-bfab-32abaa1dd99e	4.0	Star Wars: Episode II - Attack of the Clones
13d30151-838e-44e5-bfab-32abaa1dd99e	5.0	The Matrix
13d30151-838e-44e5-bfab-32abaa1dd99e	3.5	Toy Story
13d30151-838e-44e5-bfab-32abaa1dd99e	4.0	Batman Begins
13d30151-838e-44e5-bfab-32abaa1dd99e	5.0	Memento
13d30151-838e-44e5-bfab-32abaa1dd99e	5.0	The Lord of the Rings: The Fellowship of the Ring
13d30151-838e-44e5-bfab-32abaa1dd99e	3.0	Spider-Man 2
13d30151-838e-44e5-bfab-32abaa1dd99e	5.0	The Lord of the Rings: The Return of the King
13d30151-838e-44e5-bfab-32abaa1dd99e	3.0	Die Hard: With a Vengeance
13d30151-838e-44e5-bfab-32abaa1dd99e	4.5	Ocean's Eleven
13d30151-838e-44e5-bfab-32abaa1dd99e	4.5	The Dark Knight
13d30151-838e-44e5-bfab-32abaa1dd99e	4.0	Star Wars: Episode IV - A New Hope
13d30151-838e-44e5-bfab-32abaa1dd99e	3.0	The Patriot
13d30151-838e-44e5-bfab-32abaa1dd99e	4.0	The Incredibles
13d30151-838e-44e5-bfab-32abaa1dd99e	3.5	Harry Potter and the Philosopher's Stone
13d30151-838e-44e5-bfab-32abaa1dd99e	5.0	Gladiator
13d30151-838e-44e5-bfab-32abaa1dd99e	5.0	Shrek
13d30151-838e-44e5-bfab-32abaa1dd99e	5.0	Shrek 2
13d30151-838e-44e5-bfab-32abaa1dd99e	5.0	The Bourne Identity
13d30151-838e-44e5-bfab-32abaa1dd99e	4.0	Braveheart
13d30151-838e-44e5-bfab-32abaa1dd99e	4.0	Se7en
13d30151-838e-44e5-bfab-32abaa1dd99e	4.0	Dumb and Dumber
13d30151-838e-44e5-bfab-32abaa1dd99e	5.0	Requiem for a Dream
13d30151-838e-44e5-bfab-32abaa1dd99e	4.0	The Matrix Reloaded
13d30151-838e-44e5-bfab-32abaa1dd99e	3.0	Back to the Future
13d30151-838e-44e5-bfab-32abaa1dd99e	4.0	The Bourne Supremacy
13d30151-838e-44e5-bfab-32abaa1dd99e	3.5	Star Wars: Episode V - The Empire Strikes Back
13d30151-838e-44e5-bfab-32abaa1dd99e	3.5	Aladdin
13d30151-838e-44e5-bfab-32abaa1dd99e	3.5	Ace Ventura: Pet Detective
13d30151-838e-44e5-bfab-32abaa1dd99e	5.0	Fight Club
13d30151-838e-44e5-bfab-32abaa1dd99e	3.5	The Lion King
13d30151-838e-44e5-bfab-32abaa1dd99e	4.5	Schindler's List
13d30151-838e-44e5-bfab-32abaa1dd99e	5.0	The Lord of the Rings: The Two Towers
13d30151-838e-44e5-bfab-32abaa1dd99e	4.0	Raiders of the Lost Ark
13d30151-838e-44e5-bfab-32abaa1dd99e	3.0	Monsters, Inc.
13d30151-838e-44e5-bfab-32abaa1dd99e	4.0	X2: X-Men United
13d30151-838e-44e5-bfab-32abaa1dd99e	4.5	Finding Nemo
13d30151-838e-44e5-bfab-32abaa1dd99e	4.0	X-Men
13d30151-838e-44e5-bfab-32abaa1dd99e	4.5	Forrest Gump
13d30151-838e-44e5-bfab-32abaa1dd99e	2.0	Mrs. Doubtfire
13d30151-838e-44e5-bfab-32abaa1dd99e	3.0	Harry Potter and the Chamber of Secrets
13d30151-838e-44e5-bfab-32abaa1dd99e	4.0	The Godfather
13d30151-838e-44e5-bfab-32abaa1dd99e	5.0	The Shawshank Redemption
13d30151-838e-44e5-bfab-32abaa1dd99e	4.5	Catch Me If You Can
13d30151-838e-44e5-bfab-32abaa1dd99e	3.5	Pirates of the Caribbean: The Curse of the Black Pearl
Nathan_Studanski	3.5	The Dark Knight
Nathan_Studanski	3.5	Star Wars: Episode V - The Empire Strikes Back
Nathan_Studanski	4.0	The Bourne Identity
Nathan_Studanski	3.5	Shrek 2
Nathan_Studanski	4.0	Shrek
Nathan_Studanski	3.5	Monsters, Inc.
Nathan_Studanski	4.5	Harry Potter and the Philosopher's Stone
Nathan_Studanski	3.5	Star Wars: Episode II - Attack of the Clones
Nathan_Studanski	3.5	Spider-Man
Nathan_Studanski	3.5	The Incredibles
Nathan_Studanski	4.0	The Bourne Supremacy
Nathan_Studanski	2.5	The Mask
Nathan_Studanski	3.0	The Lion King
Nathan_Studanski	5.0	Back to the Future
Nathan_Studanski	4.5	Harry Potter and the Chamber of Secrets
Nathan_Studanski	5.0	Dumb and Dumber
Nathan_Studanski	4.5	Finding Nemo
Nathan_Studanski	3.0	Aladdin
Nathan_Studanski	4.5	Raiders of the Lost Ark
Nathan_Studanski	2.0	Pulp Fiction
Nathan_Studanski	4.0	Pirates of the Caribbean: The Curse of the Black Pearl
vikram	5.0	Forrest Gump
vikram	3.0	Dumb and Dumber
vikram	5.0	The Lord of the Rings: The Two Towers
vikram	3.0	The Mask
vikram	4.5	The Silence of the Lambs
vikram	2.5	Fight Club
vikram	4.0	Mrs. Doubtfire
vikram	3.0	Spider-Man
vikram	4.5	The Incredibles
vikram	5.0	The Shawshank Redemption
vikram	4.5	The Dark Knight
vikram	3.5	Ocean's Eleven
vikram	2.5	Chicken Run
vikram	3.5	Harry Potter and the Philosopher's Stone
vikram	4.5	Toy Story
vikram	4.0	Pirates of the Caribbean: The Curse of the Black Pearl
vikram	4.5	The Godfather
vikram	3.0	X2: X-Men United
vikram	2.0	Twister
vikram	3.5	V for Vendetta
vikram	2.0	Star Wars: Episode II - Attack of the Clones
vikram	3.5	Spider-Man 2
vikram	4.5	Cast Away
vikram	3.5	Men in Black
vikram	3.5	Die Hard: With a Vengeance
vikram	4.0	Aladdin
vikram	4.5	Star Wars: Episode V - The Empire Strikes Back
vikram	5.0	Titanic
vikram	4.5	Star Wars: Episode VI - Return of the Jedi
vikram	5.0	Beauty and the Beast
vikram	4.0	O Brother, Where Art Thou?
vikram	3.0	X-Men
vikram	4.0	The Lion King
vikram	4.5	Jurassic Park
vikram	4.5	The Fugitive
vikram	4.0	Finding Nemo
vikram	5.0	The Lord of the Rings: The Return of the King
vikram	4.5	Pulp Fiction
vikram	4.0	Shrek 2
vikram	4.5	The Lord of the Rings: The Fellowship of the Ring
vikram	4.0	Harry Potter and the Chamber of Secrets
vikram	3.0	Meet the Parents
vikram	4.5	Saving Private Ryan
vikram	4.0	A Beautiful Mind
vikram	3.5	Shrek
vikram	3.0	Speed
vikram	3.5	Fargo
vikram	4.0	Star Wars: Episode IV - A New Hope
vikram	4.5	Apollo 13
vikram	4.0	The Matrix
vikram	3.5	Monsters, Inc.
mongoose	4.0	Cast Away
mongoose	3.5	Ace Ventura: Pet Detective
mongoose	4.5	Aladdin
mongoose	4.0	Dumb and Dumber
mongoose	4.5	Meet the Parents
mongoose	4.5	Forrest Gump
mongoose	4.5	Toy Story
mongoose	3.0	Crouching Tiger, Hidden Dragon
mongoose	2.5	The Mask
mongoose	3.5	The Fugitive
mongoose	4.5	Star Wars: Episode IV - A New Hope
mongoose	4.0	Star Wars: Episode VI - Return of the Jedi
mongoose	4.0	AmAlie
mongoose	3.5	E.T. the Extra-Terrestrial
mongoose	4.0	Shrek
mongoose	2.5	Spider-Man 2
mongoose	4.0	Harry Potter and the Chamber of Secrets
mongoose	4.0	Men in Black
mongoose	4.5	The Incredibles
mongoose	5.0	Finding Nemo
mongoose	3.5	The Matrix
mongoose	3.5	Shrek 2
mongoose	4.5	Titanic
mongoose	4.0	Harry Potter and the Philosopher's Stone
mongoose	3.5	Memento
mongoose	3.5	The Bourne Identity
mongoose	3.0	The Dark Knight
mongoose	4.5	Beauty and the Beast
mongoose	5.0	Monsters, Inc.
mongoose	4.0	Pirates of the Caribbean: The Curse of the Black Pearl
mongoose	4.0	A Beautiful Mind
mongoose	4.5	The Lion King
mongoose	3.0	Independence Day
mongoose	3.5	Batman Begins
mongoose	3.5	Star Wars: Episode V - The Empire Strikes Back
mongoose	4.0	V for Vendetta
mongoose	2.5	Mrs. Doubtfire
mongoose	3.0	Spider-Man
mongoose	2.0	The Shawshank Redemption
ee144185-2957-46a0-af21-9cf5e7a972dc	3.5	The Incredibles
ee144185-2957-46a0-af21-9cf5e7a972dc	5.0	Minority Report
ee144185-2957-46a0-af21-9cf5e7a972dc	4.0	The Matrix
ee144185-2957-46a0-af21-9cf5e7a972dc	1.5	Harry Potter and the Chamber of Secrets
ee144185-2957-46a0-af21-9cf5e7a972dc	2.5	Snatch
ee144185-2957-46a0-af21-9cf5e7a972dc	3.5	Monsters, Inc.
ee144185-2957-46a0-af21-9cf5e7a972dc	0.5	Dumb and Dumber
ee144185-2957-46a0-af21-9cf5e7a972dc	4.5	V for Vendetta
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	3.0	Beauty and the Beast
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	3.0	Braveheart
ee144185-2957-46a0-af21-9cf5e7a972dc	3.0	Finding Nemo
ee144185-2957-46a0-af21-9cf5e7a972dc	1.5	Beauty and the Beast
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	4.5	The Lord of the Rings: The Two Towers
ee144185-2957-46a0-af21-9cf5e7a972dc	0.5	The Lord of the Rings: The Fellowship of the Ring
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	4.5	V for Vendetta
ee144185-2957-46a0-af21-9cf5e7a972dc	3.0	A Beautiful Mind
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	3.0	Chicken Run
ee144185-2957-46a0-af21-9cf5e7a972dc	5.0	The Dark Knight
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	4.5	Star Wars: Episode V - The Empire Strikes Back
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	4.5	Snatch
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	4.0	Harry Potter and the Philosopher's Stone
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	3.5	Twelve Monkeys
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	3.5	Star Wars: Episode II - Attack of the Clones
ee144185-2957-46a0-af21-9cf5e7a972dc	2.0	The Usual Suspects
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	3.5	Mission: Impossible
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	4.5	Pulp Fiction
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	4.5	Gladiator
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	4.5	Star Wars: Episode IV - A New Hope
ee144185-2957-46a0-af21-9cf5e7a972dc	3.0	Pulp Fiction
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	4.0	The Fugitive
ee144185-2957-46a0-af21-9cf5e7a972dc	5.0	Donnie Darko
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	4.0	Kill Bill: Vol. 2
ee144185-2957-46a0-af21-9cf5e7a972dc	5.0	Die Hard: With a Vengeance
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	4.0	Almost Famous
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	4.0	X-Men
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	3.5	Sin City
ee144185-2957-46a0-af21-9cf5e7a972dc	3.5	O Brother, Where Art Thou?
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	3.5	The Sixth Sense
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	4.0	The Bourne Supremacy
ee144185-2957-46a0-af21-9cf5e7a972dc	4.0	The Departed
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	4.0	Jurassic Park
ee144185-2957-46a0-af21-9cf5e7a972dc	2.0	Raiders of the Lost Ark
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	4.0	Memento
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	4.0	E.T. the Extra-Terrestrial
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	4.0	Harry Potter and the Chamber of Secrets
ee144185-2957-46a0-af21-9cf5e7a972dc	1.0	Harry Potter and the Philosopher's Stone
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	4.0	The Matrix
ee144185-2957-46a0-af21-9cf5e7a972dc	1.5	Ace Ventura: Pet Detective
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	4.5	Fight Club
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	4.5	Batman Begins
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	4.5	The Shawshank Redemption
ee144185-2957-46a0-af21-9cf5e7a972dc	3.5	Men in Black
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	4.0	Back to the Future
ee144185-2957-46a0-af21-9cf5e7a972dc	5.0	Fight Club
ee144185-2957-46a0-af21-9cf5e7a972dc	3.0	The Sixth Sense
ee144185-2957-46a0-af21-9cf5e7a972dc	5.0	Terminator 2: Judgment Day
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	3.5	The Silence of the Lambs
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	4.0	The Lord of the Rings: The Return of the King
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	4.0	Kill Bill: Vol. 1
ee144185-2957-46a0-af21-9cf5e7a972dc	3.0	Unbreakable
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	4.0	Finding Nemo
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	4.0	Fargo
ee144185-2957-46a0-af21-9cf5e7a972dc	2.0	Batman Begins
ee144185-2957-46a0-af21-9cf5e7a972dc	5.0	Eternal Sunshine of the Spotless Mind
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	3.5	Toy Story
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	4.0	The Lord of the Rings: The Fellowship of the Ring
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	3.0	Meet the Parents
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	3.0	Minority Report
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	3.5	Monsters, Inc.
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	4.0	The Dark Knight
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	3.0	X2: X-Men United
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	3.0	Spider-Man 2
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	4.0	The Incredibles
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	3.0	Spider-Man
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	4.0	The Bourne Identity
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	3.0	Ace Ventura: Pet Detective
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	3.5	Raiders of the Lost Ark
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	3.5	Pirates of the Caribbean: The Curse of the Black Pearl
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	3.5	The Lion King
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	4.0	Star Wars: Episode VI - Return of the Jedi
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	3.0	Mrs. Doubtfire
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	3.5	Forrest Gump
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	4.0	Dumb and Dumber
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	3.5	Terminator 2: Judgment Day
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	4.0	O Brother, Where Art Thou?
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	2.5	The Matrix Reloaded
c3e1cfa0-4677-4b03-a4b6-8d8d9b9a38f7	3.5	Ocean's Eleven
cond0155	4.5	O Brother, Where Art Thou?
cond0155	3.5	Harry Potter and the Philosopher's Stone
cond0155	3.5	Men in Black
cond0155	4.5	Back to the Future
cond0155	3.0	Saving Private Ryan
cond0155	3.0	The Silence of the Lambs
cond0155	4.0	Raiders of the Lost Ark
cond0155	4.5	The Bourne Supremacy
cond0155	4.0	Forrest Gump
cond0155	4.0	Aladdin
cond0155	3.5	E.T. the Extra-Terrestrial
cond0155	4.0	Cast Away
cond0155	3.5	X-Men
cond0155	1.5	Star Wars: Episode II - Attack of the Clones
cond0155	4.5	The Incredibles
cond0155	4.0	The Lion King
cond0155	4.5	The Lord of the Rings: The Fellowship of the Ring
cond0155	5.0	Toy Story
cond0155	4.0	Star Wars: Episode VI - Return of the Jedi
cond0155	3.5	Fargo
cond0155	3.5	The Lord of the Rings: The Two Towers
cond0155	1.5	Titanic
cond0155	5.0	A Beautiful Mind
cond0155	3.0	Independence Day
cond0155	3.0	The Matrix Reloaded
cond0155	3.0	Meet the Parents
cond0155	4.0	Star Wars: Episode IV - A New Hope
cond0155	4.0	Jurassic Park
cond0155	3.0	Harry Potter and the Chamber of Secrets
cond0155	5.0	Finding Nemo
cond0155	4.5	Pirates of the Caribbean: The Curse of the Black Pearl
cond0155	4.5	The Bourne Identity
cond0155	4.0	The Matrix
cond0155	4.5	Beauty and the Beast
cond0155	5.0	The Dark Knight
cond0155	4.5	Apollo 13
cond0155	2.0	Crouching Tiger, Hidden Dragon
cond0155	4.0	Batman Begins
cond0155	4.5	The Lord of the Rings: The Return of the King
cond0155	5.0	Monsters, Inc.
cond0155	3.5	X2: X-Men United
cond0155	4.5	Star Wars: Episode V - The Empire Strikes Back
6d87994b-d015-485b-926c-b2ddead6efd7	3.0	Ocean's Eleven
6d87994b-d015-485b-926c-b2ddead6efd7	4.0	Catch Me If You Can
6d87994b-d015-485b-926c-b2ddead6efd7	2.0	Harry Potter and the Chamber of Secrets
6d87994b-d015-485b-926c-b2ddead6efd7	3.5	Eternal Sunshine of the Spotless Mind
6d87994b-d015-485b-926c-b2ddead6efd7	3.0	Gladiator
6d87994b-d015-485b-926c-b2ddead6efd7	3.5	Batman Begins
6d87994b-d015-485b-926c-b2ddead6efd7	2.0	Twister
6d87994b-d015-485b-926c-b2ddead6efd7	2.5	Fargo
6d87994b-d015-485b-926c-b2ddead6efd7	3.5	Pulp Fiction
6d87994b-d015-485b-926c-b2ddead6efd7	3.5	V for Vendetta
6d87994b-d015-485b-926c-b2ddead6efd7	3.5	The Matrix
6d87994b-d015-485b-926c-b2ddead6efd7	3.5	Schindler's List
6d87994b-d015-485b-926c-b2ddead6efd7	3.0	Requiem for a Dream
6d87994b-d015-485b-926c-b2ddead6efd7	4.0	The Usual Suspects
6d87994b-d015-485b-926c-b2ddead6efd7	4.0	The Lord of the Rings: The Return of the King
6d87994b-d015-485b-926c-b2ddead6efd7	4.0	X-Men
6d87994b-d015-485b-926c-b2ddead6efd7	4.0	The Departed
6d87994b-d015-485b-926c-b2ddead6efd7	3.0	The Silence of the Lambs
6d87994b-d015-485b-926c-b2ddead6efd7	4.0	The Shawshank Redemption
6d87994b-d015-485b-926c-b2ddead6efd7	2.0	Harry Potter and the Philosopher's Stone
6d87994b-d015-485b-926c-b2ddead6efd7	3.5	Apollo 13
6d87994b-d015-485b-926c-b2ddead6efd7	3.0	Saving Private Ryan
6d87994b-d015-485b-926c-b2ddead6efd7	3.5	Se7en
6d87994b-d015-485b-926c-b2ddead6efd7	3.5	The Lord of the Rings: The Fellowship of the Ring
6d87994b-d015-485b-926c-b2ddead6efd7	4.0	A Beautiful Mind
6d87994b-d015-485b-926c-b2ddead6efd7	4.0	Fight Club
6d87994b-d015-485b-926c-b2ddead6efd7	3.0	X2: X-Men United
6d87994b-d015-485b-926c-b2ddead6efd7	3.0	Erin Brockovich
6d87994b-d015-485b-926c-b2ddead6efd7	3.0	Speed
6d87994b-d015-485b-926c-b2ddead6efd7	3.0	Pirates of the Caribbean: The Curse of the Black Pearl
Oblivion	5.0	Saving Private Ryan
Oblivion	2.5	Chicken Run
Oblivion	5.0	A Beautiful Mind
Oblivion	3.5	Stargate
Oblivion	4.0	Charlie's Angels
Oblivion	3.0	Speed
Oblivion	5.0	Schindler's List
Oblivion	5.0	Jurassic Park
Oblivion	4.0	Kill Bill: Vol. 1
Oblivion	5.0	Pirates of the Caribbean: The Curse of the Black Pearl
Oblivion	4.0	Batman Forever
Oblivion	5.0	Harry Potter and the Chamber of Secrets
Oblivion	5.0	Men in Black
Oblivion	5.0	Crouching Tiger, Hidden Dragon
Oblivion	5.0	The Dark Knight
Oblivion	5.0	Star Wars: Episode II - Attack of the Clones
Oblivion	5.0	Mission: Impossible
Oblivion	5.0	Memento
Oblivion	5.0	Spider-Man 2
Oblivion	4.0	Shrek
Oblivion	4.5	The Lord of the Rings: The Two Towers
Oblivion	4.5	Batman Begins
Oblivion	5.0	Ocean's Eleven
Oblivion	5.0	Gladiator
Oblivion	4.0	The Incredibles
Oblivion	5.0	Titanic
Oblivion	5.0	Mission: Impossible II
Oblivion	5.0	Finding Nemo
Oblivion	5.0	Toy Story
Oblivion	4.5	Monsters, Inc.
Oblivion	4.5	The Godfather
Oblivion	5.0	Independence Day
Oblivion	5.0	Meet the Parents
Oblivion	5.0	The Lord of the Rings: The Fellowship of the Ring
Oblivion	4.0	Back to the Future
Oblivion	5.0	E.T. the Extra-Terrestrial
Oblivion	5.0	Catch Me If You Can
Oblivion	5.0	The Bourne Supremacy
Oblivion	5.0	Minority Report
Oblivion	5.0	The Rock
Oblivion	5.0	Forrest Gump
Oblivion	4.5	Spider-Man
Oblivion	5.0	X2: X-Men United
Oblivion	4.5	Shrek 2
Oblivion	5.0	The Shawshank Redemption
Oblivion	5.0	The Lord of the Rings: The Return of the King
Oblivion	4.5	AmAlie
Oblivion	5.0	Harry Potter and the Philosopher's Stone
Oblivion	5.0	The Matrix
Oblivion	5.0	O Brother, Where Art Thou?
Oblivion	5.0	The Bourne Identity
Oblivion	5.0	X-Men
142a1e51-8723-45d4-85b4-54b6f87b4d4f	3.5	The Bourne Identity
142a1e51-8723-45d4-85b4-54b6f87b4d4f	3.5	The Bourne Supremacy
142a1e51-8723-45d4-85b4-54b6f87b4d4f	3.5	Toy Story
142a1e51-8723-45d4-85b4-54b6f87b4d4f	5.0	Star Wars: Episode V - The Empire Strikes Back
142a1e51-8723-45d4-85b4-54b6f87b4d4f	4.0	Monsters, Inc.
142a1e51-8723-45d4-85b4-54b6f87b4d4f	4.5	Forrest Gump
142a1e51-8723-45d4-85b4-54b6f87b4d4f	3.5	Aladdin
142a1e51-8723-45d4-85b4-54b6f87b4d4f	4.0	Finding Nemo
142a1e51-8723-45d4-85b4-54b6f87b4d4f	4.5	Star Wars: Episode II - Attack of the Clones
142a1e51-8723-45d4-85b4-54b6f87b4d4f	5.0	Star Wars: Episode VI - Return of the Jedi
142a1e51-8723-45d4-85b4-54b6f87b4d4f	4.0	The Incredibles
142a1e51-8723-45d4-85b4-54b6f87b4d4f	4.5	Fight Club
142a1e51-8723-45d4-85b4-54b6f87b4d4f	5.0	Star Wars: Episode IV - A New Hope
142a1e51-8723-45d4-85b4-54b6f87b4d4f	1.0	Spider-Man 2
Nick	5.0	Toy Story
Nick	4.0	The Lion King
Nick	4.5	Monsters, Inc.
Nick	4.5	X-Men
Nick	4.5	Shrek
Nick	4.5	Schindler's List
Nick	4.5	Star Wars: Episode VI - Return of the Jedi
Nick	3.0	Shrek 2
Nick	4.5	Batman Begins
Nick	5.0	The Matrix
Nick	4.5	V for Vendetta
Nick	5.0	The Dark Knight
Nick	4.0	Harry Potter and the Chamber of Secrets
Nick	2.0	Star Wars: Episode II - Attack of the Clones
Nick	5.0	The Lord of the Rings: The Two Towers
Nick	4.5	Dumb and Dumber
Nick	3.5	The Mask
Nick	4.0	Star Wars: Episode IV - A New Hope
Nick	5.0	The Lord of the Rings: The Return of the King
Nick	5.0	The Lord of the Rings: The Fellowship of the Ring
Nick	4.0	Finding Nemo
Nick	4.0	Titanic
Nick	4.0	Star Wars: Episode V - The Empire Strikes Back
Nick	4.0	The Matrix Reloaded
Nick	5.0	Pirates of the Caribbean: The Curse of the Black Pearl
terveen	3.5	The Shawshank Redemption
terveen	4.5	The Godfather
terveen	4.5	Saving Private Ryan
terveen	3.5	Independence Day
terveen	3.5	Gladiator
terveen	4.0	X-Men
terveen	4.5	Donnie Darko
terveen	4.5	O Brother, Where Art Thou?
terveen	3.0	Harry Potter and the Philosopher's Stone
terveen	3.5	American Beauty
terveen	3.5	Pretty Woman
terveen	5.0	Monsters, Inc.
terveen	5.0	Crouching Tiger, Hidden Dragon
terveen	4.5	Traffic
terveen	3.5	Titanic
terveen	5.0	The Silence of the Lambs
terveen	3.5	Unbreakable
terveen	5.0	Jurassic Park
terveen	5.0	Lost in Translation
terveen	4.0	The Lion King
terveen	5.0	The Usual Suspects
terveen	5.0	Finding Nemo
terveen	4.0	Fight Club
terveen	5.0	Raiders of the Lost Ark
terveen	4.5	Minority Report
terveen	3.5	Harry Potter and the Chamber of Secrets
terveen	5.0	Terminator 2: Judgment Day
terveen	5.0	E.T. the Extra-Terrestrial
terveen	5.0	Twelve Monkeys
terveen	3.0	Die Hard: With a Vengeance
terveen	5.0	The Sixth Sense
terveen	4.0	Cast Away
terveen	5.0	Star Wars: Episode IV - A New Hope
terveen	5.0	High Fidelity
terveen	4.0	Apollo 13
terveen	5.0	Memento
terveen	4.0	Stargate
terveen	5.0	Pulp Fiction
terveen	5.0	The Matrix
terveen	5.0	Toy Story
terveen	5.0	The Lord of the Rings: The Return of the King
terveen	4.0	The Fugitive
terveen	1.0	Star Wars: Episode II - Attack of the Clones
terveen	5.0	The Incredibles
terveen	4.5	Schindler's List
terveen	5.0	Star Wars: Episode V - The Empire Strikes Back
terveen	3.5	Meet the Parents
terveen	4.5	The Bourne Identity
terveen	3.5	Men in Black
terveen	5.0	Fargo
terveen	5.0	The Lord of the Rings: The Fellowship of the Ring
terveen	4.0	Erin Brockovich
terveen	4.0	Star Wars: Episode VI - Return of the Jedi
terveen	4.0	Catch Me If You Can
terveen	3.0	The Matrix Reloaded
terveen	3.0	Dances with Wolves
terveen	4.0	Ocean's Eleven
terveen	4.0	Spider-Man
terveen	4.0	Back to the Future
terveen	4.5	Almost Famous
terveen	5.0	The Lord of the Rings: The Two Towers
14684581-beae-4309-890f-2c64c4be8fc0	4.5	Braveheart
14684581-beae-4309-890f-2c64c4be8fc0	2.0	Chicken Run
14684581-beae-4309-890f-2c64c4be8fc0	5.0	A Beautiful Mind
14684581-beae-4309-890f-2c64c4be8fc0	4.0	The Incredibles
14684581-beae-4309-890f-2c64c4be8fc0	3.5	The Lord of the Rings: The Fellowship of the Ring
14684581-beae-4309-890f-2c64c4be8fc0	5.0	Titanic
14684581-beae-4309-890f-2c64c4be8fc0	3.0	Spider-Man
14684581-beae-4309-890f-2c64c4be8fc0	4.0	Independence Day
14684581-beae-4309-890f-2c64c4be8fc0	4.0	The Matrix
14684581-beae-4309-890f-2c64c4be8fc0	5.0	Forrest Gump
14684581-beae-4309-890f-2c64c4be8fc0	4.0	Spider-Man 2
14684581-beae-4309-890f-2c64c4be8fc0	4.0	Shrek
14684581-beae-4309-890f-2c64c4be8fc0	4.5	The Lord of the Rings: The Two Towers
14684581-beae-4309-890f-2c64c4be8fc0	3.5	Finding Nemo
14684581-beae-4309-890f-2c64c4be8fc0	4.5	Saving Private Ryan
14684581-beae-4309-890f-2c64c4be8fc0	4.0	Beauty and the Beast
14684581-beae-4309-890f-2c64c4be8fc0	3.0	The Lion King
14684581-beae-4309-890f-2c64c4be8fc0	3.5	Men in Black
14684581-beae-4309-890f-2c64c4be8fc0	4.5	Aladdin
14684581-beae-4309-890f-2c64c4be8fc0	4.5	Harry Potter and the Chamber of Secrets
14684581-beae-4309-890f-2c64c4be8fc0	4.5	Jurassic Park
14684581-beae-4309-890f-2c64c4be8fc0	4.0	The Lord of the Rings: The Return of the King
14684581-beae-4309-890f-2c64c4be8fc0	3.5	The Shawshank Redemption
14684581-beae-4309-890f-2c64c4be8fc0	3.5	Monsters, Inc.
14684581-beae-4309-890f-2c64c4be8fc0	4.0	V for Vendetta
14684581-beae-4309-890f-2c64c4be8fc0	4.5	The Dark Knight
14684581-beae-4309-890f-2c64c4be8fc0	4.0	The Sixth Sense
14684581-beae-4309-890f-2c64c4be8fc0	3.0	Terminator 2: Judgment Day
14684581-beae-4309-890f-2c64c4be8fc0	3.5	Pirates of the Caribbean: The Curse of the Black Pearl
14684581-beae-4309-890f-2c64c4be8fc0	2.0	The Matrix Reloaded
14684581-beae-4309-890f-2c64c4be8fc0	3.0	Harry Potter and the Philosopher's Stone
13154079-0169-498a-9923-29e70ad2daa4	5.0	Star Wars: Episode IV - A New Hope
13154079-0169-498a-9923-29e70ad2daa4	3.5	Shrek 2
13154079-0169-498a-9923-29e70ad2daa4	5.0	Monsters, Inc.
13154079-0169-498a-9923-29e70ad2daa4	3.0	Spider-Man
13154079-0169-498a-9923-29e70ad2daa4	2.5	Beauty and the Beast
13154079-0169-498a-9923-29e70ad2daa4	3.5	The Matrix Reloaded
13154079-0169-498a-9923-29e70ad2daa4	3.0	Spider-Man 2
13154079-0169-498a-9923-29e70ad2daa4	4.0	Aladdin
13154079-0169-498a-9923-29e70ad2daa4	5.0	Star Wars: Episode V - The Empire Strikes Back
13154079-0169-498a-9923-29e70ad2daa4	4.5	Finding Nemo
13154079-0169-498a-9923-29e70ad2daa4	4.5	Toy Story
13154079-0169-498a-9923-29e70ad2daa4	4.0	Shrek
13154079-0169-498a-9923-29e70ad2daa4	4.0	Independence Day
13154079-0169-498a-9923-29e70ad2daa4	3.0	The Matrix
13154079-0169-498a-9923-29e70ad2daa4	4.5	The Bourne Supremacy
13154079-0169-498a-9923-29e70ad2daa4	4.5	Raiders of the Lost Ark
13154079-0169-498a-9923-29e70ad2daa4	2.0	Terminator 2: Judgment Day
13154079-0169-498a-9923-29e70ad2daa4	4.0	The Incredibles
13154079-0169-498a-9923-29e70ad2daa4	5.0	Star Wars: Episode VI - Return of the Jedi
13154079-0169-498a-9923-29e70ad2daa4	3.5	Braveheart
13154079-0169-498a-9923-29e70ad2daa4	3.5	Mission: Impossible
13154079-0169-498a-9923-29e70ad2daa4	4.0	Pirates of the Caribbean: The Curse of the Black Pearl
13154079-0169-498a-9923-29e70ad2daa4	5.0	Ocean's Eleven
13154079-0169-498a-9923-29e70ad2daa4	4.0	The Dark Knight
13154079-0169-498a-9923-29e70ad2daa4	4.0	Batman Begins
13154079-0169-498a-9923-29e70ad2daa4	4.5	Star Wars: Episode II - Attack of the Clones
13154079-0169-498a-9923-29e70ad2daa4	4.0	Chicken Run
13154079-0169-498a-9923-29e70ad2daa4	4.0	The Bourne Identity
14150340-dc4b-4eca-a845-d92ac49281ea	4.5	The Lord of the Rings: The Two Towers
14150340-dc4b-4eca-a845-d92ac49281ea	5.0	The Dark Knight
14150340-dc4b-4eca-a845-d92ac49281ea	4.5	AmAlie
14150340-dc4b-4eca-a845-d92ac49281ea	4.5	The Lord of the Rings: The Fellowship of the Ring
14150340-dc4b-4eca-a845-d92ac49281ea	5.0	The Shawshank Redemption
14150340-dc4b-4eca-a845-d92ac49281ea	3.5	The Matrix
14150340-dc4b-4eca-a845-d92ac49281ea	4.5	The Godfather
14150340-dc4b-4eca-a845-d92ac49281ea	4.5	Titanic
14150340-dc4b-4eca-a845-d92ac49281ea	4.5	Forrest Gump
14150340-dc4b-4eca-a845-d92ac49281ea	4.5	Monsters, Inc.
14150340-dc4b-4eca-a845-d92ac49281ea	3.0	Batman Begins
14150340-dc4b-4eca-a845-d92ac49281ea	4.5	The Bourne Supremacy
14150340-dc4b-4eca-a845-d92ac49281ea	4.0	Chicken Run
14150340-dc4b-4eca-a845-d92ac49281ea	3.5	Star Wars: Episode V - The Empire Strikes Back
14150340-dc4b-4eca-a845-d92ac49281ea	4.5	E.T. the Extra-Terrestrial
14150340-dc4b-4eca-a845-d92ac49281ea	4.5	Fight Club
14150340-dc4b-4eca-a845-d92ac49281ea	5.0	Se7en
14150340-dc4b-4eca-a845-d92ac49281ea	3.5	Star Wars: Episode IV - A New Hope
14150340-dc4b-4eca-a845-d92ac49281ea	4.0	Harry Potter and the Philosopher's Stone
14150340-dc4b-4eca-a845-d92ac49281ea	3.5	V for Vendetta
14150340-dc4b-4eca-a845-d92ac49281ea	3.5	The Lion King
14150340-dc4b-4eca-a845-d92ac49281ea	3.5	The Incredibles
edc4c49c-d263-4d37-bc57-da5f7a344800	3.0	Spider-Man
edc4c49c-d263-4d37-bc57-da5f7a344800	4.0	Harry Potter and the Chamber of Secrets
edc4c49c-d263-4d37-bc57-da5f7a344800	1.5	Star Wars: Episode II - Attack of the Clones
Lange	5.0	The Lord of the Rings: The Fellowship of the Ring
Lange	3.5	The Lion King
Lange	3.5	Raiders of the Lost Ark
14150340-dc4b-4eca-a845-d92ac49281ea	5.0	The Silence of the Lambs
Lange	3.5	Shrek
14150340-dc4b-4eca-a845-d92ac49281ea	4.5	The Bourne Identity
Lange	4.0	Pirates of the Caribbean: The Curse of the Black Pearl
Lange	3.5	The Fugitive
14150340-dc4b-4eca-a845-d92ac49281ea	4.5	The Lord of the Rings: The Return of the King
Lange	4.0	Spider-Man
14150340-dc4b-4eca-a845-d92ac49281ea	3.0	Star Wars: Episode II - Attack of the Clones
14150340-dc4b-4eca-a845-d92ac49281ea	4.5	Toy Story
14150340-dc4b-4eca-a845-d92ac49281ea	5.0	Pulp Fiction
Lange	4.0	The Matrix
14150340-dc4b-4eca-a845-d92ac49281ea	4.0	Harry Potter and the Chamber of Secrets
Lange	4.0	Stargate
Lange	5.0	The Dark Knight
Lange	4.0	Batman Forever
Lange	4.0	The Bourne Identity
Lange	4.0	Schindler's List
Lange	4.0	The Sixth Sense
Lange	3.0	X-Men
14150340-dc4b-4eca-a845-d92ac49281ea	3.5	The Matrix Reloaded
Lange	4.0	Batman Begins
Lange	5.0	Back to the Future
14150340-dc4b-4eca-a845-d92ac49281ea	4.0	Finding Nemo
14150340-dc4b-4eca-a845-d92ac49281ea	4.0	The Departed
Lange	5.0	Se7en
Lange	4.5	Star Wars: Episode IV - A New Hope
14150340-dc4b-4eca-a845-d92ac49281ea	4.5	Schindler's List
Lange	3.5	Mission: Impossible II
Lange	3.5	The Lord of the Rings: The Return of the King
Lange	2.5	Beauty and the Beast
Lange	4.0	Requiem for a Dream
Lange	3.5	Shrek 2
Lange	4.5	Star Wars: Episode II - Attack of the Clones
Lange	5.0	Titanic
Lange	5.0	Toy Story
Lange	3.5	Mission: Impossible
Lange	4.0	Harry Potter and the Chamber of Secrets
Lange	3.5	Jurassic Park
14150340-dc4b-4eca-a845-d92ac49281ea	3.0	Star Wars: Episode VI - Return of the Jedi
14150340-dc4b-4eca-a845-d92ac49281ea	4.0	Pirates of the Caribbean: The Curse of the Black Pearl
Lange	4.5	Meet the Parents
Lange	4.0	Ace Ventura: Pet Detective
Lange	3.5	Apollo 13
Lange	4.5	A Beautiful Mind
Lange	4.5	The Mask
Lange	5.0	Charlie's Angels
Lange	5.0	The Lord of the Rings: The Two Towers
Lange	5.0	The Silence of the Lambs
Lange	4.0	Independence Day
Lange	4.0	Speed
Lange	4.5	Finding Nemo
Lange	4.5	Monsters, Inc.
Lange	5.0	Forrest Gump
Lange	5.0	Saving Private Ryan
Lange	5.0	Batman
Lange	4.0	Aladdin
80169ff0-eb90-473a-8779-ea537c9f6955	2.0	Chicken Run
Lange	5.0	Men in Black
80169ff0-eb90-473a-8779-ea537c9f6955	5.0	The Matrix Reloaded
Lange	5.0	Dumb and Dumber
Lange	4.0	The Incredibles
Lange	4.0	Star Wars: Episode VI - Return of the Jedi
80169ff0-eb90-473a-8779-ea537c9f6955	5.0	X-Men
Lange	5.0	The Rock
Lange	5.0	Star Wars: Episode V - The Empire Strikes Back
Lange	5.0	Terminator 2: Judgment Day
Lange	3.5	Chicken Run
80169ff0-eb90-473a-8779-ea537c9f6955	4.5	Harry Potter and the Chamber of Secrets
80169ff0-eb90-473a-8779-ea537c9f6955	5.0	The Lord of the Rings: The Return of the King
80169ff0-eb90-473a-8779-ea537c9f6955	4.5	The Silence of the Lambs
80169ff0-eb90-473a-8779-ea537c9f6955	5.0	The Lord of the Rings: The Two Towers
80169ff0-eb90-473a-8779-ea537c9f6955	3.5	Independence Day
80169ff0-eb90-473a-8779-ea537c9f6955	4.5	Toy Story
80169ff0-eb90-473a-8779-ea537c9f6955	4.5	The Sixth Sense
80169ff0-eb90-473a-8779-ea537c9f6955	5.0	Harry Potter and the Philosopher's Stone
80169ff0-eb90-473a-8779-ea537c9f6955	5.0	The Dark Knight
80169ff0-eb90-473a-8779-ea537c9f6955	5.0	The Bourne Identity
80169ff0-eb90-473a-8779-ea537c9f6955	3.5	Finding Nemo
80169ff0-eb90-473a-8779-ea537c9f6955	4.5	The Bourne Supremacy
80169ff0-eb90-473a-8779-ea537c9f6955	3.5	Titanic
80169ff0-eb90-473a-8779-ea537c9f6955	5.0	Aladdin
80169ff0-eb90-473a-8779-ea537c9f6955	3.0	Spider-Man
80169ff0-eb90-473a-8779-ea537c9f6955	4.5	Jurassic Park
80169ff0-eb90-473a-8779-ea537c9f6955	3.0	The Incredibles
80169ff0-eb90-473a-8779-ea537c9f6955	3.5	Monsters, Inc.
80169ff0-eb90-473a-8779-ea537c9f6955	2.5	X2: X-Men United
80169ff0-eb90-473a-8779-ea537c9f6955	5.0	The Matrix
80169ff0-eb90-473a-8779-ea537c9f6955	3.0	Mission: Impossible
80169ff0-eb90-473a-8779-ea537c9f6955	5.0	The Lion King
80169ff0-eb90-473a-8779-ea537c9f6955	3.0	Spider-Man 2
80169ff0-eb90-473a-8779-ea537c9f6955	4.0	Mission: Impossible II
80169ff0-eb90-473a-8779-ea537c9f6955	4.5	Batman Begins
80169ff0-eb90-473a-8779-ea537c9f6955	5.0	Men in Black
80169ff0-eb90-473a-8779-ea537c9f6955	4.0	Pretty Woman
80169ff0-eb90-473a-8779-ea537c9f6955	4.0	Terminator 2: Judgment Day
80169ff0-eb90-473a-8779-ea537c9f6955	5.0	Gladiator
80169ff0-eb90-473a-8779-ea537c9f6955	3.5	Shrek
80169ff0-eb90-473a-8779-ea537c9f6955	3.0	Pirates of the Caribbean: The Curse of the Black Pearl
80169ff0-eb90-473a-8779-ea537c9f6955	5.0	Beauty and the Beast
80169ff0-eb90-473a-8779-ea537c9f6955	4.0	Ocean's Eleven
80169ff0-eb90-473a-8779-ea537c9f6955	5.0	A Beautiful Mind
80169ff0-eb90-473a-8779-ea537c9f6955	5.0	The Lord of the Rings: The Fellowship of the Ring
80169ff0-eb90-473a-8779-ea537c9f6955	5.0	Forrest Gump
80169ff0-eb90-473a-8779-ea537c9f6955	5.0	Minority Report
80169ff0-eb90-473a-8779-ea537c9f6955	2.5	Shrek 2
edc4c49c-d263-4d37-bc57-da5f7a344800	4.0	Charlie's Angels
edc4c49c-d263-4d37-bc57-da5f7a344800	4.5	V for Vendetta
edc4c49c-d263-4d37-bc57-da5f7a344800	5.0	Raiders of the Lost Ark
edc4c49c-d263-4d37-bc57-da5f7a344800	3.5	Braveheart
edc4c49c-d263-4d37-bc57-da5f7a344800	2.5	Meet the Parents
edc4c49c-d263-4d37-bc57-da5f7a344800	3.5	E.T. the Extra-Terrestrial
edc4c49c-d263-4d37-bc57-da5f7a344800	3.0	Aladdin
edc4c49c-d263-4d37-bc57-da5f7a344800	5.0	Batman Begins
edc4c49c-d263-4d37-bc57-da5f7a344800	3.5	Beauty and the Beast
edc4c49c-d263-4d37-bc57-da5f7a344800	4.5	The Matrix
edc4c49c-d263-4d37-bc57-da5f7a344800	4.0	Mission: Impossible
edc4c49c-d263-4d37-bc57-da5f7a344800	4.0	Finding Nemo
edc4c49c-d263-4d37-bc57-da5f7a344800	4.0	Pirates of the Caribbean: The Curse of the Black Pearl
edc4c49c-d263-4d37-bc57-da5f7a344800	4.5	Star Wars: Episode V - The Empire Strikes Back
edc4c49c-d263-4d37-bc57-da5f7a344800	3.5	Shrek
edc4c49c-d263-4d37-bc57-da5f7a344800	4.5	The Bourne Identity
edc4c49c-d263-4d37-bc57-da5f7a344800	3.5	The Matrix Reloaded
edc4c49c-d263-4d37-bc57-da5f7a344800	4.0	The Incredibles
edc4c49c-d263-4d37-bc57-da5f7a344800	5.0	The Bourne Supremacy
edc4c49c-d263-4d37-bc57-da5f7a344800	5.0	The Lord of the Rings: The Two Towers
edc4c49c-d263-4d37-bc57-da5f7a344800	4.0	Mrs. Doubtfire
edc4c49c-d263-4d37-bc57-da5f7a344800	3.5	The Lion King
edc4c49c-d263-4d37-bc57-da5f7a344800	5.0	Ocean's Eleven
edc4c49c-d263-4d37-bc57-da5f7a344800	5.0	Catch Me If You Can
edc4c49c-d263-4d37-bc57-da5f7a344800	3.5	Die Hard: With a Vengeance
edc4c49c-d263-4d37-bc57-da5f7a344800	5.0	Back to the Future
edc4c49c-d263-4d37-bc57-da5f7a344800	3.5	Apollo 13
edc4c49c-d263-4d37-bc57-da5f7a344800	5.0	The Lord of the Rings: The Fellowship of the Ring
edc4c49c-d263-4d37-bc57-da5f7a344800	5.0	The Lord of the Rings: The Return of the King
edc4c49c-d263-4d37-bc57-da5f7a344800	5.0	Star Wars: Episode VI - Return of the Jedi
edc4c49c-d263-4d37-bc57-da5f7a344800	4.0	Toy Story
edc4c49c-d263-4d37-bc57-da5f7a344800	5.0	The Dark Knight
edc4c49c-d263-4d37-bc57-da5f7a344800	3.5	Men in Black
edc4c49c-d263-4d37-bc57-da5f7a344800	4.0	Independence Day
edc4c49c-d263-4d37-bc57-da5f7a344800	3.5	Gladiator
edc4c49c-d263-4d37-bc57-da5f7a344800	4.0	Forrest Gump
edc4c49c-d263-4d37-bc57-da5f7a344800	4.5	Star Wars: Episode IV - A New Hope
edc4c49c-d263-4d37-bc57-da5f7a344800	3.5	Shrek 2
edc4c49c-d263-4d37-bc57-da5f7a344800	4.5	The Silence of the Lambs
edc4c49c-d263-4d37-bc57-da5f7a344800	4.0	Titanic
edc4c49c-d263-4d37-bc57-da5f7a344800	3.5	Monsters, Inc.
edc4c49c-d263-4d37-bc57-da5f7a344800	4.5	Jurassic Park
edc4c49c-d263-4d37-bc57-da5f7a344800	4.5	Harry Potter and the Philosopher's Stone
edc4c49c-d263-4d37-bc57-da5f7a344800	4.0	Spider-Man 2
DevinLange	4.5	Schindler's List
DevinLange	4.0	Raiders of the Lost Ark
DevinLange	4.0	The Bourne Supremacy
DevinLange	3.0	Charlie's Angels
DevinLange	4.5	Star Wars: Episode V - The Empire Strikes Back
DevinLange	4.0	Finding Nemo
DevinLange	4.5	Beauty and the Beast
DevinLange	3.5	Fight Club
DevinLange	4.5	Star Wars: Episode VI - Return of the Jedi
DevinLange	4.0	The Bourne Identity
DevinLange	4.0	Shrek
DevinLange	3.5	Batman Begins
DevinLange	4.0	Aladdin
DevinLange	4.5	The Dark Knight
DevinLange	4.5	Star Wars: Episode IV - A New Hope
DevinLange	4.0	Braveheart
DevinLange	3.5	X2: X-Men United
DevinLange	3.5	Kill Bill: Vol. 1
DevinLange	5.0	The Lord of the Rings: The Fellowship of the Ring
DevinLange	3.5	The Silence of the Lambs
DevinLange	4.0	Donnie Darko
DevinLange	3.0	Kill Bill: Vol. 2
DevinLange	4.0	Ocean's Eleven
DevinLange	4.0	A Beautiful Mind
DevinLange	4.0	The Lion King
DevinLange	4.0	O Brother, Where Art Thou?
DevinLange	3.5	Jurassic Park
DevinLange	3.5	Spider-Man
DevinLange	4.0	Crouching Tiger, Hidden Dragon
DevinLange	4.5	The Matrix
DevinLange	3.5	Shrek 2
DevinLange	4.0	Toy Story
DevinLange	5.0	The Lord of the Rings: The Two Towers
DevinLange	3.5	Die Hard: With a Vengeance
DevinLange	4.5	Pirates of the Caribbean: The Curse of the Black Pearl
DevinLange	4.0	Harry Potter and the Chamber of Secrets
DevinLange	3.5	V for Vendetta
DevinLange	3.0	The Mask
DevinLange	4.0	Men in Black
DevinLange	4.5	Saving Private Ryan
DevinLange	4.0	The Incredibles
DevinLange	3.5	Spider-Man 2
DevinLange	4.0	Monsters, Inc.
DevinLange	4.0	The Matrix Reloaded
DevinLange	4.0	Back to the Future
DevinLange	4.5	Harry Potter and the Philosopher's Stone
DevinLange	4.5	Star Wars: Episode II - Attack of the Clones
DevinLange	3.0	Chicken Run
DevinLange	4.5	Forrest Gump
DevinLange	5.0	The Lord of the Rings: The Return of the King
DevinLange	4.0	X-Men
polli012	3.5	Pirates of the Caribbean: The Curse of the Black Pearl
polli012	2.0	Crouching Tiger, Hidden Dragon
polli012	4.5	V for Vendetta
polli012	4.0	Fight Club
polli012	1.0	E.T. the Extra-Terrestrial
polli012	3.5	Toy Story
polli012	4.5	Shrek 2
polli012	2.5	Beauty and the Beast
polli012	4.0	The Matrix
polli012	4.0	Back to the Future
polli012	5.0	Minority Report
polli012	4.5	The Silence of the Lambs
polli012	5.0	The Shawshank Redemption
polli012	4.0	Harry Potter and the Chamber of Secrets
polli012	5.0	Harry Potter and the Philosopher's Stone
polli012	4.0	Aladdin
polli012	4.0	Memento
polli012	5.0	The Incredibles
polli012	5.0	The Dark Knight
polli012	5.0	Ocean's Eleven
polli012	3.5	AmAlie
polli012	4.0	Shrek
polli012	4.5	Batman Begins
polli012	3.5	The Godfather
polli012	2.5	Forrest Gump
polli012	1.5	The Lion King
polli012	3.5	Finding Nemo
polli012	3.0	Independence Day
polli012	4.0	Monsters, Inc.
polli012	3.5	Se7en
6632e5b3-89cc-461c-aaf7-06e69e634333	4.0	The Silence of the Lambs
6632e5b3-89cc-461c-aaf7-06e69e634333	3.0	Batman
6632e5b3-89cc-461c-aaf7-06e69e634333	4.0	Batman Begins
6632e5b3-89cc-461c-aaf7-06e69e634333	5.0	Toy Story
6632e5b3-89cc-461c-aaf7-06e69e634333	4.0	Independence Day
6632e5b3-89cc-461c-aaf7-06e69e634333	3.5	Monsters, Inc.
6632e5b3-89cc-461c-aaf7-06e69e634333	3.5	Men in Black
6632e5b3-89cc-461c-aaf7-06e69e634333	4.0	Chicken Run
6632e5b3-89cc-461c-aaf7-06e69e634333	3.5	Star Wars: Episode VI - Return of the Jedi
6632e5b3-89cc-461c-aaf7-06e69e634333	3.5	Unbreakable
6632e5b3-89cc-461c-aaf7-06e69e634333	3.5	Dances with Wolves
6632e5b3-89cc-461c-aaf7-06e69e634333	4.5	A Beautiful Mind
6632e5b3-89cc-461c-aaf7-06e69e634333	4.5	Mission: Impossible
6632e5b3-89cc-461c-aaf7-06e69e634333	4.0	Shrek
6632e5b3-89cc-461c-aaf7-06e69e634333	4.0	Star Wars: Episode II - Attack of the Clones
6632e5b3-89cc-461c-aaf7-06e69e634333	4.0	X2: X-Men United
6632e5b3-89cc-461c-aaf7-06e69e634333	4.5	The Incredibles
6632e5b3-89cc-461c-aaf7-06e69e634333	4.5	Back to the Future
6632e5b3-89cc-461c-aaf7-06e69e634333	4.5	Forrest Gump
6632e5b3-89cc-461c-aaf7-06e69e634333	4.5	Schindler's List
6632e5b3-89cc-461c-aaf7-06e69e634333	3.5	AmAlie
6632e5b3-89cc-461c-aaf7-06e69e634333	4.0	Braveheart
6632e5b3-89cc-461c-aaf7-06e69e634333	3.5	Fargo
6632e5b3-89cc-461c-aaf7-06e69e634333	3.5	Shrek 2
6632e5b3-89cc-461c-aaf7-06e69e634333	5.0	The Lion King
6632e5b3-89cc-461c-aaf7-06e69e634333	4.5	Spider-Man
6632e5b3-89cc-461c-aaf7-06e69e634333	4.5	The Lord of the Rings: The Two Towers
6632e5b3-89cc-461c-aaf7-06e69e634333	3.0	Kill Bill: Vol. 2
6632e5b3-89cc-461c-aaf7-06e69e634333	4.0	Star Wars: Episode V - The Empire Strikes Back
6632e5b3-89cc-461c-aaf7-06e69e634333	5.0	Mission: Impossible II
6632e5b3-89cc-461c-aaf7-06e69e634333	4.0	The Patriot
6632e5b3-89cc-461c-aaf7-06e69e634333	4.5	Titanic
6632e5b3-89cc-461c-aaf7-06e69e634333	4.5	Star Wars: Episode IV - A New Hope
6632e5b3-89cc-461c-aaf7-06e69e634333	3.5	Harry Potter and the Chamber of Secrets
6632e5b3-89cc-461c-aaf7-06e69e634333	4.0	The Matrix
6632e5b3-89cc-461c-aaf7-06e69e634333	3.0	Crouching Tiger, Hidden Dragon
6632e5b3-89cc-461c-aaf7-06e69e634333	3.0	Sin City
6632e5b3-89cc-461c-aaf7-06e69e634333	4.0	Spider-Man 2
6632e5b3-89cc-461c-aaf7-06e69e634333	4.5	Saving Private Ryan
6632e5b3-89cc-461c-aaf7-06e69e634333	4.0	Die Hard: With a Vengeance
6632e5b3-89cc-461c-aaf7-06e69e634333	4.5	X-Men
6632e5b3-89cc-461c-aaf7-06e69e634333	4.5	Beauty and the Beast
6632e5b3-89cc-461c-aaf7-06e69e634333	4.5	The Lord of the Rings: The Return of the King
6632e5b3-89cc-461c-aaf7-06e69e634333	5.0	Meet the Parents
6632e5b3-89cc-461c-aaf7-06e69e634333	3.5	Terminator 2: Judgment Day
6632e5b3-89cc-461c-aaf7-06e69e634333	4.5	The Godfather
6632e5b3-89cc-461c-aaf7-06e69e634333	4.5	Aladdin
6632e5b3-89cc-461c-aaf7-06e69e634333	5.0	The Mask
6632e5b3-89cc-461c-aaf7-06e69e634333	5.0	Finding Nemo
6632e5b3-89cc-461c-aaf7-06e69e634333	3.0	Harry Potter and the Philosopher's Stone
6632e5b3-89cc-461c-aaf7-06e69e634333	3.5	Lost in Translation
bbbdc2b5-e28c-4cad-b59d-5043999e84e9	4.0	Finding Nemo
bbbdc2b5-e28c-4cad-b59d-5043999e84e9	3.5	Catch Me If You Can
bbbdc2b5-e28c-4cad-b59d-5043999e84e9	4.5	The Godfather
bbbdc2b5-e28c-4cad-b59d-5043999e84e9	3.5	Schindler's List
bbbdc2b5-e28c-4cad-b59d-5043999e84e9	5.0	Star Wars: Episode V - The Empire Strikes Back
bbbdc2b5-e28c-4cad-b59d-5043999e84e9	5.0	A Beautiful Mind
bbbdc2b5-e28c-4cad-b59d-5043999e84e9	4.5	Jurassic Park
bbbdc2b5-e28c-4cad-b59d-5043999e84e9	4.0	Spider-Man
bbbdc2b5-e28c-4cad-b59d-5043999e84e9	4.0	Apollo 13
bbbdc2b5-e28c-4cad-b59d-5043999e84e9	5.0	The Lord of the Rings: The Two Towers
bbbdc2b5-e28c-4cad-b59d-5043999e84e9	5.0	Back to the Future
bbbdc2b5-e28c-4cad-b59d-5043999e84e9	4.5	The Incredibles
bbbdc2b5-e28c-4cad-b59d-5043999e84e9	3.0	The Dark Knight
JosephIsAwesome	5.0	E.T. the Extra-Terrestrial
JosephIsAwesome	4.0	Dumb and Dumber
JosephIsAwesome	2.0	Spider-Man 2
JosephIsAwesome	1.5	Shrek 2
JosephIsAwesome	2.5	Star Wars: Episode II - Attack of the Clones
JosephIsAwesome	3.0	Mrs. Doubtfire
JosephIsAwesome	5.0	Cast Away
JosephIsAwesome	5.0	Fight Club
JosephIsAwesome	5.0	Raiders of the Lost Ark
JosephIsAwesome	5.0	Batman Begins
JosephIsAwesome	5.0	The Lord of the Rings: The Fellowship of the Ring
JosephIsAwesome	4.0	The Incredibles
JosephIsAwesome	4.5	The Bourne Supremacy
JosephIsAwesome	4.0	Beauty and the Beast
JosephIsAwesome	5.0	Finding Nemo
JosephIsAwesome	3.5	Pirates of the Caribbean: The Curse of the Black Pearl
JosephIsAwesome	4.0	Se7en
JosephIsAwesome	5.0	The Godfather
JosephIsAwesome	5.0	The Lord of the Rings: The Two Towers
JosephIsAwesome	4.0	The Fugitive
JosephIsAwesome	5.0	Kill Bill: Vol. 1
JosephIsAwesome	5.0	The Lion King
JosephIsAwesome	5.0	Star Wars: Episode VI - Return of the Jedi
JosephIsAwesome	5.0	Dances with Wolves
JosephIsAwesome	4.5	Harry Potter and the Chamber of Secrets
JosephIsAwesome	4.0	Chicken Run
JosephIsAwesome	5.0	Harry Potter and the Philosopher's Stone
JosephIsAwesome	5.0	Star Wars: Episode V - The Empire Strikes Back
JosephIsAwesome	4.0	Catch Me If You Can
JosephIsAwesome	5.0	The Patriot
JosephIsAwesome	5.0	The Matrix
JosephIsAwesome	5.0	Pulp Fiction
JosephIsAwesome	4.0	Apollo 13
JosephIsAwesome	4.5	Meet the Parents
JosephIsAwesome	5.0	Schindler's List
JosephIsAwesome	5.0	A Beautiful Mind
JosephIsAwesome	5.0	Titanic
JosephIsAwesome	5.0	The Departed
JosephIsAwesome	5.0	Aladdin
JosephIsAwesome	4.0	X2: X-Men United
JosephIsAwesome	4.0	The Sixth Sense
JosephIsAwesome	5.0	Toy Story
JosephIsAwesome	5.0	The Shawshank Redemption
JosephIsAwesome	5.0	The Lord of the Rings: The Return of the King
JosephIsAwesome	4.0	X-Men
JosephIsAwesome	5.0	Kill Bill: Vol. 2
JosephIsAwesome	4.0	Ocean's Eleven
JosephIsAwesome	5.0	Shrek
JosephIsAwesome	5.0	The Silence of the Lambs
JosephIsAwesome	4.0	V for Vendetta
JosephIsAwesome	3.0	Independence Day
JosephIsAwesome	4.5	The Bourne Identity
JosephIsAwesome	5.0	Forrest Gump
JosephIsAwesome	5.0	The Dark Knight
JosephIsAwesome	5.0	Gladiator
JosephIsAwesome	3.0	Pretty Woman
JosephIsAwesome	4.0	Back to the Future
JosephIsAwesome	5.0	Jurassic Park
JosephIsAwesome	5.0	Monsters, Inc.
JosephIsAwesome	5.0	Star Wars: Episode IV - A New Hope
JosephIsAwesome	3.5	Spider-Man
JosephIsAwesome	3.5	Men in Black
JosephIsAwesome	5.0	Braveheart
bbbdc2b5-e28c-4cad-b59d-5043999e84e9	4.0	Donnie Darko
bbbdc2b5-e28c-4cad-b59d-5043999e84e9	4.5	V for Vendetta
bbbdc2b5-e28c-4cad-b59d-5043999e84e9	5.0	Harry Potter and the Philosopher's Stone
bbbdc2b5-e28c-4cad-b59d-5043999e84e9	4.5	Pirates of the Caribbean: The Curse of the Black Pearl
bbbdc2b5-e28c-4cad-b59d-5043999e84e9	5.0	The Lord of the Rings: The Fellowship of the Ring
bbbdc2b5-e28c-4cad-b59d-5043999e84e9	4.0	Shrek 2
bbbdc2b5-e28c-4cad-b59d-5043999e84e9	4.0	Requiem for a Dream
bbbdc2b5-e28c-4cad-b59d-5043999e84e9	5.0	Aladdin
bbbdc2b5-e28c-4cad-b59d-5043999e84e9	5.0	Harry Potter and the Chamber of Secrets
bbbdc2b5-e28c-4cad-b59d-5043999e84e9	5.0	The Lion King
bbbdc2b5-e28c-4cad-b59d-5043999e84e9	5.0	Shrek
bbbdc2b5-e28c-4cad-b59d-5043999e84e9	5.0	Star Wars: Episode IV - A New Hope
bbbdc2b5-e28c-4cad-b59d-5043999e84e9	5.0	Star Wars: Episode VI - Return of the Jedi
bbbdc2b5-e28c-4cad-b59d-5043999e84e9	5.0	Star Wars: Episode II - Attack of the Clones
bbbdc2b5-e28c-4cad-b59d-5043999e84e9	0.5	Forrest Gump
bbbdc2b5-e28c-4cad-b59d-5043999e84e9	3.5	Monsters, Inc.
bbbdc2b5-e28c-4cad-b59d-5043999e84e9	5.0	The Lord of the Rings: The Return of the King
hi mom	3.5	Pirates of the Caribbean: The Curse of the Black Pearl
hi mom	3.0	O Brother, Where Art Thou?
hi mom	5.0	Saving Private Ryan
hi mom	4.0	Harry Potter and the Philosopher's Stone
hi mom	3.5	Titanic
hi mom	4.0	Terminator 2: Judgment Day
hi mom	4.5	Ocean's Eleven
hi mom	3.0	Chicken Run
hi mom	3.0	The Patriot
hi mom	4.5	Mission: Impossible
hi mom	3.5	Forrest Gump
hi mom	4.5	Shrek
hi mom	4.0	Apollo 13
hi mom	4.5	The Lord of the Rings: The Fellowship of the Ring
hi mom	3.5	The Lord of the Rings: The Two Towers
hi mom	3.0	The Fugitive
hi mom	3.0	A Beautiful Mind
hi mom	3.0	Harry Potter and the Chamber of Secrets
hi mom	3.5	The Bourne Supremacy
hi mom	5.0	The Lord of the Rings: The Return of the King
hi mom	4.5	The Dark Knight
hi mom	3.5	The Matrix Reloaded
hi mom	3.0	Memento
hi mom	4.0	Batman Begins
hi mom	5.0	The Incredibles
hi mom	4.0	Toy Story
hi mom	4.0	The Bourne Identity
hi mom	4.0	Spider-Man 2
hi mom	4.0	Braveheart
hi mom	3.5	Shrek 2
hi mom	4.0	Mission: Impossible II
hi mom	3.0	Crouching Tiger, Hidden Dragon
hi mom	4.0	Monsters, Inc.
hi mom	3.5	Pulp Fiction
hi mom	4.0	V for Vendetta
hi mom	4.5	The Silence of the Lambs
hi mom	4.5	Men in Black
hi mom	4.5	Independence Day
hi mom	4.0	Spider-Man



