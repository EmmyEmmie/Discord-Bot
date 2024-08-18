# Discord-Bot
import discord
from discord.ext import commands

# Set the bot's command prefix (e.g., '!' for commands like !hello)
bot = commands.Bot(command_prefix='!')

@bot.event
async def on_ready():
    print(f'Bot connected as {bot.user}')

@bot.command()
async def hello(ctx):
    await ctx.send(f'Hello, {ctx.author.name}!')

@bot.command()
async def ping(ctx):
    await ctx.send('Pong!')

@bot.command()
async def echo(ctx, *, message):
    await ctx.send(message)

# Replace 'YOUR_TOKEN' with your actual Discord bot token
bot.run('YOUR_TOKEN')
