# Lab Report 2

## ChatServer code
```
import java.io.IOException;
import java.net.URI;

class ChatHandler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    String allChats = "";

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return allChats;
        } else {
            if (url.getPath().contains("/add-message")) {
                String[] parameters = url.getQuery().split("&");
                if(parameters[1].contains("user=")){
                    String userPart[] = parameters[1].split("=");
                    String user = userPart[1];
                    if (parameters[0].contains("s=")) {
                        String messagePart[] = parameters[0].split("=");
                        String message = messagePart[1];
                        allChats += user + ": " + message +"\n";
                        return allChats;
                    }
                }
            }
            return "404 Not Found!";
        }
    }
}

class ChatServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new ChatHandler());
    }
}
```
