# MMM-WeatherChart

Hourly Forecast (temperature, weather icons on the top, rain volume on the bottom)

![image](https://user-images.githubusercontent.com/48573325/94290828-b0d23e80-ff95-11ea-8c32-b9c4b13d2b8a.png)

Daily Forecast (max and min temperature, weather icons on the top, rain volume on the bottom)

![image](https://user-images.githubusercontent.com/48573325/94291243-54bbea00-ff96-11ea-83f9-0873b4dd8faf.png)

MagicMirror module for displaying weather forecasts from [OpenWeather](https://openweathermap.org/). Weather forecasts are displayed by using [Chart.js](https://www.chartjs.org/), an open-source free library for drawing charts.

This module can work with free OpenWeather API, which only requires to sign up and get an API key.

## Installation

Clone this repository and place it on MagicMirror module directory.

```
$ cd ~/MagicMirror/modules
$ git clone https://github.com/mtatsuma/MMM-WeatherChart.git
```

## Configuration

### Configuration Example
```
   modules: [
        {
            "module": "MMM-WeatherChart",
            "position": "top_right",
            "config": {
                "apiKey": "xxxx",
                "dataNum": 12,
                "dataType": "hourly",
                "height": "500px",
                "width": "800px"
                "lat": 35.571337,
                "lon": 139.633989,
                "units": "metric",
            }
        }
   ]
```

### Configuration Options

| Options | Required | Default | Description |
|:--------|:--------:|:--------|:------------|
| updateInterval | | `10 * 60 * 1000` | Weather data update interval (miliseconds) |
| retryDelay | | `5 * 1000` | Delay for retry to get weather data (miliseconds) |
| apiBase | | `https://api.openweathermap.org/data/` | Base URL of [OpenWeather](https://openweathermap.org/) API |
| apiVersion | | `2.5` | Version of [OpenWeather](https://openweathermap.org/) API |
| apiEndpoint | | `onecall` | [OpenWeather](https://openweathermap.org/) API endpoint. [One Call API](https://openweathermap.org/api/one-call-api) is used by default, which is available for Free subscription. Note: Don't change this option because other endpoint is not supported! |
| apiKey | yes | | API key to call [OpenWeather](https://openweathermap.org/) API. You can get the API key by signing up [OpenWeather](https://openweathermap.org/). |
| lat | yes | | latitude of the place you want to get weather information |
| lon | yes | | longitude of the place you want to get weather information |
| units | | `standard` | Units of measurement documented in [OpenWeather API document](https://openweathermap.org/api/one-call-api). `standard`, `metric` and `imperial` units are available. |
| chartjsVersion | | `2.9.3` | Version of [Chart.js](https://www.chartjs.org/) |
| chartjsDatalablesVersion | | `0.7.0` | Version of Chart.js [Datalabels plugin](https://github.com/chartjs/chartjs-plugin-datalabels) |
| height | | `300px` | Height of the chart area |
| width | | `500px` | Width of the chart area |
| fontSize | | `16` | Font size of characters in the chart |
| timeOffsetHours | | `0` | Offset in hours. This is used when your timezone is different from the timezone set in MagicMirror server. |
| title | | `Weather Forecast` | Title of the chart to display |
| iconURLBase | | `https://openweathermap.org/img/wn/` | Base URL to get weather icons. By default, icons provided from OpenWeather is used. If you want to use your own icons, you must prepare icon image files whose name is the `<icon ID>.png`. The icon ID is documented in [Weather conditions](https://openweathermap.org/weather-conditions#How-to-get-icon-URL) |
| dataType | | `hourly` | Data type to display. `hourly` or `daily` is available. |
| dataNum | | `24` | Number of data to display. When you set this value as larger than the maximum number of data returned from [OpenWeather API](https://openweathermap.org/api/one-call-api), the number of data is automatically set as the maximum number of data from [OpenWeather API document](https://openweathermap.org/api/one-call-api) API. |
| nightBorderDash | | `[5, 1]` | Style of dash line for nighttime (`[<line length>, <blank length>]`). This option is available only for `hourly` data type. |
| showIcon | | `false` | Show weather Icon on the top |
| showRain | | `false` | Show rain volume (mm) on the bottom |
| color | | `rgba(255, 255, 255, 1)` | Color of line and letters |
| backgroundColor | | `rgba(0, 0, 0, 0)` | Color of background |
| fillColor | | `rgba(255, 255, 255, 0.1)` | Color for filling rain volume line |