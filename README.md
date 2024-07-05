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
