# <h1 align="center">🧹 [4sgm URL Cleaner](https://github.com/ronknight/flask-url-cleaner) </h1> 

#### <h4 align="center">A versatile Flask web application and API that cleans URLs by removing unnecessary parameters like 'csrfToken' and empty fields.</h4>

<p align="center">
<a href="https://twitter.com/PinoyITSolution"><img src="https://img.shields.io/twitter/follow/PinoyITSolution?style=social"></a>
<a href="https://github.com/ronknight?tab=followers"><img src="https://img.shields.io/github/followers/ronknight?style=social"></a>
<a href="https://github.com/ronknight/ronknight/stargazers"><img src="https://img.shields.io/github/stars/BEPb/BEPb.svg?logo=github"></a>
<a href="https://github.com/ronknight/ronknight/network/members"><img src="https://img.shields.io/github/forks/BEPb/BEPb.svg?color=blue&logo=github"></a>
<a href="https://youtube.com/@PinoyITSolution"><img src="https://img.shields.io/youtube/channel/subscribers/UCeoETAlg3skyMcQPqr97omg"></a>
<a href="https://github.com/ronknight/flask-url-cleaner/issues"><img src="https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=flat"></a>
<a href="https://github.com/ronknight/flask-url-cleaner/blob/master/LICENSE"><img src="https://img.shields.io/badge/License-MIT-yellow.svg"></a>
<a href="#"><img src="https://img.shields.io/badge/Made%20with-Python-1f425f.svg"></a>
<a href="https://github.com/ronknight"><img src="https://img.shields.io/badge/Made%20with%20%F0%9F%A4%8D%20by%20-%20Ronknight%20-%20red"></a>
</p>

<p align="center">
  <a href="#features">Features</a> •
  <a href="#requirements">Requirements</a> •
  <a href="#installation">Installation</a> •
  <a href="#project-structure">Project Structure</a> •
  <a href="#usage">Usage</a> •
  <a href="#api-endpoint">API Endpoint</a> •
  <a href="#example">Example</a> •
  <a href="#web-interface">Web Interface</a> •
  <a href="#visualization">Visualization</a>
</p>

---

## 🌟 Features

- Removes the 'csrfToken' parameter from URLs
- Simple Flask web application with a user interface
- **API endpoint** for programmatic access
- Easily integrable into larger projects

## 📋 Requirements

- Python 3.x
- Flask

## 🛠️ Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/ronknight/flask-url-cleaner.git
   cd flask-url-cleaner
   ```

2. Install the required dependencies:
   ```bash
   pip install flask
   ```

## 📁 Project Structure

The project has the following structure:

```
flask-url-cleaner/
│
├── app.py
├── README.md
└── index.html
```

- `app.py`: The main Flask application file
- `README.md`: This file, containing project information and instructions
- `index.html`: The HTML template for the web interface

## 🚀 Usage

1. Run the Flask application:
   ```bash
   python app.py
   ```

2. The server will start running on `http://127.0.0.1:5000/` and will be accessible on your local network.

3. Open your web browser and navigate to `http://127.0.0.1:5000/` or use your local network IP address to access the application from other devices.

## 📡 API Endpoint

### POST /clean_url

Removes the 'csrfToken' parameter from the provided URL.

**Request Body:**
```json
{
    "url": "https://example.com/page?param1=value1&csrfToken=abc123&param2=value2"
}
```

**Response:**
```json
{
    "cleaned_url": "https://example.com/page?param1=value1&param2=value2"
}
```

## 💡 Example

Using curl to test the API:

```bash
curl -X POST -H "Content-Type: application/json" -d '{"url": "https://example.com/page?param1=value1&csrfToken=abc123&param2=value2"}' http://127.0.0.1:5000/clean_url
```

Expected output:
```json
{
    "cleaned_url": "https://example.com/page?param1=value1&param2=value2"
}
```

## 🌐 Web Interface

The application includes a web interface for easy URL cleaning:

1. Open your web browser and go to `http://127.0.0.1:5000/` or use your local network IP address (e.g., `http://192.168.1.200:5000/`)
2. You'll see a form with the title "Enter a URL to Clean"
3. Enter the URL you want to clean in the provided input field
4. Click the "Clean URL" button
5. The cleaned URL will be displayed in the "Response" section below the form
6. You can **copy** the cleaned URL by clicking the "Copy" button next to the URL input

The web interface now includes a copy button after the cleaned URL field and provides a description explaining the removal of unnecessary parameters like `csrfToken`, `keywords`, and other empty fields that don't affect functionality.

The web interface is rendered using the `index.html` file located in the root directory. Flask serves this file directly from the root URL `/`.

## 📊 Visualization

```mermaid
graph TD
    A[User Inputs URL] -->|Submits via Web Form| B[Flask Server]
    B --> C[Clean URL Function]
    C -->|Removes csrfToken & unnecessary parameters| D[Returns Cleaned URL]
    B --> E[API Endpoint /clean_url]
    E --> F[Receives POST Request]
    F -->|Removes csrfToken & unnecessary parameters| G[Responds with Cleaned URL]
    D --> H[Web UI Displays Cleaned URL + Copy Button]
    G --> H

```

---

Made with ❤️ by [Ronknight](https://github.com/ronknight)