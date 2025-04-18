### CMD
- docker run --rm <image-name> echo "Hello this is me"
- docker run --rm cmd-example sh -c "apk add curl && curl https://www.google.com"
### CMD IS EASILY DISTRACTED 
 new comes old is disapperd

## ENTRY POINT means ENTRYPOINT ["echo" , "hello" ]
  old + new 
- docker run --rm entrypoint-example "hello from the terminal"
- docker run --rm entrypoint-example echo "hello from the terminal"  ===> echo will be in output
- docker run --rm --entrypoint "echo" entrypoint-example "hello from terminal"  ===> old out new in



 
