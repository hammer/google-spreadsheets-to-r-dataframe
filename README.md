google-spreadsheets-to-r-dataframe
==================================

Demonstration of how to import a Google Spreadsheet into an R data.frame

```R
install.packages('RCurl')
install.packages('XML')
```

Then, download [RGoogleDocs](http://www.omegahat.org/RGoogleDocs/).

```R
install.packages(path_to_RGoogleDocs_tarball, repos = NULL, type="source")
library(RGoogleDocs)
```

Finally, use the library.

```R
sheets.con = getGoogleDocsConnection(getGoogleAuth(<username>, <password>, service = "wise"))
spreadsheets = getDocs(sheets.con)
worksheets = getWorksheets(a[[<spreadsheet_name>]], sheets.con)
worksheet_as_df = sheetAsMatrix(worksheets[[<worksheet_name>]], header = TRUE, as.data.frame = TRUE, trim = TRUE)
```
