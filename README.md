# Backend Using Java With Spring
package com.milanwittpohl.playgroundwebbackend;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
package com.milanwittpohl.playgroundwebbackend.controller;

import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RestController;

@RestController
public class HelloWorldController {

    @GetMapping("/sayhello")
    public String sayHelloWorld(){
        return "Hello World!";
    }

}

version: '3'
services:
  playground-web-db:
    image: mongo:4.2.2
    environment:
      MONGO_INITDB_DATABASE: playground-web
    ports:
      - 27017:27017
      then docker-compose -f docker-compose-dev.yml up
package com.milanwittpohl.playgroundwebbackend.data;

public class ToDo {

    private String id;

    private String title;

    private Boolean completed;

}
package com.milanwittpohl.playgroundwebbackend.data;

import org.springframework.data.annotation.Id;

public class ToDo {

    @Id
    private String id;

    private String title;

    private Boolean completed;

    public ToDo(String title, Boolean completed){
        this.title = title;
        this.completed = completed;
    }

    public String getId() {
        return id;
    }

    public String getTitle() {
        return title;
    }

    public Boolean getCompleted() {
        return completed;
    }

}
