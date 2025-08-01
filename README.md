JSON Data Converter and Validator

This Python project reads two different JSON data formats and converts them into a unified structure. It also includes test cases using the `unittest` module to ensure correctness of the transformation.

## Project Structure
├── data-1.json # Input JSON file in Format 1
├── data-2.json # Input JSON file in Format 2
├── data-result.json # Expected unified result format
├── json # Main Python script with transformation & tests

 Features

- Convert JSON from **Format 1** to unified format
- Convert JSON from **Format 2** to unified format
- Parse timestamp from ISO8601 format to epoch milliseconds
-  Extract nested location and device details
-  Unit testing with `unittest`


##  How to Run

1. Make sure all `.json` files are in the same directory.
2. Run the Python file:

```bash
python json

JSON FORMAT DETAILS
Format 1
{
  "deviceID": "...",
  "deviceType": "...",
  "timestamp": 123456789,
  "location": "country/city/area/factory/section",
  "operationstatus": "...",
  "temp": ...
}

Format 2
{
  "device": {
    "id": "...",
    "type": "..."
  },
  "timestamp": "2024-01-01T12:00:00.000Z",
  "country": "...",
  "city": "...",
  "area": "...",
  "factory": "...",
  "section": "...",
  "operationstatus": "...",
  "temperature": ...
}
Unified Format (Output)
{
  "deviceID": "...",
  "deviceType": "...",
  "timestamp": 123456789000,
  "location": {
    "country": "...",
    "city": "...",
    "area": "...",
    "factory": "...",
    "section": "..."
  },
  "data": {
    "status": "...",
    "temperature": ...
  }
}

Test Coverage
test_dataType1: Ensures format 1 is converted correctly
test_dataType2: Ensures format 2 is converted correctly
test_sanity: Ensures expected result format is intact

Requirements
Python 3.x
Standard libraries only (json, datetime, unittest)

