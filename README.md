# backend-ssk

A simple Go REST API that fetches real-time weather data using the [OpenWeatherMap API](https://openweathermap.org/api).

## Features

- Query current weather by city name
- Returns temperature (current, min, max) in JSON
- Dockerized for easy deployment
- CI with CodeQL and SonarCloud

## Tech Stack

- **Language:** Go
- **API:** OpenWeatherMap
- **CI:** GitHub Actions (CodeQL, SonarCloud)
- **Deploy:** Docker

## Getting Started

### Prerequisites

- Go 1.18+
- OpenWeatherMap API key → [get one free](https://openweathermap.org/api)

### Configuration

Create an `.apiConfig` file in the project root:

```json
{
  "OpenWeatherMapApiKey": "your_api_key_here"
}
```

### Run locally

```bash
go run main.go
```

### Run with Docker

```bash
docker build -t backend-ssk .
docker run -p 8080:8080 backend-ssk
```

## Usage

```bash
curl http://localhost:8080/weather?city=Singapore
```

Example response:

```json
{
  "name": "Singapore",
  "main": {
    "temp": 303.15,
    "temp_min": 301.48,
    "temp_max": 304.82
  }
}
```
