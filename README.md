# Open-Redirection-Scanner
a python tool used to scan for Open redirection vulnerability

### How to Use:

what makes this tool diffrent is that you can use it for auth-based scanning because you can provide a cookie if u want, example:

python openredir.py -u test.com -c "Cookie=test"

Also this tool supports 2 types of scanning:

1- Url based

2-parameter based

the tool uses different wordlists for each type of scans

example for using parameter based:

python openredir.py -u test.com/file.php?redirc= -p test.com

you must specify a domain when using parameter based scanning, the tool will use the domain name while scanning




usage: openredirectionscanner.py [-h] [-u URL] [-p domain.com] [-f FILEPATH]
                                 [-c Cookie=value] [-v]

Open Redirection Scanner
arguments:

  -h, --help       show this help message and exit
  
  -u (URL)           Url to test
  
  -p (domain.com)    Parameter based scan (Uses a diffrent payload list),you
                   must Specify a domain to be used in the payloads
  -f (FILEPATH)      load URLs from a file (Optional)
  
  -c (Cookie=value)  scan with a specific Cookie (Optional)
  
  -v               Verbose mode (Optional)
  
=================================================================================================

# Open Redirect Payloads
Payloads from BB reports for Open Redirect

***

### Replace www.whitelisteddomain.tld with a specific whitelisted domain in your test case

To do this simply modify the WHITELISTEDDOMAIN with value www.test.com to your test case URL.

`WHITELISTEDDOMAIN="www.test.com" && sed 's/www.whitelisteddomain.tld/'"$WHITELISTEDDOMAIN"'/' Open-Redirect-payloads.txt > Open-Redirect-payloads-burp-"$WHITELISTEDDOMAIN".tmp && sed 's/@www.whitelisteddomain.tld/@'"$WHITELISTEDDOMAIN"'/' Open-Redirect-payloads-burp-"$WHITELISTEDDOMAIN".tmp > Open-Redirect-payloads-burp-"$WHITELISTEDDOMAIN".txt && echo "$WHITELISTEDDOMAIN" | awk -F. '{if ($1 =="www") print "//not"$2"."$NF"/"; else print "//not"$1"."$NF"/";}' >> Open-Redirect-payloads-burp-"$WHITELISTEDDOMAIN".txt && echo "$WHITELISTEDDOMAIN" | awk -F. '{if ($1 =="www") print "http://not"$2"."$NF"/"; else print "http://not"$1"."$NF"/";}' >> Open-Redirect-payloads-burp-"$WHITELISTEDDOMAIN".txt && echo "$WHITELISTEDDOMAIN" | awk -F. '{print "http://"$0"."$NF"/"}' >> Open-Redirect-payloads-burp-"$WHITELISTEDDOMAIN".txt && rm -f Open-Redirect-payloads-burp-"$WHITELISTEDDOMAIN".tmp && echo -e "\nDone. Filename: $(pwd)/Open-Redirect-payloads-burp-"$WHITELISTEDDOMAIN".txt"`

***  

===============================================================================================
# redirect.py
UPDATED!  we add awesomes payloads list by https://github.com/cujanovic/Open-Redirect-Payloads

Open redirect Scanner by Ak1t4 - https://hackerone.com/ak1t4
(contributor(s): @sxcurity)

Use ./redirect.py [subdomains.file] [redirect-payload]

Example ./redirect.py uber.list '//yahoo.com/%2F..'


UPDATE:  ((Now is not necessarily indicate the payload we replace we an entire payloads list)

this is pretty awesome, now you can run 1 only command who search all subdomains in 1 file and inject unlimited Payloads from payloads.list

Use example:

skynet-localhost:Sublist3r ak1t4_hax0r$  while read -r line;do python redirect.py.1 uber.list $line;done < payloads.list 


Here is a new video PoC with the unlimited payloads -> https://youtu.be/hCWxb88do2I

This is the old video PoC  -> https://www.youtube.com/watch?v=esMBWSO4RUU

Enjoy!

@ak1t4


