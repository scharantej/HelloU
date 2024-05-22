## Flask App Design: Hello World in Google Font

### HTML Files
- **index.html:**
   - Contains the HTML structure for the web page.
   - Includes a div element with an id of "message" where the "Hello World" message will be displayed.

### Routes
- **/index**:
   - Defines the main route of the application.
   - Serves the index.html file to the client.

- **/hello_world**:
   - Defines the route responsible for generating the "Hello World" message.
   - Renders the index.html template with the "Hello World" message embedded in the div element with id "message."

### Implementation
- The following code snippet implements the Flask application based on the design:

```python
from flask import Flask, render_template

app = Flask(__name__)

@app.route('/')
def index():
    return render_template('index.html')

@app.route('/hello_world')
def hello_world():
    message = "Hello World"
    return render_template('index.html', message=message)

if __name__ == '__main__':
    app.run(debug=True)
```