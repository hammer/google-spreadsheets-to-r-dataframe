google-spreadsheets-to-r-dataframe
==================================

Demonstration of how to import a Google Spreadsheet into an R data.frame

First, install the dependencies for [RGoogleDocs](http://www.omegahat.org/RGoogleDocs/), if you don't already have them.

    > install.packages('RCurl')
    > install.packages('XML')

Next, download RGoogleDocs

    $ wget http://www.omegahat.org/RGoogleDocs/RGoogleDocs_0.7-0.tar.gz

Then, install RGoogleDocs

    > install.packages(<path_to_RGoogleDocs_tarball>, repos = NULL, type="source")
    > library(RGoogleDocs)

Finally, use the library.

    > sheets.con = getGoogleDocsConnection(getGoogleAuth(<username>, <password>, service = "wise"))
    > spreadsheets = getDocs(sheets.con)
    > worksheets = getWorksheets(a[[<spreadsheet_name>]], sheets.con)
    > worksheet_as_df = sheetAsMatrix(worksheets[[<worksheet_name>]], header = TRUE, as.data.frame = TRUE, trim = TRUE)
