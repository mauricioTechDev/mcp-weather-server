# Weather MCP Server

A Model Context Protocol (MCP) server that provides weather information services using the National Weather Service (NWS) API. This server implements a set of tools that can be used by AI models to fetch weather alerts and forecasts for locations in the United States.

## Features

- **Weather Alerts**: Get active weather alerts for any US state using a two-letter state code
- **Weather Forecast**: Get detailed weather forecasts for any location in the US using latitude and longitude coordinates
- **MCP Integration**: Implements the Model Context Protocol for seamless integration with AI models
- **TypeScript**: Written in TypeScript for type safety and better developer experience

## Installation

```bash
npm install
npm run build
```

## Usage

This server is designed to be used as a CLI tool and can be installed globally:

```bash
npm install -g .
weather
```

The server runs on stdio and provides two main tools:

### 1. Get Weather Alerts
Retrieves active weather alerts for a specified US state.

Example parameters:
```json
{
  "state": "CA"  // Two-letter state code
}
```

### 2. Get Weather Forecast
Retrieves weather forecast for a specific location using coordinates.

Example parameters:
```json
{
  "latitude": 37.7749,
  "longitude": -122.4194
}
```

## Technical Details

- Built using the `@modelcontextprotocol/sdk` for MCP implementation
- Uses the National Weather Service (NWS) API for weather data
- Implements data validation using Zod
- Written in TypeScript with Node.js
- Uses ES modules (type: "module" in package.json)

## Dependencies

- `@modelcontextprotocol/sdk`: ^1.12.1
- `zod`: ^3.25.41
- `typescript`: ^5.8.3 (dev dependency)
- `@types/node`: ^22.15.26 (dev dependency)

## Development

1. Clone the repository
2. Install dependencies: `npm install`
3. Build the project: `npm run build`
4. Run the server: `npm start`

## API Integration

The server uses the National Weather Service (NWS) API with the following endpoints:
- Alerts: `https://api.weather.gov/alerts`
- Points: `https://api.weather.gov/points/{lat},{lon}`
- Forecast: Uses the forecast URL provided by the points endpoint

## Error Handling

The server includes robust error handling for:
- API request failures
- Invalid coordinates
- Missing or malformed data
- Network issues

## License

ISC 