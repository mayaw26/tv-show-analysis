# TV Show Analysis

SQL and visualization project exploring TV show longevity.

https://data.imdb.com/non-commercial-datasets/

## Database Schema

The project uses IMDb's non-commercial datasets, which were imported into a relational SQLite database. The database consists of seven tables:

| Table | Description |
|---|---|
| `people` | Contains information about actors, directors, writers, and other individuals, including names, birth and death years, professions, and titles they are known for. |
| `titles` | Contains information about IMDb titles, including title type, name, release years, runtime, and genres. |
| `title_akas` | Contains alternative and localized titles, including regional and language variations. |
| `crew` | Identifies the directors and writers associated with each title. |
| `episodes` | Connects individual TV episodes to their parent series and identifies season and episode numbers. |
| `principals` | Contains the principal cast and crew associated with each title, including their role or category. |
| `ratings` | Contains the average IMDb rating and number of votes for each title. |

Most tables are connected using IMDb's unique title identifier, `tconst`. Individuals are identified using `nconst`, which connects cast and crew records to the `people` table.

For television episodes, `episodes.tconst` identifies the individual episode, while `episodes.parent_tconst` identifies the series to which the episode belongs.
