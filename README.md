# FILE-HANDLING-UTILITY

**COMPANY** : CODTECH IT SOLUTION

**NAME** : PURVA KISHOR BAKARE

**INTERN ID** : CT08GOM

**DOMAIN** : JAVA PROGRAMMING

**BATCH DURATION** : JANUARY 5th, 2025 to FEBRUVARY 5th, 2025

**MENTOR NAME** : NEELA SANTOSH

**DESCRIPTION OF TASK** : This Java program, named WeatherApiClient.java, is designed to fetch real-time weather data from the OpenWeatherMap API using HTTP requests. It retrieves weather details such as temperature, humidity, and weather conditions for a specified city. The program makes an HTTP request, receives the response in JSON format, parses the JSON data, and then displays relevant information to the user. 

Tools and Resources Used :
1. Java Development Kit (JDK)
The program is written in Java, requiring the Java Development Kit (JDK) to compile and execute.
The JDK provides essential tools like javac (Java Compiler) and the Java Virtual Machine (JVM), which are necessary to run Java applications.

2. Integrated Development Environment (IDE)
Although Java code can be written in any text editor (like Notepad), an IDE such as IntelliJ IDEA, Eclipse, or NetBeans can help in debugging and managing dependencies effectively.
These IDEs also provide syntax highlighting, code completion, and debugging features.

3. OpenWeatherMap API
OpenWeatherMap is an online service that provides real-time weather data.
The API key (a unique identifier) is required to authenticate and access weather data from OpenWeatherMap.
The program makes a request to https://api.openweathermap.org/data/2.5/weather?q=cityname&appid=API_KEY&units=metric to fetch weather details.

4. Internet Connection
Since the program sends HTTP requests to an external API, an active internet connection is required for fetching data.

Libraries Used :
To achieve its functionality, the program uses several built-in and external libraries:

1. java.net (Networking Library)
HttpURLConnection: Establishes an HTTP connection with the OpenWeatherMap API server.
URL: Constructs and handles the API URL dynamically based on user input.

2. java.io (Input/Output Library)
BufferedReader: Reads the response stream from the API efficiently, line by line.
InputStreamReader: Converts the byte stream from the HTTP response into a readable text format.

3. org.json (JSON Parsing Library)
JSONObject: Parses the JSON response and allows easy retrieval of data fields.
JSONArray: Extracts arrays of JSON objects (used for weather conditions).

4. java.util.Scanner (User Input)
Scanner: Reads user input from the console, allowing the user to specify the city name for which they want weather details.

Program Breakdown and Functionality :
Step 1: User Input
The program starts by prompting the user to enter a city name.
The Scanner object reads the input city name from the console.

Step 2: Constructing the API Request
The getWeatherData(city) method dynamically constructs the API URL by appending the user-provided city name and API key.
The HttpURLConnection object is created to establish a connection with the OpenWeatherMap API server.
The request method is set to "GET", meaning the program only retrieves data.
The "Accept" header is set to "application/json" to specify that the response should be in JSON format.

Step 3: Handling the API Response
If the response code is 200 (OK), the program reads the data stream using BufferedReader.
The response is stored in a StringBuilder object to handle multi-line JSON responses efficiently.

Step 4: Parsing JSON Data
The program converts the JSON string into a JSONObject.
It extracts relevant weather details:
City Name: Extracted using jsonObject.getString("name").
Temperature: Retrieved from the "main" object using main.getDouble("temp").
Humidity: Retrieved from "main" as main.getInt("humidity").
Weather Description: Extracted from the "weather" array as jsonObject.getJSONArray("weather").getJSONObject(0).getString("description").

Step 5: Displaying Output
The extracted weather details are printed to the console in a user-friendly format.

Error Handling in the Program :
If the API request fails (e.g., invalid city name or network issues), getWeatherData() returns null.
The program prints an error message:
Error fetching data. Check city name or API key.
The try-catch block ensures that any exceptions (such as network errors or invalid JSON parsing) are caught and printed to the console.

This Java program effectively demonstrates how to handle HTTP requests and parse JSON responses in a simple yet practical way. By integrating OpenWeatherMap's API, it provides real-time weather information to users in a structured format. The use of networking, I/O, JSON parsing, and user input handling makes it a great example of working with external APIs in Java. With further enhancements, it can be turned into a fully functional weather application with better user interaction and more advanced features.
