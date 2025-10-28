# 🌤️ Weather App

A Spring Boot web application that displays real-time weather information for any city using the OpenWeatherMap API.

## 📋 Features

-  Search weather by city name
-  Display current temperature (Celsius)
-  Show weather description (clear sky, cloudy, rainy, etc.)
-  Display humidity percentage
-  Show wind speed
-  Display weather icons
-  Show country code

##  Technologies Used

- **Java 17** - Programming language
- **Spring Boot 3.x** - Backend framework
- **Spring MVC** - Web framework
- **Thymeleaf** - Template engine for HTML
- **RestTemplate** - HTTP client for API calls
- **OpenWeatherMap API** - Weather data provider
- **Maven** - Build and dependency management tool

##  Prerequisites

Before running this application, make sure you have:

-  Java JDK 11 or higher installed
-  Maven 3.6+ installed
-  An OpenWeatherMap API key (free tier available)
-  Internet connection

## 🚀 Setup Instructions

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/adelekeemmanuel/Weather-App.git
cd Weather-App
```

### 2️⃣ Get an API Key

1. Visit [OpenWeatherMap](https://openweathermap.org/api)
2. Click **Sign Up** and create a free account
3. Verify your email address
4. Go to **API Keys** section in your dashboard
5. Copy your API key (it looks like: `abc123def456ghi789`)

### 3️⃣ Configure the Application

Open `src/main/resources/application.properties` and replace the placeholder:

**Change this:**
```properties
api.key=YOUR_API_KEY_HERE
```

**To this (with your actual key):**
```properties
api.key=abc123def456ghi789
```

💡 **Important:** Never share this file or push it to GitHub with your real API key!

### 4️⃣ Run the Application

#### Using Maven Command Line:
```bash
mvn spring-boot:run
```

#### Using IntelliJ IDEA:
1. Locate `WeatherAppApplication.java` (main class)
2. Right-click on the file
3. Select **Run 'WeatherAppApplication'**

#### Using Command Line (after building):
```bash
mvn clean package
java -jar target/Weather-App-0.0.1-SNAPSHOT.jar
```

### 5️⃣ Access the Application

Open your web browser and go to:
```
http://localhost:8080/abc
```

## 🎯 How to Use

1. 🚀 Launch the application
2. 🌐 Open `http://localhost:8080/abc` in your browser
3. 📝 Enter a city name (e.g., "London", "New York", "Tokyo")
4. 🖱️ Click "Get Weather" or press Enter
5. 📊 View the current weather information displayed

## 📁 Project Structure
```
Weather-App/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/weather/Weather_App/
│   │   │       ├── WeatherAppApplication.java      # Main application class
│   │   │       ├── controller/
│   │   │       │   └── WeatherController.java      # Handles web requests
│   │   │       └── model/
│   │   │           └── WeatherResponse.java        # API response model
│   │   └── resources/
│   │       ├── application.properties              # Configuration (NOT in Git)
│   │       ├── static/
│   │       │   ├── css/                           # CSS stylesheets
│   │       │   │   ├── index.css
│   │       │   │   └── weather.css
│   │       │   └── images/                        # Image assets
│   │       └── templates/
│   │           ├── index.html                     # Search page
│   │           └── weather.html                   # Results page
│   └── test/                                      # Test files
├── target/                                        # Compiled files (ignored)
├── .gitignore                                     # Git ignore rules
├── pom.xml                                        # Maven configuration
└── README.md                                      # This file
```

## 🔧 Configuration

The application uses the following configuration (in `application.properties`):
```properties
# API Configuration
api.key=YOUR_API_KEY_HERE

# Server Configuration
server.port=8080

# Application Name
spring.application.name=Weather-App
```

### Customization Options:

**Change the port:**
```properties
server.port=9090  # Now runs on http://localhost:9090
```

**Use environment variable for API key:**
```properties
api.key=${WEATHER_API_KEY:default_key}
```

## 🌐 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/abc` | Home page with search form |
| GET | `/weather?city={cityName}` | Get weather for specified city |

**Example:**
```
http://localhost:8080/weather?city=London
```

## 🔒 Security & Best Practices

### ✅ DO:
- Keep your API key in `application.properties` (ignored by Git)
- Use environment variables for production deployment
- Monitor your API usage on OpenWeatherMap dashboard
- Set up rate limiting if exposing the API publicly

### ❌ DON'T:
- Never commit `application.properties` with real API keys
- Don't share your API key in screenshots or messages
- Don't hardcode API keys in Java files
- Don't expose the API key in frontend JavaScript

## 📊 API Rate Limits

**OpenWeatherMap Free Tier:**
- ⏱️ **60 calls per minute**
- 📅 **1,000,000 calls per month**
- 🌍 Current weather data only
- ⏰ Data updates every 10 minutes

If you exceed these limits, you'll get HTTP 429 (Too Many Requests) error.

## 🐛 Troubleshooting

### Problem: "City not found" error
**Solutions:**
- ✓ Check spelling of the city name
- ✓ Use English names for international cities
- ✓ Try adding country code: "Paris,FR" or "London,GB"

### Problem: Application won't start
**Solutions:**
- ✓ Verify API key is correct in `application.properties`
- ✓ Check if port 8080 is already in use
- ✓ Ensure Java and Maven are properly installed
- ✓ Run `mvn clean install` to rebuild

### Problem: "401 Unauthorized" error
**Solutions:**
- ✓ Verify your API key is active
- ✓ Wait 10-15 minutes after creating new API key (activation time)
- ✓ Check for extra spaces in the API key

### Problem: "Connection refused" error
**Solutions:**
- ✓ Check your internet connection
- ✓ Verify OpenWeatherMap API is not down
- ✓ Check firewall settings

### Problem: Slow response times
**Solutions:**
- ✓ Check your internet speed
- ✓ OpenWeatherMap free tier may have delays
- ✓ Consider caching weather data

## 🧪 Testing

Run tests with:
```bash
mvn test
```

## 📦 Building for Production

Create an executable JAR:
```bash
mvn clean package
```

The JAR file will be created in `target/Weather-App-0.0.1-SNAPSHOT.jar`

Run the JAR:
```bash
java -jar target/Weather-App-0.0.1-SNAPSHOT.jar
```

## 🚀 Deployment Options

- **Heroku**: Easy deployment with free tier
- **AWS Elastic Beanstalk**: Scalable cloud deployment
- **Docker**: Containerized deployment
- **Traditional Server**: Deploy JAR to any server with Java

## 🤝 Contributing

Contributions are welcome! Here's how:

1. 🍴 Fork the repository
2. 🌿 Create a feature branch: `git checkout -b feature/AmazingFeature`
3. 💾 Commit your changes: `git commit -m 'Add some AmazingFeature'`
4. 📤 Push to the branch: `git push origin feature/AmazingFeature`
5. 🔃 Open a Pull Request

## 📝 Future Enhancements

- [ ] Add 5-day weather forecast
- [ ] Implement weather alerts
- [ ] Add temperature unit toggle (Celsius/Fahrenheit)
- [ ] Save favorite cities
- [ ] Add weather maps
- [ ] Implement geolocation for automatic city detection
- [ ] Add dark mode
- [ ] Create mobile-responsive design
- [ ] Add weather history charts

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 👨‍💻 Author

**Your Name**
- GitHub: [@yourusername](https://github.com/adelekeemmanuel)
- Email: adelekeemmanuel29@gmail.com

## 🙏 Acknowledgments

- [OpenWeatherMap](https://openweathermap.org/) - For providing the weather API
- [Spring Boot](https://spring.io/projects/spring-boot) - For the amazing framework
- [Thymeleaf](https://www.thymeleaf.org/) - For the template engine
- [Maven](https://maven.apache.org/) - For build management

## 📞 Support

If you have any questions or run into issues:
1. Check the [Troubleshooting](#-troubleshooting) section
2. Open an issue on GitHub
3. Contact me via email

## 📸 Screenshots

### Home Page
![Home Page](screenshots/home.png)
*Search for any city to get weather information*

### Weather Results
![Weather Results](screenshots/results.png)
*Detailed weather information with icons*

---

**Made with ❤️ and ☕ by Adeleke Emmanuel**

**⭐ Star this repo if you found it helpful!**
```

