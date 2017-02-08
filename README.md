```javascript
function sendToApiAi(sender,text){
    var request = api.textRequest(text, {
        sessionId: sender
    });
    request.on('response', function(response) {
        sendTextMessage(sender, response.result.fulfillment.messages[0].speech)
    });

    request.on('error', function(error) {
        console.log(error);
    });

    request.end();
}
```
