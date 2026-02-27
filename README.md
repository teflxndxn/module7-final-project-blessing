# module7-database-project

**Name:** Blessing Aganaga

## Initial Data Source

The data source used for this project was the IMDb dataset in TSV (Tab-Separated Values) format, including:

* name.basics.tsv
* title.basics.tsv
* title.ratings.tsv

## Data Format and Size

The dataset was imported into PostgreSQL as three relational tables:

* names (millions of rows, 6 columns)
* titles (millions of rows, 9 columns)
* ratings (millions of rows, 3 columns)

The files were tab-delimited and required the delimiter E'\t' during import.

## Database Structure

I created a database with three tables:

* names
* titles
* ratings

All tables include text data types and support relational queries.

## Data Dictionary (Example – names table)

* nconst: Unique identifier for a person
* primaryName: Person’s primary name
* birthYear: Year of birth
* deathYear: Year of death
* primaryProfession: Main profession(s)
* knownForTitles: Titles the person is known for

## Challenges Encountered

One challenge I faced was importing large TSV files and setting the correct delimiter for PostgreSQL.
Another challenge was locating the exact clickable page required in the instructions, so I documented my full work in GitHub for accessibility.

## Verification Queries

I verified the data using:

* SELECT * FROM names LIMIT 10;
* SELECT * FROM titles LIMIT 10;
* SELECT * FROM ratings LIMIT 10;

## Join Query (Required)

```sql
SELECT t.primaryTitle, r.averageRating, r.numVotes
FROM titles t
JOIN ratings r ON t.tconst = r.tconst
LIMIT 20;
```

## Group By + Aggregate Query (Required)

```sql
SELECT titleType, COUNT(*) AS total_titles
FROM titles
GROUP BY titleType
ORDER BY total_titles DESC;
```

Screenshots in this repository show:

* Data import
* Table structure
* SELECT verification
* Join and aggregate queries
