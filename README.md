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
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0
         https://maven.apache.org/xsd/maven-4.0.0.xsd">

	<modelVersion>4.0.0</modelVersion>

	<parent>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-starter-parent</artifactId>
		<version>4.1.1</version>
		<relativePath/>
	</parent>

	<groupId>com.example</groupId>
	<artifactId>spring-mvc</artifactId>
	<version>0.0.1-SNAPSHOT</version>

	<properties>
		<java.version>21</java.version>
	</properties>

	<dependencies>

		<!-- Spring MVC -->
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-web</artifactId>
		</dependency>

		<!-- Thymeleaf -->
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-thymeleaf</artifactId>
		</dependency>

		<!-- Testing -->
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-test</artifactId>
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

### SpringMvcApplication.java (Main Class):

```
package com.example.spring_mvc;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class SpringMvcApplication {

	public static void main(String[] args) {
		SpringApplication.run(SpringMvcApplication.class, args);
	}

}
```

### HomeController.java (Controller):
```
package com.example.spring_mvc;

import org.springframework.stereotype.Controller;
import org.springframework.ui.Model;
import org.springframework.web.bind.annotation.GetMapping;

@Controller
public class HomeController {

    @GetMapping("/")
    public String homePage(Model model) {

        model.addAttribute("message",
                "Welcome to Spring Boot MVC!");

        return "index";
    }
}
```

### index.html (View – inside src/main/resources/templates/):
```
<!DOCTYPE html>
<html xmlns:th="http://www.thymeleaf.org">
<head>
    <title>Spring MVC</title>
</head>
<body>

<h1 th:text="${message}">
    Default Message
</h1>

</body>
</html>
```

### application.properties:
```
server.port=8081
```

 ### Output:
<img width="1535" height="817" alt="image" src="https://github.com/user-attachments/assets/c100e1a3-4962-4c1b-b6bb-24412a2d65eb" />


 ### Result:
 Hence Simple Spring Boot MVC is successfully created



