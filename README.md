
# h1privdisc - h1 Private Program Disclosed Issues Scraper
Created with all credit to @defparam and their `h1stats` tool: https://github.com/defparam/h1stats

Written in Python 3, this script will perform the following:

 - Request the list of private programs you are a member of from the HackerOne GraphQL API
 - For each, determine whether the program has any (privately) disclosed issues
 - For each issue, dump some details including issue title, bounty paid (if public) and link to the report

Note this is only used for reading disclosed issues from private programs (which are not easily searchable in the Hacktivity feed). Public programs are easily searchable from the Hacktivity feed and as a result this tool does not consider them.

Data Collected:
 - Program Name
 - Program URL
 - Report Title
 - Report ID
 - Report URL
 - Reporter Username
 - Severity
 - Bounty Paid (if disclosed by the reporter)

## Usage

```
python3 h1disc [\<Your HackerOne __Host-session cookie\>]
```

## WARNING (Authenticated Usage)
**THIS SCRIPT HANDLES YOUR H1 SESSION TOKEN WHICH CONTAINS YOUR HACKERONE PRIVATE DATA AND THE PRIVATE DATA OF YOUR HACKERONE PROGRAMS. BECAREFUL WHEN HANDLING THIS TOKEN. THE AUTHORS ARE NOT LIABLE FOR ANY MISUSE OF THIS SCRIPT OR YOUR HACKERONE SESSION TOKEN. PLEASE USE AT YOUR OWN RISK. DO NOT PUBLISH ANY CSVs WITH HACKERONE PRIVATE PROGRAM DATA.**

For authenticated usage It is suggested that you assign your token into a variable once using `export` and pushing the env variable into the script's argument list (as shown in the examples).


## Examples
```
bash> export H1CRED="JGH92kd9...b5e" # HackerOne __Host-session cookie 
bash> python3 h1disc $H1CRED

h1disclosed - get private program disclosed bugs

[+] Using specified session cookie
[+] Please wait... (this may take several minutes)
...
[+] Collecting... (129 programs)
[+] Wrote all data to: h1disc-PRIVATE-2021-6-24.csv
[+] Warning: this data contains private information under NDA, do not publish!
[+] Done!
```


