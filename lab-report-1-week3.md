# Lab Report 2, Week 3
# Part 1
## 1. Code
```
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;
import java.util.Arrays;

class Handler implements URLHandler {
    ArrayList<String> list = new ArrayList<String>();

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return String.format("Make a search!");
        } else if (url.getPath().contains("/add")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    list.add(parameters[1]);
                    return String.format("%s has been added!", parameters[1]);
                }
        } else if (url.getPath().contains("/search")) {
            String[] parameters = url.getQuery().split("=");
            if (parameters[0].equals("s")) {
                ArrayList<String> returnList = new ArrayList<String>();
                for (int i = 0; i < list.size(); i++) {
                    if (list.get(i).contains(parameters[1])) {
                        returnList.add(list.get(i));
                    }
                }
                return "The values that match your results are: " + Arrays.toString(returnList.toArray());
            } else {
                if (parameters[0].equals("all")) {
                    return "The list of all entries is: " + Arrays.toString(list.toArray());
                }
            }
        }
        return "404 Not Found!";
    }
}


public class SearchEngine {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}
```
## 2. Screenshots
---
![add](server_add.png)
The handleRequest() method is called and the argument to the method is the url including and after the first / which in this case, is add?s=CSE15L. This query is processed and the string "CSE15L" is added to an ArrayList<String> called list that contains all of the strings added. Since this is the first time something was added, the ArrayList became instantiated and the string "CSE15" was added.
---
![all](server_all.png)
The handleRequest)() method was called with the input "/search?all". Since the url contained the key search, the code looked for the query which was all and then because the query was all, returned the string values of all the elements in the list ArrayList. 
---
![search](server_search.png)
The handleRequest() method was called with the argument /search?s=CSE. Since the url contained the keyword search, the query was checked and since the query contained the s=, the string "CSE" was searched for in all strings in the list ArrayList. If the char sequence "CSE" was found in a string in list, that value was appended to a new list, which was converted to a string at the end and returned. 

---
# Part 2
