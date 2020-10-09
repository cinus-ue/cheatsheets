# CURL CHEAT SHEET

## OPTIONS
```
-o <file>    # --output: write to file
-u user:pass # --user: Authentication
-v           # --verbose
-vv          # Even more verbose
-s           # --silent
-i           # --include: Include the HTTP-header in the output
-I           # --head: headers only
```

## REQUEST
```
-X POST          # --request
-L               # follow link if page redirects
```
## DATA
```
-d 'data'    # --data: HTTP post data, URL encoded (eg, status="Hello")
-d @file     # --data via file
-G           # --get: send -d data via get
```

## HEADERS
```
-A <str>         # --user-agent
-b name=val      # --cookie
-b FILE          # --cookie
-H "X-Foo: y"    # --header
--compressed     # use deflate/gzip
```

## SSL
```
    --cacert <file>
    --capath <dir>
-E, --cert <cert>     # --cert: Client cert file
    --cert-type       # der/pem/eng
-k, --insecure        # for self-signed certs
```

## EXAMPLES
```
# Post data:
curl -d "name=username&password=123456" <URL>
# Curl post send json	 
curl <URL> -H "content-type: application/json" -d "{ \"woof\": \"bark\"}"
# Auth/data:
curl -u user:pass -d status="Hello" http://twitter.com/statuses/update.xml
# multipart file upload
curl -v -include --form key1=value1 --form upload=@localfilename URL
# Use Curl to Check if a remote resource is available
# details: https://matthewsetter.com/check-if-file-is-available-with-curl/
curl -o /dev/null --silent -Iw "%{http_code}" https://example.com/my.remote.tarball.gz

GET/HEAD
# Curl head request	 
curl -I https://www.google.com
# Curl head request with verbose	 
curl -v -I https://www.google.com
# Curl with explicit http method	 
curl -X GET https://www.google.com
# Curl without http proxy	 
curl --noproxy 127.0.0.1 http://www.stackoverflow.com
# Curl has no timeout by default	
curl --connect-timeout 10 -I -k https://www.google.com
# Curl get with extra headers	
curl --verbose --header "Host: www.mytest.com:8182" www.google.com
# Curl get response with headers	 
curl -k -v https://www.google.com

Advanced
# Get my public ip	
curl -L -s http://ipecho.net/plain, curl -L -s http://whatismijnip.nl
# Curl with credential	 
curl -u $username:$password http://repo.dennyzhang.com/README.txt
# Curl upload	 
curl -v -F key1=value1 -F upload=@localfilename <URL>
# Curl with http2	 
curl -k -v --http2 https://www.google.com/
# Curl ftp upload	 
curl -T cryptopp552.zip -u test:test ftp://10.32.99.187/
# Curl ftp download	 
curl -u test:test ftp://10.32.99.187/cryptopp552.zip -o cryptopp552.zip
# Curl upload with credential	 
curl -v -u admin:admin123 --upload-file package1.zip http://mysever:8081/dir/package1.zip
```