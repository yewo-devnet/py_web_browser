# PyQt5 Web Browser

## Project Overview
This project is a simple **web browser** built using **PyQt5**,the browser default fumctionality extends a previous project, an [AsyncIO HTTP server](https://github.com/yewo-devnet/py-http-server), by connecting to it to render HTML templates hosted locally at `http://localhost:8085`. When a requested page is not found, the browser displays an error message and offers an option to search for the query on Google.

The browser:
- Loads the homepage (`http://localhost:8085/`) by default.
- Allows users to enter a page name (e.g., `register`) to load templates like `http://localhost:8085/register`.
- Displays a "Page not found" message if the requested page does not exist on the local server.
- Provides a button to search the query on Google if the page is not found.
- Prioritizes local server content, making it a specialized client for the AsyncIO HTTP server.

## Prerequisites
To run this project, you need:
- Python 3.7 or higher
- PyQt5 library 
- PyQt5 WebEngine 
- The [AsyncIO HTTP server](https://github.com/yewo-devnet/py-http-server) running locally on `http://localhost:8085`
- The `templates/` folder from the HTTP server project, containing `index.html` and `register.html`

## Installation
1. **Clone the Repository**:
   ```bash
   git clone https://github.com/your-username/py_web_browser.git
   cd py_web_browser
   ```

2. **Install Dependencies**:
   Install the required Python packages:
   ```bash
   pip install -r requirements.txt
   ```

3. **Set Up the HTTP Server**:
   - Ensure the [AsyncIO HTTP server](https://github.com/yewo-devnet/py-http-server) is set up and running.
   - Verify the `templates/` directory in the HTTP server project contains:
     - `index.html`: A homepage (e.g., `<h1>Welcome to the AsyncIO Server</h1>`).
     - `register.html`: A form with `username` and `email` fields (see the HTTP server repository for details).
   - Start the HTTP server:
     ```bash
     cd path/to/py_http_server
     python server.py
     ```

4. **Project Structure**:
   Ensure the following file is present:
   ```
   py_web_browser/
   ├── browser.py
   └── README.md
   └── requirements.txt
   ```

## Usage
1. **Run the Browser**:
   ```bash
   python browser.py
   ```
   The browser window will open, displaying the homepage from `http://localhost:8085/`.

2. **Navigate Pages**:
   - In the search bar, enter a page name (e.g., `register`) to load `http://localhost:8085/register`.
   - Press Enter to navigate to the page.
   - If the page exists (e.g., `register.html`), it will render in the browser.
   - If the page does not exist, a "Page not found" message appears, and a "Search on Google" button is shown.

3. **Search on Google**:
   - If a page is not found, click the "Search on Google" button to search the entered query on Google (e.g., `https://www.google.com/search?q=register`).

## Notes
- The browser requires the AsyncIO HTTP server to be running on `http://localhost:8085` to load local templates.
- The search bar expects page names without the `.html` extension or full URLs (e.g., enter `register` for `http://localhost:8085/register`).
- The browser does not handle external URLs directly unless redirected to Google search.
- Error handling is basic, focusing on detecting failed page loads and offering a Google search fallback.


## Acknowledgments
- Special thanks to my lecturer, **Ramsey Ith Njema II**, for providing guidance and instruction during the course at the University of Malawi, which made this project possible.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
