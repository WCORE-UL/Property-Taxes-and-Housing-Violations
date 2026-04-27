# Ingestion Information

## Tax Values

The file intially contained a significant amount of NA values in the total column, values which are useless for our analysis. These are removed simply through a na filter.
Next, we needed to remove the character values that were confusing R. These were commas and $ in the currency values for taxation. 
We grepled through the columns that contained $ and removed them, along with the commas before converting said column to numeric form. 

## Violation Counts

Since the dataset did not have information on how many violations each address had, we had to tally it ourselves by counting the number of times a given address appeared in the data
This went fairly smoothly, with the exception of a single address with 250,000 unique violations. These were chalked up to human data entry error and removed.

## Initial data centralization

In order to prevent overlapping values in the data, we are only going to export the unique values of address,tax class, total tax payment, city,  zip code, state, and violation count.
This allows us to keep all of the variables we want to use in tableau without fear of repeating data. 

## Geocoding

The next section is more specific to our data, and relies on a tool you may not be familiar with. Our datasets have a column for longitude and latitude.
In both datasets,however, the columns are empty. To map our values onto a tableau visualization, we need these coordinates. The tool we stumbled upon is the [US census geocoder](https://geocoding.geo.census.gov/geocoder/locations/addressbatch?form)
This allowed us to input the addresses from our set after seperating it into manageable pieces. The tool then outputted usable coordinates for our dataset. 

## Final Data centralization

With both pieces of our first workable dataset complete, they are merged and exported as a csv. 

## Item dataset

The second dataset relies on the work we did previously, and so is much simpler. It is merely a collection of columns from our cleaned dataset, before we kept only the unqiue rows.
These variables are the type of violation, the tax class, the zip code, the date of violation filing, the data of violation completion, and the address. We then turn it into a csv and export
