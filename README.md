
The CSV I downloaded from opendatasoft was messed up in some places, e.g. missing data or incorrectly formatted. I removed all the descriptions because they were a major source of errors. Then I just kept running the copy command below and fixing the errors. When I saw I was making progress, I kept going until the copy was successful. It took me long enough that I think it's worth putting into it's own separate branch to show off. Now that the CSV is actually formatted correctly, it should just work everytime.

Also note to self, don't apply primary key to a table you're importing. I ran into so many duplicate id's due to duplicate records that could have probably been avoided if I saved the constraints for later.

Make a table named "beer" with these columns in this order:

name,id,breweryid,catid,styleid,abv,ibu,srm,upc,filepath,description,adduser,lastmod,style,category,brewer,address,city,state,country,coordinates,website

COPY COMMAND:
copy beer from '/Users/sean/open-beer-database/open-beer-database.csv' delimiters ',' csv;

