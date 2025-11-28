# SpringAI-trip-and-image-generator
Project for integration of Spring AI in Spring Boot app asking question for Trips or generate images.

### Add OpenAI token
For this application to work, you will need to provide your own OpenAI API key which is defined in `src\main\resources\application.properties`:

```
spring.ai.openai.api-key=<YOUR_API_KEY>
```

### Running the application
To run the app first built it using maven:

```
mvn clean install
```

Then you can run `SpringAI-trip-and-image-generator` as regular Spring Boot app.

### Accessing REST API
When the application starts, it can be interacted by using REST endpoints defined in `AiController`. the app starts at `localhost:8080`

#### Simple text prompts
To ask questions you can call `ask-ai` providing your prompt, such as:

```
http://localhost:8080/ask-ai?prompt=how%20are%20you
```

#### Templated prompts
Endpoint `city-guide` uses parametrized predefined query, where placeholders are replaced with user provided parameters.
Based on city and interest provided, you will get tips what to do in that city as a tourist based on your interest.

```
http://localhost:8080/city-guide?city=Prague&interest=history
```

#### Generating images
Image generation can be accessed via `http://localhost:8080/generate-image?prompt=xxx`, where you can provide prompt defining what image should be generated.

For example:

```
http://localhost:8080/generate-image?prompt=cute%20cat
```