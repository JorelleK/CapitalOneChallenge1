# Airbnb Listings Optimization

Check out the working demo: http://jorellek.github.io/CapitalOneChallenge1/

## Services

#### 1. Price estimation
   Use csv file to calculate the price estimation given latitude and longitude. Then, add a link on html file to read csv file.

#### 2. Maps
use iframe to embed maps to website

#### 3. Bookings Optimization
           Use csv file to display Price depending on location. The user can sort the price.
           
 ##### Script to read csv file in html
``` html
<script>
  CsvToHtmlTable.init({
    csv_path: 'data/Health Clinics in Chicago.csv', 
    element: 'table-container', 
    allow_download: true,
    csv_options: {separator: ',', delimiter: '"'},
    datatables_options: {"paging": false}
  });
</script>
```

* `csv_path` Path to your CSV file.
* `element` The HTML element to render your table to. Defaults to `table-container`
* `allow_download` if true, shows a link to download the CSV file. Defaults to `false`
* `csv_options` jQuery CSV configuration. Use this if you want to use a custom `delimiter` or `separator` in your input file. See [their documentation](https://code.google.com/p/jquery-csv/wiki/API#$.csv.toArrays%28%29).
* `datatables_options` DataTables configuration. See [their documentation](http://datatables.net/reference/option/).
* `custom_formatting` **New!** A list of column indexes and custom functions to format your data (see below)

##### Reviews Score

Use Splunk to produce a dashboard with some graphs visualization and link it to the html page.

##### formatting 

    Use CSS and Javscript to format the webpage

``` html
<script>

  //my custom function that creates a hyperlink
  function format_link(link){
    if (link)
      return "<a href='" + link + "' target='_blank'>" + link + "</a>";
    else
      return "";
  }

  //initializing the table
  CsvToHtmlTable.init({
    csv_path: 'data/review.csv', 
    element: 'table-container', 
    allow_download: true,
    csv_options: {separator: ',', delimiter: '"'},
    datatables_options: {"paging": false},
    custom_formatting: [[4, format_link]] //execute the function on the 4th column of every row
  });
</script>
```

#### 5. Deploy it

**GitHub pages** Host it on GitHub pages for free! 
Then navigate to http://jorellek.github.io/CapitalOneChallenge1/

**Web server** This project should work on any web server. 

## Dependencies

* [Bootstrap](http://getbootstrap.com/) - Responsive HTML, CSS and Javascript framework
* [jQuery](https://jquery.com/) - a fast, small, and feature-rich JavaScript library
* [jQuery CSV](https://github.com/evanplaice/jquery-csv/) - Parse CSV (Comma Separated Values) to Javascript arrays or dictionaries.

## Copyright

Copyright (c) 2017 Jorelle Kebeto. Released (https://github.com/jorellek/CapitalOneChallenge1/blob/master/LICENSE).
