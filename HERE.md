# codedex-bot-de-discord
import discord
from discord.ext import commands

# Crea una instancia del bot con el prefijo "!" para los comandos
bot = commands.Bot(command_prefix="!")

# Evento: cuando el bot se conecta y está listo
@bot.event
async def on_ready():
    print(f"¡Hola! Soy el bot de {bot.user}! 😄 ¡Estoy conectado y listo para ayudarte!")

# Comando simple: "¡hola"
@bot.command()
async def hola(ctx):
    await ctx.send(f"¡Hola, {ctx.author.display_name}! Soy el bot creado por TI. 😎 ¿Cómo estás hoy?")

# Comando con argumentos: "¡sumar 5 3"
@bot.command()
async def sumar(ctx, num1: int, num2: int):
    result = num1 + num2
    await ctx.send(f"Hola {ctx.author.display_name}, la suma de {num1} y {num2} es: {result}.")

# Comando adicional: "¡presentate"
@bot.command()
async def presentate(ctx):
    await ctx.send(f"¡Hola! Soy un bot creado por {ctx.author.display_name}. ¡Espero que te diviertas!")

# Aquí va tu token
token = 'TU_TOKEN_AQUI'  # Reemplaza con tu token de bot

# Ejecuta el bot
bot.run(token)
