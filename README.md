# PROG7312 ICE Task 4 – Weather Dashboard

A React Native weather dashboard developed for PROG7312 ICE Task 4. The application was provided as a debugging exercise containing several functional and interface-related errors. The purpose of this task was to investigate the supplied application, identify the problems, correct them and verify that the complete weather dashboard functions correctly.

# 1. Project Overview

The Weather Dashboard allows users to view weather information for three South African cities:

- Johannesburg
- Cape Town
- Durban

The application displays current weather information, a 24-hour forecast, a five-day forecast and Sun & Moon information.

The application was developed using React Native with TypeScript and tested using Expo Go on BlueStacks 5.

# 2. Purpose of the Task

The purpose of ICE Task 4 was to investigate and correct errors within an existing React Native application.

The supplied application contained a number of errors that were not all immediately visible through compilation. The application therefore had to be inspected, tested and debugged by interacting with the different sections of the interface.

The main areas investigated were:

- City selection
- Current weather information
- Weather details
- 24-hour forecast
- Five-day forecast
- Sun & Moon information
- Dashboard scrolling
- User interface behaviour

# 3. Technologies Used

- React Native
- TypeScript
- Expo
- Expo Go
- BlueStacks 5
- Visual Studio Code
- Git
- GitHub

# 4. Development Environment

The application was developed using Visual Studio Code.

The application was executed using Expo and tested on an Android environment through BlueStacks 5 and Expo Go.

The main application code is contained in `App.tsx`.

# 5. Application Features

The completed application provides:

- City selection
- Current weather information
- Weather details
- 24-hour weather forecast
- Five-day weather forecast
- Sun & Moon information
- City-specific background images
- Horizontal hourly forecast scrolling
- Full dashboard scrolling

## 5.1 City Selection

Users can select between:

- Johannesburg
- Cape Town
- Durban

Selecting a city updates the dashboard using the corresponding weather data.

## 5.2 Current Weather

The dashboard displays:

- City
- Country
- Weather condition
- Current temperature
- Weather icon
- Background image

## 5.3 Additional Weather Information

The application displays:

- Feels Like temperature
- Humidity
- Wind speed
- Wind direction
- Visibility
- Atmospheric pressure
- UV Index

## 5.4 24-Hour Forecast

The dashboard provides hourly weather information including:

- Time
- Weather icon
- Temperature

The hourly forecast can be accessed horizontally.

## 5.5 Five-Day Forecast

The application displays:

- Day
- Weather condition
- Weather icon
- High temperature
- Low temperature

## 5.6 Sun & Moon

The dashboard displays:

- Sunrise
- Sunset
- Moonrise
- Moonset
- Moon phase

# 6. Initial Debugging Investigation

The supplied application was first inspected and tested before corrections were made.

The debugging process involved both code inspection and manual interaction with the application because some errors were logical or visual rather than compiler errors.

The following areas were investigated:

- City selection
- Current weather information
- Weather detail values
- Hourly forecast values
- Hourly forecast scrolling
- Five-day forecast rendering
- High and low temperatures
- Sunrise and sunset information
- Sun & Moon information
- Dashboard scrolling

# 7. Error Log

| Error | Problem Identified | Correction |
|---|---|---|
| Missing ImageBackground import | ImageBackground was used without the required import | Added ImageBackground to the React Native imports |
| Incorrect city comparison | City buttons compared selectedCity with weather.country | Changed comparison to weather.city |
| Incorrect city selection value | Selecting a city stored the country instead of the city | Changed selection to weather.city |
| Incorrect humidity value | Humidity displayed the feelsLike value | Changed to selectedWeather.humidity |
| Incorrect hourly temperature | Every hourly card displayed the current temperature | Changed to hour.temperature |
| Incorrect hourly scrolling | Hourly forecast was not configured for horizontal access | Changed ScrollView to horizontal |
| Five-day forecast rendering | Daily forecast JSX was not correctly returned | Corrected the map rendering |
| Incorrect high temperature | Low temperature was displayed as high | Changed to day.high |
| Incorrect low temperature | High temperature was displayed as low | Changed to day.low |
| Incorrect sunrise value | Sunrise displayed sunset | Changed to selectedWeather.sunrise |
| Incorrect WeatherDetail value | Label was displayed instead of value | Changed output to value |

# 8. Debugging Corrections

## 8.1 ImageBackground

The supplied application used ImageBackground without correctly importing it.

The required React Native component was added to the import list.

The correction allowed the city-specific background image to display correctly.

## 8.2 City Selection

The original city selection logic incorrectly used the country value.

The comparison was corrected to use the city:

`selectedCity === weather.city`

The button action was also corrected to:

`setSelectedCity(weather.city)`

This ensured that Johannesburg, Cape Town and Durban could be selected correctly.

## 8.3 Humidity

The humidity section originally displayed the feels-like temperature.

This was corrected to use:

`selectedWeather.humidity`

The correct humidity percentage is now displayed for each city.

## 8.4 Hourly Forecast

The hourly forecast originally displayed the current temperature for every hour.

This was corrected to use:

`hour.temperature`

Each hourly card therefore displays its own temperature.

## 8.5 Horizontal Hourly Forecast

The 24-hour forecast was intended to be horizontally accessible.

The ScrollView was corrected to use the horizontal property.

This allows the user to access the complete 24-hour forecast.

## 8.6 Five-Day Forecast

The five-day forecast contained an issue with the JSX returned from the map function.

The rendering structure was corrected so that each daily forecast produces a visible card containing:

- Day
- Weather icon
- Condition
- High temperature
- Low temperature

## 8.7 High and Low Temperatures

The high and low values were reversed.

The correction uses:

- `day.high` for the high temperature
- `day.low` for the low temperature

## 8.8 Sunrise

The Sunrise field incorrectly used the sunset value.

It was corrected to use:

`selectedWeather.sunrise`

Sunrise and Sunset now display their respective values.

## 8.9 WeatherDetail

The reusable WeatherDetail component originally displayed the label instead of the supplied value.

The component was corrected so that the label and value are displayed separately.

# 9. Testing Approach

After the corrections were implemented, the application was manually tested using BlueStacks 5 and Expo Go.

Testing focused on actual application behaviour rather than only confirming that the project compiled.

The following areas were tested:

- Application launch
- City selection
- Current weather
- Weather details
- Hourly forecast
- Five-day forecast
- Sun & Moon
- Scrolling
- Different city datasets

# 10. Johannesburg Test

The Johannesburg dashboard was tested first.

The following values were verified:

- Temperature: 24°
- Feels Like: 25°
- Humidity: 42%
- Wind: 18 km/h NW
- Visibility: 10 km
- Pressure: 1018 hPa
- UV Index: 7

The Johannesburg city button was selected correctly and the corresponding background image was displayed.

<img width="555" height="937" alt="image" src="https://github.com/user-attachments/assets/9119d055-8541-417b-bcfb-628b6e1b045a" />
<img width="542" height="933" alt="image" src="https://github.com/user-attachments/assets/0bc98454-8da0-47a4-8a2b-7ba4b9c7480d" />



**Result: PASS**

# 11. Cape Town Test

Cape Town was selected using the city selector.

The following values were verified:

- Temperature: 19°
- Feels Like: 18°
- Humidity: 68%
- Wind: 24 km/h SW
- Visibility: 12 km

The background image changed correctly and the Cape Town weather information was displayed.

<img width="557" height="938" alt="image" src="https://github.com/user-attachments/assets/dcd57154-4057-4532-9c8a-88ea5f3b0260" />


**Result: PASS**

# 12. Durban Test

Durban was selected using the city selector.

The following values were verified:

- Temperature: 26°
- Feels Like: 28°
- Humidity: 76%
- Wind: 15 km/h NE
- Visibility: 9 km
- Pressure: 1012 hPa
- UV Index: 8

The Durban background image and weather information displayed correctly.

<img width="553" height="925" alt="image" src="https://github.com/user-attachments/assets/61af5fa8-fb28-4673-939b-15bf610618ff" />


**Result: PASS**

# 13. 24-Hour Forecast Test

The 24-hour forecast was tested to ensure that each hourly card displayed its own temperature.

For example, the Johannesburg forecast displayed:

- 10 AM: 24°
- 11 AM: 25°
- 12 PM: 26°
- 1 PM: 27°

The forecast was also tested for horizontal accessibility.

<img width="552" height="946" alt="image" src="https://github.com/user-attachments/assets/2dce09c0-170b-41f8-b002-c89a2863a0c6" />


**Result: PASS**

# 14. Five-Day Forecast Test

The five-day forecast was tested to ensure that all daily forecast entries were rendered.

Each entry displayed:

- Day
- Weather icon
- Condition
- High temperature
- Low temperature

The high and low values were also checked to ensure that they were displayed correctly.

<img width="548" height="930" alt="image" src="https://github.com/user-attachments/assets/12aa8acd-3b7e-41b1-a189-196497a84907" />


**Result: PASS**

# 15. Sun & Moon Test

The Sun & Moon section was tested to verify that each astronomical value was displayed correctly.

For Durban, the values were:

- Sunrise: 05:05
- Sunset: 18:08
- Moonrise: 21:32
- Moonset: 08:21
- Moon Phase: Waxing Gibbous 🌔

The test confirmed that Sunrise displayed the sunrise value rather than incorrectly displaying the sunset value.

<img width="552" height="965" alt="image" src="https://github.com/user-attachments/assets/3cb9b35d-817c-4d19-8d50-9db08cf21d63" />


**Result: PASS**

# 16. Scrolling Test

The complete dashboard was scrolled from the top to the bottom.

The following sections were confirmed to be accessible:

1. Weather Dashboard
2. City selector
3. Current weather
4. Weather details
5. 24 Hour Forecast
6. 5 Day Forecast
7. Sun & Moon
8. Footer

The dashboard remained accessible throughout the scrolling process.
<img width="550" height="930" alt="image" src="https://github.com/user-attachments/assets/25c30aa7-f949-4cad-8b6b-a27e1a24d0f4" />
<img width="548" height="936" alt="image" src="https://github.com/user-attachments/assets/4e86a073-62dc-4eb6-a44e-8a343ec551b1" />


**Result: PASS**

# 17. Testing Summary

| Test | Expected Result | Actual Result | Status |
|---|---|---|---|
| Application launch | Dashboard opens without an error | Dashboard opened successfully | PASS |
| Johannesburg selection | Johannesburg weather displayed | Correct | PASS |
| Cape Town selection | Cape Town weather displayed | Correct | PASS |
| Durban selection | Durban weather displayed | Correct | PASS |
| Current weather | Correct values displayed | Correct | PASS |
| Weather details | Correct weather details displayed | Correct | PASS |
| 24-hour forecast | Hourly values displayed correctly | Correct | PASS |
| Horizontal hourly scrolling | Complete hourly forecast accessible | Correct | PASS |
| Five-day forecast | Five daily entries rendered | Correct | PASS |
| High/low temperatures | High and low values displayed correctly | Correct | PASS |
| Sun & Moon | Correct astronomical values displayed | Correct | PASS |
| Full dashboard scrolling | All sections accessible | Correct | PASS |

# 18. Testing Environment

## Development Environment

- Visual Studio Code
- React Native
- TypeScript
- Expo

## Testing Environment

- BlueStacks 5
- Android
- Expo Go

The application was manually tested after the debugging corrections were implemented.

# 19. Code Quality

The corrected application maintains the structure of the supplied application while resolving the identified functional problems.

Comments were kept concise and were added where they assist in explaining important sections of the implementation.

The application uses TypeScript types for:

- Hourly forecast data
- Daily forecast data
- Weather data
- Weather detail properties

This improves clarity and provides type checking during development.

# 20. AI Usage

AI assistance was used during the development and debugging process.

ChatGPT by OpenAI was used to assist with:

- Understanding the supplied React Native code
- Identifying possible bugs
- Explaining TypeScript and React Native concepts
- Suggesting corrections

- Structuring testing documentation
- Reviewing application behaviour


The supplied application remained the basis of the implementation. Suggested changes were reviewed and tested manually by the student using BlueStacks 5 and Expo Go.



# 21. Learning Outcomes

The debugging process provided practical experience with:

- Reading and understanding existing React Native code
- Identifying logical errors
- Debugging TypeScript applications
- Working with arrays and objects
- Using map functions to render interface components
- Managing React state using useState
- Using conditional styling
- Working with ScrollView
- Testing applications on an Android environment
- Verifying application behaviour through manual testing
- Documenting debugging decisions and test results

# 22. Challenges Encountered

One of the main challenges was that not every problem produced a compiler error.

Several issues only became clear after interacting with the application.

For example, the application could run while still displaying incorrect information because:

- The wrong property was being displayed.
- The wrong city value was being stored.
- Hourly cards were using the current temperature.
- The five-day forecast was not rendering correctly.
- Sunrise was displaying the sunset value.

This required both code inspection and manual testing.

# 23. Final Application Status

After the corrections were implemented and tested, the Weather Dashboard successfully provides the required functionality.

The final application allows users to:

- Select Johannesburg, Cape Town or Durban
- View current weather information
- View additional weather details
- View a 24-hour forecast
- View a five-day forecast
- View Sun & Moon information
- Scroll through the complete dashboard

All major functionality tested during the development process passed successfully.

# 24. Conclusion

ICE Task 4 provided practical experience in debugging an existing React Native application.

The supplied Weather Dashboard contained a combination of compilation, data-binding, rendering and interface-related problems. These were investigated systematically and corrected while maintaining the original application structure.

Testing was then performed using BlueStacks 5 and Expo Go. The three available cities were tested along with the hourly forecast, five-day forecast, Sun & Moon information and complete dashboard scrolling.

The final result is a functioning React Native Weather Dashboard that meets the required functionality of the task.

# 25. References

Expo, 2026. *Expo Documentation*. [online] Available at: https://docs.expo.dev/ [Accessed 12 October 2026].

Meta, 2026. *React Native Documentation*. [online] Available at: https://reactnative.dev/docs/getting-started [Accessed 12 October 2026].

PROG7312, 2026. *ICE Task 4 – Weather Dashboard & UI Debugging*. Unpublished coursework document. The Independent Institute of Education (The IIE).

TypeScript, 2026. *TypeScript Documentation*. [online] Available at: https://www.typescriptlang.org/docs/ [Accessed 12 October 2026].

# 26. Repository

The complete source code for this project is available on GitHub:

https://github.com/ST10519103/prog7312-2026-prog7312-ice-task-4-iamphineas

# 27. Project Structure

The project is organised as follows:

- `App.tsx` – Main React Native application
- `assets/` – Application assets
- `screenshots/` – Testing screenshots
- `app.json` – Expo application configuration
- `package.json` – Project dependencies and scripts
- `package-lock.json` – Dependency lock file
- `tsconfig.json` – TypeScript configuration
- `README.md` – Project documentation



# 28. Final Testing Statement

The application was tested manually after the debugging corrections were implemented.

The following areas were successfully verified:

- Application launch
- Johannesburg weather
- Cape Town weather
- Durban weather
- Current weather information
- Additional weather information
- 24-hour forecast
- Five-day forecast
- Sun & Moon information
- Horizontal hourly scrolling
- Full dashboard scrolling

All tested functionality passed successfully.

**Final Result: PASS**
<img width="556" height="932" alt="image" src="https://github.com/user-attachments/assets/dc13bf58-469c-4a18-83db-b6ecd2255b6d" />

The Weather Dashboard is ready for submission.
