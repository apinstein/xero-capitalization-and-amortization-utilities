# XERO Amoritization Schedule Importer

## The Problem...

The proper way to account for a loan in XERO is to have a periodic entry that posts to a Bank account, an interest account, and a liability account.

Since XERO doesn't have a built-in feature to create amortization schedules for loans, this becomes a tedious, error-prone, manual process.

## The Solution...

There is a way to automate this entire process in under 5 minutes using XERO's Manual Journal import feature.

## Instructions

1. Open the spreadsheet document
1. Adjust all variables on the `CONFIG` sheet
1. Verify Amortization Table looks accurate on `AMORTIZATION` sheet
1. Export the spreadsheet as CSV
    * use the "Create a file for each table" option
    * this will export 4 csv files, you only will use the file titled `XERO MJ ENTRIES-IMPORT AS XERO MJ.csv`
1. Open the `XERO MJ ENTRIES-IMPORT AS XERO MJ.csv` CSV file and delete blank rows (XERO has 300 row import max)
    * NOTE: if your amortization table has more than 300 rows (299 periods), you'll have to do multiple imports with only 300 rows per import, juggle your rows accordingly
1. Go to XERO > Manual Journals > Import and choose the CSV
    * NOTE: they will be imported as DRAFT MJ's so it's safe and easy to review / delete if they are wrong
1. Verify the importer detected the same number of MJ’s as periods in the loan
1. Complete the import and verify a few sample draft MJ’s
1. Post MJ’s
1. When the payments post into your XERO the reconciliation feauture should see it and suggest it as a MATCH.

Enjoy your perfect and easy amortization bookkeeping!

## Future

I could make a Google Spreadsheet or XSLX of this. I tried exporting and importing, but it messed up all the forumlas and I didn't want to spend the time to fix. 

If you don't have a Mac and want me to make a schedule for me, email me and I'll do it for $10.
