<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Formulario de Amor</title>
    <style>
        body {
            font-family: 'Comic Sans MS', cursive, sans-serif;
            background-color: #ffe4e1;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }
        .form-container {
            background-color: #fff;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        .form-container h1 {
            font-size: 24px;
            margin-bottom: 20px;
            text-align: center;
        }
        .form-container label {
            display: block;
            margin-bottom: 8px;
        }
        .form-container input[type="text"] {
            width: 100%;
            padding: 8px;
            margin-bottom: 10px;
            border: 1px solid #ccc;
            border-radius: 4px;
        }
        .form-container button {
            background-color: #ff69b4;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }
        .form-container button:hover {
            background-color: #ff1493;
        }
    </style>
</head>
<body>
    <div class="form-container">
        <h1>Formulario de Amor 💖</h1>
        <form action="/submit" method="post">
            <label for="name">¿Cómo te llamas?</label>
            <input type="text" id="name" name="name" required>
            <button type="submit">Enviar</button>
        </form>
    </div>
</body>
</html>
from flask import Flask, render_template, request

app = Flask(__name__)

@app.route('/')
def index():
    return render_template('love_form.html')

@app.route('/submit', methods=['POST'])
def submit():
    name = request.form['name']
    response = f"Hola, {name}! 🌹 Aquí hay algunas cosas que quiero que sepas:\n\n"
    response += "1. Te quiero tanto como a Python. ¡Y eso es mucho! 🐍\n"
    response += "2. Eres el print de mi Hello World! 💻\n"
    response += "3. Si fueras un error, serías un SyntaxError, porque simplemente no puedo ignorarte. 🥰\n"
    response += "4. Si fueras una función, serías mi favorita() porque siempre me haces sonreír. 😊\n"
    return response

if __name__ == '__main__':
    app.run(debug=True)
