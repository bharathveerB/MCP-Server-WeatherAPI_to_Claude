# MCP Weather Service

A Model Control Protocol (MCP) server that provides weather-related tools including weather alerts and forecasts using the National Weather Service (NWS) API.

## Features

- **MCP Tools**:
  - `get_alerts`: Retrieve weather alerts for any US state
  - `get_forecast`: Get detailed weather forecasts by coordinates
- **MCP Integration**:
  - Built with FastMCP framework
  - Asynchronous operation support
  - Type-annotated interfaces
  - Self-documenting tools

## Screenshot

<!-- Add your Claude response image here -->
![Claude Response](path/to/your/image.png)
*Replace the above path with your actual image path*

## Getting Started

### Prerequisites

- Python 3.8+
- pip (Python package manager)
- An internet connection (for API access)

### Installation

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd weather
   ```

2. Create and activate a virtual environment (recommended):
   ```bash
   python -m venv .venv
   .venv\Scripts\activate  # On Windows
   ```

3. Install the required dependencies:
   ```bash
   pip install -e .
   ```

## Usage

### Available Commands

1. **Get Weather Alerts**
   ```python
   from weather import get_alerts
   
   # Get alerts for California
   alerts = await get_alerts("CA")
   print(alerts)
   ```

2. **Get Weather Forecast**
   ```python
   from weather import get_forecast
   
   # Get forecast for New York City
   forecast = await get_forecast(40.7128, -74.0060)
   print(forecast)
   ```

## API Reference

### `get_alerts(state: str) -> str`
Get weather alerts for a US state.
- `state`: Two-letter US state code (e.g., 'CA', 'NY')

### `get_forecast(latitude: float, longitude: float) -> str`
Get weather forecast for specific coordinates.
- `latitude`: Latitude of the location
- `longitude`: Longitude of the location

## MCP Implementation

### Project Structure

- `weather.py`: Main MCP server implementation with tool definitions
- `main.py`: MCP server entry point
- `pyproject.toml`: Project configuration with MCP dependencies

### MCP Tools

#### `get_alerts(state: str) -> str`
Fetches active weather alerts for a US state.

**Parameters**:
- `state`: Two-letter US state code (e.g., 'CA', 'NY')

**Returns**:
Formatted string containing active weather alerts

#### `get_forecast(latitude: float, longitude: float) -> str`
Retrieves weather forecast for specific coordinates.

**Parameters**:
- `latitude`: Latitude of the location
- `longitude`: Longitude of the location

**Returns**:
Formatted weather forecast information

## MCP Dependencies

- `fastmcp`: Core MCP server implementation
- `httpx`: Async HTTP client for API requests
- `pydantic`: For data validation and settings management

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
