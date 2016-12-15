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

The sp_WhatsupQueryStore Stored Procedure is a SQL Server Stored Procedure that retrieves all kinds of information from the Query Store. 
By running the script on this website the sp_WhatsupQueryStore Stored Procedure gets installed in the "master" database of your SQL Server Instance.

After installation you can run the Stored Procedure as follows:

EXEC sp_WhatsupQueryStore 
    @dbname, 
	@timewindow, 
	@topqueries,
	@return_all,
	@return_store_config,
	@return_forced_plans,
	@return_multiple_plans,
	@return_top_executed,
	@return_top_duration,
	@return_top_cpu,
	@return_top_log_read,
	@return_top_log_write,
	@return_top_phys_read
	@show_query_hints
	
You must specify at least one @return parameter which is depended on the information you are interested in retrieving. 
If you want to return all information windows use the @return_all = 1 parameter. 
Returning all the information windows can take some time depending on the size and activity of your Query Store.

For some examples to get you started, check out the "[Examples](https://github.com/Evdlaar/sp_WhatsupQueryStore/wiki/Examples)" page!

- @dbname : specify the database name that has Query Store data you want to analyze.
- @timewindow : specify the time in hours the data aggragation has to go back. For instance, a '1' will return the top n queries executed in the last hour. (optional)
- @topqueries : specify how many queries you want to return in the results. For instance, a '10' will return the top 10 queries. (optional)
- @show_query_hints: Adds an additional column to the “Multiple plans” information window that shows the SQL query you can run to force a specific execution plan for the selected query. Default is ‘0’. (optional)
- @return_all: returns all the information windows described below if set to ‘1’. Default is ‘0’. (optional)
- @return_store_config : show or hide the Query Store configuration window. A '0' indicates not returning the window, a '1' returns the window. '1' is set as the default. (optional)
- @return_forced_plans : show or hide the Forced Query Store plans window. A '0' indicates not returning the window, a '1' returns the window. '1' is set as the default. (optional)
- @return_multiple_plans : show or hide queries that have more than one execution plan generated in the selected time window. A '0' indicates not returning the window, a '1' returns the window. '0' is set as the default. (optional)
- @return_top_executed : show or hide the Top queries based on the amount of executions. A '0' indicates not returning the window, a '1' returns the window. '0' is set as the default. (optional)
- @return_top_duration : show or hide the Top queries based on avg. duration window.  A '0' indicates not returning the window, a '1' returns the window. '1' is set as the default. (optional)
- @return_top_cpu : show or hide the Top queries based on avg. CPU time window. A '0' indicates not returning the window, a '1' returns the window. '1' is set as the default. (optional)
- @return_top_log_read : show or hide the Top queries based on avg. logical read IO. A '0' indicates not returning the window, a '1' returns the window. '1' is set as the default. (optional)
- @return_top_log_write : show or hide the Top queries based on avg. logical write IO. A '0' indicates not returning the window, a '1' returns the window. '1' is set as the default. (optional)
- @return_top_phys_read : show or hide the Top queries based on avg. physical read IO. A '0' indicates not returning the window, a '1' returns the window. '1' is set as the default. (optional)

The sp_WhatsupQueryStore Stored Procedure is developed and maintained by Enrico van de Laar (Twitter: @evdlaar).


## License
[MIT](/license.md)