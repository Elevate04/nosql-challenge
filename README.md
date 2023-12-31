#  nosql-challenge

## Part 1: Database and Jupyter Notebook Set Up

Use NoSQL_setup_starter.ipynb for this section of the challenge.

Import the data provided in the establishments.json file from your Terminal. Name the database uk_food and the collection establishments. Copy the text you used to import your data from your Terminal to a markdown cell in your notebook.

Within your notebook, import the libraries you need: PyMongo and Pretty Print (pprint).

Create an instance of the Mongo Client.

Confirm that you created the database and loaded the data properly:

List the databases you have in MongoDB. Confirm that uk_food is listed.
List the collection(s) in the database to ensure that establishments is there.
Find and display one document in the establishments collection using find_one and display with pprint.
Assign the establishments collection to a variable to prepare the collection for use.

## Part 2: Update the Database

Use NoSQL_setup_starter.ipynb for this section of the challenge.

The magazine editors have some requested modifications for the database before you can perform any queries or analysis for them. Make the following changes to the establishments collection:

An exciting new halal restaurant just opened in Greenwich, but hasn't been rated yet. The magazine has asked you to include it in your analysis. Add the following information to the database:

Find the BusinessTypeID for "Restaurant/Cafe/Canteen" and return only the BusinessTypeID and BusinessType fields.

Update the new restaurant with the BusinessTypeID you found.

The magazine is not interested in any establishments in Dover, so check how many documents contain the Dover Local Authority. Then, remove any establishments within the Dover Local Authority from the database, and check the number of documents to ensure they were deleted.

Some of the number values are stored as strings, when they should be stored as numbers.

Use update_many to convert latitude and longitude to decimal numbers.
Use update_many to convert RatingValue to integer numbers.

## Part 3: Exploratory Analysis

To receive all points, your Jupyter notebook analysis file must have all of the following:
Question 1: Which establishments have a hygiene score equal to 20? (8 points)

A query is correctly performed to find the establishments with a hygiene score of 20 (2 points)

count_documents() is used to list the correct number of documents (answer: 41) (2 points)

The first result is printed using pprint (2 points)

The results are converted to a Pandas DataFrame and displays the first 10 rows (2 points)

Question 2: Which establishments in London have a RatingValue greater than or equal to 4? (12 points)

A query is correctly performed to find the establishments in London with a RatingValue greater than or equal to 4 (4 points)

The query uses the $regex operator to locate the London establishments (2 points)

count_documents() is used to list the correct number of documents (answer: 33) (2 points)

The first result is printed using pprint (2 points)

The results are converted to a Pandas DataFrame and displays the first 10 rows (2 points)

Question 3: What are the top 5 establishments with a RatingValue of 5, sorted by lowest hygiene score, nearest to the new restaurant added, "Penang Flavours"? (15 points)

A query is correctly performed to find the establishments within 0.01 degree of the "Penang Flavours" restaurant (4 points)

The query also limits the results to establishments with a RatingValue of 5 (2 points)

The query uses the sort() method in PyMongo to sort in ascending order on the hygiene score (2 points)

The query uses the limit() method in PyMongo to limit the results to 5 (2 points)

All five results are printed using pprint (3 points)

The results are converted to a Pandas DataFrame and displayed (2 points)

Question 4: How many establishments in each Local Authority area have a hygiene score of 0? Sort the results from highest to lowest, and print out the top ten local authority areas. (20 points)

An aggregation pipeline is built to include a match query, group, and sort (3 points)

The match query matches documents with a hygiene score of 0 (2 points)

The group step of the pipeline is grouped on LocalAuthorityName and counts the number of documents (4 points)

The sort step of the pipeline sorts the count of the documents in descending order (2 points)

The aggregation pipeline is correctly sent to the aggregate() method (2 points)

The results from the aggregation query is cast as a list and then saved to a variable (2 points)

The first ten results are printed using pprint (3 points)

The results are converted to a Pandas DataFrame and displays the first 10 rows (2 points)

