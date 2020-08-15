https://developer.atlassian.com/cloud/jira/software/getting-started/

http://go.atlassian.com/cloud-dev

https://davemjones-dev.atlassian.net/

## Getting Setup
1. Create `ngrok-authtoken.txt` in __./devcontainer__.  Save your ngrok personal token in this file.  Do NOT commit this file.


## Starting HTTP and NGROK
1. Start the http server
```
http-server -p 8000
```
2. Make the app available to the internet using ngrok
```
ngrok http 8000
```
3. Edit the app descriptor file, and set the baseUrl property to the ngrok HTTPS URL.