google-spreadsheets-to-r-dataframe
==================================

Demonstration of how to import a Google Spreadsheet into an R data.frame.

Most of this information comes from the excellent [RGoogleDocs tutorial](http://www.omegahat.org/RGoogleDocs/run.html).

First, install the dependencies for [RGoogleDocs](http://www.omegahat.org/RGoogleDocs/), if you don't already have them.

    > install.packages('RCurl')
    > install.packages('XML')

Next, download RGoogleDocs

    $ wget http://www.omegahat.org/RGoogleDocs/RGoogleDocs_0.7-0.tar.gz

Then, install RGoogleDocs

    > install.packages(<path_to_RGoogleDocs_tarball>, repos = NULL, type="source")
    > library(RGoogleDocs)

Finally, use the library.

Get a connection object:

    > sheets.con = getGoogleDocsConnection(getGoogleAuth(<username>, <password>, service = "wise"))
    
Get handles for your spreadsheets and workshees:

    > spreadsheets = getDocs(sheets.con)
    > worksheets = getWorksheets(spreadsheets[[<spreadsheet_name>]], sheets.con)
    
Import a worksheet as a data.frame:

    > worksheet_as_df = sheetAsMatrix(worksheets[[<worksheet_name>]], header = TRUE, as.data.frame = TRUE, trim = TRUE)

Create a new worksheet:

    > sh = addWorksheet(spreadsheets[[<spreadsheet_name>]], sheets.con, title="test")
    
I have not yet been able to get writes to spreadsheet cells working.
