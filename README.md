# dato-a-la-azar
from ast import Return
import random
from flask import Flask

app = Flask(__name__)

datos = ["Elon Musk afirma que las redes sociales están diseñadas para mantenernos dentro de la plataforma, para que pasemos el mayor tiempo posible viendo contenidos",
         "Las redes sociales tienen aspectos positivos y negativos, y debemos ser conscientes de ambos cuando utilicemos estas plataformas",
         "La mayoría de las personas que sufren adicción tecnológica experimentan un fuerte estrés cuando se encuentran fuera del área de cobertura de la red o no pueden utilizar sus dispositivos",
         "El estudio de la dependencia tecnológica es una de las áreas más relevantes de la investigación científica moderna"]

animes = ["https://erikstore.com/blog/wp-content/uploads/2024/06/DRAGON-BALL-Z.avif",
          "https://erikstore.com/blog/wp-content/uploads/2024/06/NARUTO-SHIPPUDEN.avif",
          "https://erikstore.com/blog/wp-content/uploads/2024/06/ONE-PIECE-min.jpg",
          "https://erikstore.com/blog/wp-content/uploads/2024/06/POKEMON.jpg",
          "https://erikstore.com/blog/wp-content/uploads/2024/06/ATTACK-ON-TITAN-min.jpeg",
          "https://erikstore.com/blog/wp-content/uploads/2024/06/demon-slayer.webp"]

@app.route("/dato_al_azar")
def hello_world():
    return f'<p>hola buen dia<p>{random.choice(datos)}</p>'

@app.route("/")
def inicio():
    return f'<a href="/dato_al_azar">¡Ver un dato aleatorio!</a>'

@app.route("/imagen_al_azar")
def ANIME():
    return f'<p>{random.choice(animes)}</p>'

@app.route("/")
def start():
    return f'<a href="/imagen_al_azar">¡Ver una imagen aleatoria!</a>'

app.run(debug=True)
