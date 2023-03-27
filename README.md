# nosql-challenge
## Purpose
The UK Food Standards Agency evaluates various establishments across the United Kingdom, and gives them a food hygiene rating. I've been contracted by the editors of a food magazine, Eat Safe, Love, to evaluate some of the ratings data in order to help their journalists and food critics decide where to focus future articles. The to-do list is the following:
## Overview
### Part 1: Database and Jupyter Notebook Set Up
- [x] Include the mongoimport command text you used to import establishments.json in a markdown cell at the beginning of your Jupyter notebook file
- [x] The mongoimport command text correctly drops any existing establishments collection before importing establishments.json into MongoDB
- [x] The database is named uk_food and the collection is named establishments
- [x] Correctly imports PyMongo and Pretty Print
- [x] An instance of the Mongo Client is created
- [x] Lists the databases you have in Mongo, which includes uk_food
- [x] Lists the collection(s) in the uk_food database, which includes establishments in the output
- [x] Uses find_one() and pprint to display one document in the establishments collection
- [x] The establishments collection is assigned to a variable
### Part 2: Update the Database
- [x] The supplied data for the "Penang Flavours" restaurant is correctly inserted into the establishments collection
- [x] A query is performed to find the BusinessTypeID for "Restaurant/Cafe/Canteen" and returns only the BusinessTypeID and BusinessType fields
- [x] The "Penang Flavours" document is updated with the correct value for BusinessTypeID
- [x] A query is correctly performed to delete all the documents in the collection where "Dover Local Authority" is the value for LocalAuthorityName
- [x] A count_documents() check is performed before and after the removal of the Dover documents to ensure the documents were removed
- [x] An update_many() query is performed to convert the latitude and longitude fields from strings to decimal numbers
### Part 3: Exploratory Analysis
#### Question 1: Which establishments have a hygiene score equal to 20?
- [x] A query is correctly performed to find the establishments with a hygiene score of 20
- [x] count_documents() is used to list the correct number of documents (answer: 41)
- [x] The first result is printed using pprint
- [x] The results are converted to a Pandas DataFrame and displays the first 10 rows
#### Question 2: Which establishments in London have a RatingValue greater than or equal to 4?
- [x] A query is correctly performed to find the establishments in London with a RatingValue greater than or equal to 4
- [x] The query uses the $regex operator to locate the London establishments
- [x] count_documents() is used to list the correct number of documents (answer: 34)
- [x] The first result is printed using pprint
- [x] The results are converted to a Pandas DataFrame and displays the first 10 rows
#### Question 3: What are the top 5 establishments with a RatingValue of '5', sorted by lowest hygiene score, nearest to the new restaurant added, "Penang Flavours"?
- [x] A query is correctly performed to find the establishments within 0.01 degree of the "Penang Flavours" restaurant
- [x] The query also limits the results to establishments with a RatingValue of 5
- [x] The query uses the sort() method in PyMongo to sort in ascending order on the hygiene score
- [x] The query uses the limit() method in PyMongo to limit the results to 5
- [x] All five results are printed using pprint
- [x] The results are converted to a Pandas DataFrame and displayed
#### Question 4: How many establishments in each Local Authority area have a hygiene score of 0? Sort the results from highest to lowest, and print out the top ten local authority areas.
- [x] An aggregation pipeline is built to include a match query, group, and sort
- [x] The match query matches documents with a hygiene score of 0
- [x] The group step of the pipeline is grouped on LocalAuthorityName and counts the number of documents
- [x] The sort step of the pipeline sorts the count of the documents in descending order
- [x] The aggregation pipeline is correctly sent to the aggregate() method
- [x] The results from the aggregation query is cast as a list and then saved to a variable
- [x] The first ten results are printed using pprint
- [x] The results are converted to a Pandas DataFrame and displays the first 10 rows
### Deployment, Submission and Comments
- [x] Submit a link to a GitHub repository that’s cloned to your local machine and contains your files
- [x] Use the command line to add your files to the repository
- [x] Include appropriate commit messages in your files
- [x] Be well commented with concise, relevant notes that other developers can understand