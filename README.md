# Exp_2_Simple-Spring-Boot-MVC-Application

## AIM:
To develop a Simple Spring Boot MVC (Model-View-Controller) Application that uses a Controller to handle HTTP requests, a Model to pass data, and a View (Thymeleaf) to render dynamic HTML pages.

## ALGORITHM:
Create a New Spring Boot Project:

Use Spring Initializr

Add dependencies:

Spring Web

Thymeleaf

Set Up Project Structure:

Create the main class annotated with @SpringBootApplication

Create a Controller class using @Controller

Add HTML templates under src/main/resources/templates

Create a Controller:

Define a method to handle HTTP GET requests using @GetMapping

Return a view name (HTML page name) from the controller

Pass data to the view using Model object

Create a Model (Optional):

Define a simple POJO class if you need to pass structured data to the view

Create View Pages (HTML using Thymeleaf):

Create an HTML file inside the templates folder

Use Thymeleaf syntax (e.g., ${name}) to render dynamic content

Run the Application:

Run the Spring Boot application from your IDE or command line

Access the Application:

Open a browser and navigate to http://localhost:8080/
## PROGRAM
spring-mvc-demo/
├── src/
│   └── main/
│       ├── java/
│       │   └── com.example.mvc/
│       │       ├── MvcApplication.java
│       │       └── HomeController.java
│       └── resources/
│           ├── templates/
│           │   └── index.html
│           └── application.properties
├── pom.xml

### pom.xml :
```
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd">
	<modelVersion>4.0.0</modelVersion>
	<parent>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-starter-parent</artifactId>
		<version>4.0.6</version>
		<relativePath/> <!-- lookup parent from repository -->
	</parent>
	<groupId>com.example</groupId>
	<artifactId>demo</artifactId>
	<version>0.0.1-SNAPSHOT</version>
	<name/>
	<description/>
	<url/>
	<licenses>
		<license/>
	</licenses>
	<developers>
		<developer/>
	</developers>
	<scm>
		<connection/>
		<developerConnection/>
		<tag/>
		<url/>
	</scm>
	<properties>
		<java.version>21</java.version>
	</properties>
	<dependencies>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-webmvc</artifactId>
		</dependency>

		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-webmvc-test</artifactId>
			<scope>test</scope>
		</dependency>
	</dependencies>

	<build>
		<plugins>
			<plugin>
				<groupId>org.springframework.boot</groupId>
				<artifactId>spring-boot-maven-plugin</artifactId>
			</plugin>
		</plugins>
	</build>

</project>
```

### MvcApplication.java (Main Class):
```
package com.example.demo;

import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RestController;

@RestController
public class demo2 {
    @GetMapping("/")
    public String test1()
    {
        return "Hello world";
    }
}
```

### HomeController.java (Controller):
```
ppackage com.example.MVC_Application;


import org.springframework.stereotype.Controller;
import org.springframework.ui.Model;
import org.springframework.web.bind.annotation.GetMapping;

@Controller
public class HomeController {

    @GetMapping("/")
    public String homePage(Model model) {
        System.out.println("Controller is called"); // DEBUG
        model.addAttribute("message", "Welcome To ThymeLeaf");
        return "index";
    }
}
```

### Script.js
```
function showMessge() {
    alert("Hello nanba! 👋 Welcome to Thymeleaf Page!");
}

function changeText() {
    document.getElementById("demo").innerHTML = "Text Changed Successfully!";
}
```

### Style.css
```
/* Reset some default styles */
body {
    font-family: "Times New Roman", sans-serif;
    background: linear-gradient(to right, #4facfe, #00f2fe);
    text-align: center;
    padding: 50px;
    color: #333;
}

/* Heading */
h1 {
    color: white;
    margin-top: 40px;
}

/* Paragraph */
#demo {
    font-size: 24px;
    font-weight: bold;
    margin-bottom: 20px;
    color: #222;
}

/* Buttons */
button {
    padding: 10px 20px;
    margin: 10px;
    font-family: "Times New Roman", sans-serif;
    font-size: 16px;
    font-weight: bold;
    border: none;
    border-radius: 8px;
    cursor: pointer;
    transition: 0.3s;
}

/* First button */
button:nth-child(2) {
    background-color: #0000FF;
    color: white;
}

/* Second button */
button:nth-child(3) {
    background-color: #28a745;
    color: white;
}

/* Hover effect */
button:hover {
    transform: scale(1.1);
    opacity: 0.9;
}
```

### index.html (View – inside src/main/resources/templates/):
```
<!DOCTYPE html>
<html>
<head>
    <title>Home</title>
    <link rel="stylesheet" th:href="@{style.css}">
</head>
<body>
<p id ="demo">Original Text</p>
<button onclick="showMessage()">Click Me</button>

<button onclick="changeText()">Change</button>

<script th:src="@{script.js}"></script>
<h1>Welcome to Java Application</h1>
<h1>JAVA WEB APPLICATION DEVELOPMENT</h1>
</body>
</html>
```
### application.properties:
``` server.port=8080 ```

### Output
<img width="1600" height="772" alt="WhatsApp Image 2026-05-13 at 11 03 19 AM" src="https://github.com/user-attachments/assets/79f6d283-7565-4633-b77d-2a90217b6396" />

### Result
A simple Spring Boot MVC application was successfully developed and executed, displaying dynamic content using Thymeleaf with interactive UI functionality.
