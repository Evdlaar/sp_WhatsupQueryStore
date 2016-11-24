# sp_WhatsupQueryStore
[![licence badge]][licence]
[![stars badge]][stars]
[![forks badge]][forks]
[![issues badge]][issues]

[licence badge]:https://img.shields.io/badge/license-MIT-blue.svg
[stars badge]:https://img.shields.io/github/stars/Evdlaar/sp_WhatsupQueryStore.svg
[forks badge]:https://img.shields.io/github/forks/Evdlaar/sp_WhatsupQueryStore.svg
[issues badge]:https://img.shields.io/github/issues/Evdlaar/sp_WhatsupQueryStore.svg

[licence]:https://github.com/Evdlaar/sp_WhatsupQueryStore/blob/master/LICENSE.md
[stars]:https://github.com/Evdlaar/sp_WhatsupQueryStore/stargazers
[forks]:https://github.com/Evdlaar/sp_WhatsupQueryStore/network
[issues]:https://github.com/Evdlaar/sp_WhatsupQueryStore/issues

The sp_WhatsupQueryStore Stored Procedure is a Microsoft SQL Server Stored Procedure that retrieves all kinds of information from the Query Store.
By running the script on this website the sp_WhatsupQueryStore Stored Procedure gets installed in the "master" database of your SQL Server Instance.

After installation you can run the Stored Procedure as follows:

**EXEC sp_WhatsupQueryStore @dbname, @timewindow, @topqueries**

- @dbname : specify the database name that has Query Store data you want to analyze.
- @timewindow : specify the time in hours the data aggragation has to go back. For instance, a '1' will return the top n queries executed in the last hour.
- @topqueries : specify how many queries you want to return in the results. For instance, a '10' will return the top 10 queries.

The sp_WhatsupQueryStore Stored Procedure is developed and maintained by Enrico van de Laar (@evdlaar).


## License
[MIT](/license.md)