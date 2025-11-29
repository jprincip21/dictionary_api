# 📘 Dictionary API (Flask)
A simple Flask-based web application that serves word definitions through a clean API endpoint. This project loads a dictionary dataset from a CSV file, displays a homepage, and exposes a REST API for retrieving definitions.

## 🚀 Features

- Flask web server with a homepage (/)

- REST API endpoint for fetching definitions
- Example: /api/v1/your-word
- CSV-powered dictionary using Pandas
- Automatic dash-to-space translation (e.g., “ice-cream” → “ice cream”)
- JSON response format

## 🛠️ Requirements

Install dependencies:
```
pip install flask pandas
```

The app starts on:
```
http://127.0.0.1:5001/
```

## 📡 API Usage
# Endpoint
```
GET /api/v1/<word>
```
### Example Request
```
GET /api/v1/hello
```
### Example Response
```
{
  "word": "hello",
  "definition": "A greeting used when meeting someone."
}
```

If the requested word contains dashes, they are automatically converted to spaces:
```
GET /api/v1/ice-cream
```
Looks up the word ice cream.

## 🧠 How It Works
- The CSV file (dictionary.csv) is loaded once at startup:
  ```
  df = pd.read_csv("dictionary.csv")
  ```
- When a word is requested, Flask:

1. Converts dashes -> spaces

2. Looks up the word in the DataFrame

3. Returns a JSON dictionary with the definition
