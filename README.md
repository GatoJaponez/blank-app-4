import streamlit as st
import random

def get_random_drink(keyword):
    drinks = {
        "café": [
            "Cappuccino",
            "Latte Macchiato",
            "Flat White",
            "Mocha",
            "Espresso Doble",
            "Caramel Macchiato",
            "Affogato"
        ],
        "frappé": [
            "Frappé de Vainilla",
            "Frappé de Caramelo",
            "Frappé de Chocolate",
            "Frappé de Fresa",
            "Frappé de Té Verde",
            "Frappé de Avellana",
            "Frappé de Café"
        ],
        "té": [
            "Té Chai Latte",
            "Té Verde Matcha",
            "Té Negro con Vainilla",
            "Té de Hibisco",
            "Té Blanco con Miel",
            "Té de Frutos Rojos",
            "London Fog Latte"
        ],
        "chocolate": [
            "Chocolate Caliente Clásico",
            "Chocolate Blanco Caliente",
            "Chocolate con Naranja",
            "Chocolate con Menta",
            "Chocolate con Canela",
            "Chocolate con Avellanas",
            "Chocolate con Almendras"
        ],
        "especial": [
            "Pumpkin Spice Latte",
            "Toffee Nut Latte",
            "Gingerbread Latte",
            "Maple Pecan Latte",
            "Coconut Mocha",
            "Honey Almond Latte",
            "Salted Caramel Mocha"
        ]
    }
    
    return random.choice(drinks.get(keyword, ["No hay bebidas disponibles para esta palabra."]))

st.title("Generador de Bebidas Random estilo Starbucks")

keyword = st.text_input("Escribe una palabra clave para encontrar una bebida:")

if st.button("Generar Bebida"):
    drink = get_random_drink(keyword.lower())
    st.subheader("Bebida Sugerida:")
    st.write(drink)
