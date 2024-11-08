###Jsonbin Update Content

```java
https://api.jsonbin.io/v3 Copy/b/<BIN_ID> Copy
```

```java
Request Type: PUT
```
headers 

```java
"Content-Type:application/json",
"X-Master-Key:<API_KEY>",
"X-Access-Key:<ACCESS_KEY>",

Data

'{"sample": "Hello World"}'
```

My credibtials

```java
X-Master-Key:   $2a$10$zMRoydoU1WLF0I8ShxsBr.gbP4wdVTCq42IHf92PecrKigdoTPbya
X-Access-Key:   $2a$10$/Bc2iY.Djug6nj53voazWeLhOhNYwfWUafTD6qayMdYgzNonwukuG
```


###Jsonbin Read

```java
url:-  https://api.jsonbin.io/v3/b/<BIN_ID> Copy
```




```java
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.io.OutputStream;
import java.net.HttpURLConnection;
import java.net.URL;

public class HttpURLConnectionExample {

	private static final String USER_AGENT = "Mozilla/5.0";

	private static final String GET_URL = "https://api.jsonbin.io/v3/b/<BIN_ID>";

	private static final String POST_URL = "https://api.jsonbin.io/v3 Copy/b/<BIN_ID>";

	private static final String POST_PARAMS = '{"locLat": "Hello World","locLat": "mani"}'';

	public static void main(String[] args) throws IOException {
		sendGET();
		System.out.println("GET DONE");
		sendPOST();
		System.out.println("POST DONE");
	}

	private static void sendGET() throws IOException {
		URL obj = new URL(GET_URL);
		HttpURLConnection con = (HttpURLConnection) obj.openConnection();
		con.setRequestMethod("GET");
		con.setRequestProperty("User-Agent", USER_AGENT);
		con.setRequestProperty("X-Master-Key", "$2a$10$zMRoydoU1WLF0I8ShxsBr.gbP4wdVTCq42IHf92PecrKigdoTPbya");
		con.setRequestProperty("X-Access-Key", "$2a$10$/Bc2iY.Djug6nj53voazWeLhOhNYwfWUafTD6qayMdYgzNonwukuG");
		int responseCode = con.getResponseCode();
		System.out.println("GET Response Code :: " + responseCode);
		if (responseCode == HttpURLConnection.HTTP_OK) { // success
			BufferedReader in = new BufferedReader(new InputStreamReader(con.getInputStream()));
			String inputLine;
			StringBuffer response = new StringBuffer();

			while ((inputLine = in.readLine()) != null) {
				response.append(inputLine);
			}
			in.close();

			// print result
			System.out.println(response.toString());
		} else {
			System.out.println("GET request did not work.");
		}

	}

	private static void sendPOST() throws IOException {
		URL obj = new URL(POST_URL);
		HttpURLConnection con = (HttpURLConnection) obj.openConnection();
		con.setRequestMethod("POST");
		con.setRequestProperty("User-Agent", USER_AGENT);
		con.setRequestProperty("X-Master-Key", "$2a$10$zMRoydoU1WLF0I8ShxsBr.gbP4wdVTCq42IHf92PecrKigdoTPbya");
		con.setRequestProperty("X-Access-Key", "$2a$10$/Bc2iY.Djug6nj53voazWeLhOhNYwfWUafTD6qayMdYgzNonwukuG");
		con.setRequestProperty("Content-Type","application/json");
		// For POST only - START
		con.setDoOutput(true);
		OutputStream os = con.getOutputStream();
		os.write(POST_PARAMS.getBytes());
		os.flush();
		os.close();
		// For POST only - END

		int responseCode = con.getResponseCode();
		System.out.println("POST Response Code :: " + responseCode);

		if (responseCode == HttpURLConnection.HTTP_OK) { //success
			BufferedReader in = new BufferedReader(new InputStreamReader(con.getInputStream()));
			String inputLine;
			StringBuffer response = new StringBuffer();

			while ((inputLine = in.readLine()) != null) {
				response.append(inputLine);
			}
			in.close();

			// print result
			System.out.println(response.toString());
		} else {
			System.out.println("POST request did not work.");
		}
	}

}

```
