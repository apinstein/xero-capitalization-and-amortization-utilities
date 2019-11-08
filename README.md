# XERO Amoritization Schedule Importer

## The Problem

The proper way to account for a loan in XERO is to have a periodic entry that posts to a Bank account, an interest account, and a liability account.

Unfortunately, XERO doesn't have a built-in feature to create amortization schedules for loans, making it a tedious, error-prone, manual process to properly enter a loan in XERO.

## The Solution

Fortunately, XERO allows importing MJ's via CSV. This allows us to automate this entire process with less than 5 minutes of work.

## Instructions

1. Open the spreadsheet document
1. Adjust all variables on the `CONFIG` sheet
1. Verify Amortization Table looks accurate on `AMORTIZATION` sheet
1. Export the spreadsheet as CSV
    * use the "Create a file for each table" option
    * this will export 4 csv files, you only will use the file titled `XERO MJ ENTRIES-IMPORT AS XERO MJ.csv`
1. Open the `XERO MJ ENTRIES-IMPORT AS XERO MJ.csv` CSV file 
    * delete blank rows (XERO has 300 row import max)
      * NOTE: as of 8/16/2019 XERO seems to automatically prune empty rows so this step likely isn't needed anymore.
    * NOTE: if your amortization table has more than 300 rows (299 periods), you'll have to do multiple imports with only 300 rows per import, juggle your rows accordingly
1. Go to XERO > Manual Journals > Import and choose the CSV
    * NOTE: they will be imported as DRAFT MJ's so it's safe and easy to review / delete if they are wrong
1. Verify the importer detected the same number of MJ’s as periods in the loan
1. Complete the import and verify a few sample draft MJ’s
1. Post MJ’s
1. When the payments post into your XERO the reconciliation feauture should see it and suggest it as a MATCH.

Enjoy your perfect and easy amortization bookkeeping!

## Limitations

Xero assumes all transactions are CASH AND ACCRUAL by default. You can chance this by twiddling the 'show journal on cash basis' checkbox (uncheck to remove from cash basis). For loan amortizations this is actually perfect typically. You can edit each MJ however to accrual-only if you want after importing since there is no way to specify this via import. Vote on this feature here: https://community.xero.com/business/discussion/37725075/

## TODO / Future

I could make a Google Spreadsheet or XSLX of this. I tried exporting and importing, but it messed up all the forumlas and I didn't want to spend the time to fix. 

If you don't have a Mac and want me to make a schedule for you, email me and I'll do it for $10.

I also intend to provide a similar tool for generation small amortization / capitalization schedules for things like Deferred Revenue, Prepaid Services, etc.
