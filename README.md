# Movie Rating User Similarity

Assignment 1 for the Mining Big Datasets Course of AUEB's MSc in Business Analytics.

In this assignment, you will explore the use of Jaccard distance, Min-Hashing, and LSH in the context of user similarity in a movie rating dataset. To fulfill this assignment, you will have to perform the following tasks:

## 1) Import and pre-process the dataset with users
Download the movieLens dataset from Moodle. This dataset includes 100,000 ratings (1-5) from 943 users on 1,682 movies. Each user has rated at least 20 movies. There are 3 files for the dataset:
- `users.txt`: Contains id, age, gender, occupation, and postcode separated by `|`.
- `movies.txt`: Contains id, title (with release year), and some other information not related to the assignment separated by `|`.
- `ratings.txt`: Contains userid, movieid, rating (1-5), and timestamp (tab-separated). For this assignment, only the set of movies that a user has rated will be used, not the ratings.

## 2) Compute the exact Jaccard Similarity of users
Compute the exact Jaccard Similarity for all pairs of users and output only the pairs of users that have a similarity of at least 0.5 (>=50%). For each pair, denote their ids and the similarity score. Also, output the movie titles that the most similar pair of users has seen.

## 3) Compute Similarity Using Min-Hash Signatures
Compute min-hash signatures for each user and use them to evaluate their similarity. Use the following family of hash functions: ha,b(x) = (ax + b) mod R, with a, b random integers in the interval (0, R), and R a large enough prime number. Use 50, 100, and 200 hash functions. For each value, output the pair of users with estimated similarity at least 0.5 and report the number of false positives and false negatives for 5 different runs. Comment on how the number of hash functions affects the false positive and negative figures.

## 4) Locate similar users using LSH Index
Using a set of 200 hash functions, break up the signatures into b bands with r hash functions per band (b * r = 200) and implement Locality Sensitive Hashing (LSH). Use two instances of LSH with different parameters:
- **LSH instance 1:** b = 25, r = 8
- **LSH instance 2:** b = 40, r = 5
Find the pair of users with similarity at least 0.5 and report the number of true pairs returned (true positives) and the number of similarity evaluations performed using the initial representations. Report the averages for 5 different runs.

### Assignment Handout
You should turn in your code, the input file used, the output files produced for the different runs, a file with the average numbers (for tasks 3 and 4), and a report with your observations or a Juputer Notebook containing all above mentioned.
