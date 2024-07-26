# grid-template-layout
Simple layout using grid template


``` html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Welcome to pyEstate</title>
    <link rel="stylesheet" href="{{ url_for('static', filename='/styles.css') }}">
    <script src="https://cdn.jsdelivr.net/npm/tinymce@5.10.2/tinymce.min.js" referrerpolicy="origin"></script>
    <script>
        tinymce.init({
            selector: '.editor',
            menubar: false,
            plugins: 'advlist autolink lists link charmap print preview anchor textcolor',
            toolbar: 'undo redo | formatselect | bold italic backcolor | alignleft aligncenter alignright alignjustify | bullist numlist outdent indent | removeformat'
        });
    </script>


</head>
<body>
    <div class="main-container">
        <div class="top-content">
            <div class="logo-box"></div>
            <button class="orange-button send-button">SEND</button>

        </div>
        <br>
        <br>
        <div class="bottom-content">
            <button class="orange-button orange-button-one">ADD CONTACT</button>
            <button class="orange-button orange-button-two">INCLUDE CONTACT</button>
            <button class="orange-button orange-button-three">NEW EMAIL</button>
            <button class="orange-button orange-button-four">LOAD EMAIL</button> 
            <textarea class="editor editor-one" id="editor"></textarea>
    
        </div>
    </div>
</body>
</html>
```
``` css
body {
    font-family: Arial, sans-serif;
    background-color: #f0f0f0;
}

.logo-box {
    width: 200px;
    height: 100px;
    background-color: #ff0000; /* Red color */
    margin-bottom: auto;
}

.orange-button {
    background-color: #ff9a02; /* Orange color */
    border: 3px solid #000000; /* Black thick stroke */
    color: #000000; /* Black text */
    padding: 10px 20px;
    font-size: 16px;
    cursor: pointer;
    margin: 20px;
    text-align: center;
}

.orange-button:hover {
    background-color: #ff8c00; /* Darker orange on hover */
}
.editor-container {
    width: 100%;
    max-width: 800px;
}

.row-height{
    height: 500px;
}



.top-content {
    display: grid;
    grid-template-columns: 200px 200px;

}
.orange-button-send{
    grid-area: orange-button-send;
}
.orange-button-one{
    grid-area: orange-button-one;
}
.orange-button-two{
    grid-area: orange-button-two;
}
.orange-button-three{
    grid-area: orange-button-three;
}
.orange-button-four{
    grid-area: orange-button-four;
}
.editor-one{
    grid-area: editor-one;
}
.editor-two{
    grid-area: editor-two;
}


.bottom-content {
    display: grid;
    grid-template-rows: 100px 100px 100px 100px ;
    grid-template-columns: 200px  800px;
    grid-template-areas: "orange-button-one editor-one"
    "orange-button-two editor-one"
    "orange-button-three editor-one"
    "orange-button-four editor-one";
    

}
```
``` python
from flask import Flask, render_template

app = Flask(__name__)

@app.route('/')
def home():
    return render_template('index.html')

if __name__ == '__main__':
    app.run(debug=True)
```
