# schowz.jr
import discord
import random
from discord.ext import commands

intents = discord.Intents.default()
intents.message_content = True

bot = commands.Bot(command_prefix='$', intents=intents)

@bot.event
async def on_ready():
    print(f'Estamos logados como {bot.user}')

@bot.command()
async def hello(ctx):
    await ctx.send(f'Olá! eu sou o bot {bot.user}!')

@bot.command()
async def sigma(ctx):
    await ctx.send(f' 🤫 🧏‍♂️  !')

@bot.command()
async def eai_bot(ctx):
    await ctx.send(f'Olá! eu sou o bot {bot.user}!')

@bot.command()
async def heh(ctx, count_heh = 5):
    await ctx.send("he" * count_heh)

@bot.command()
async def conhecer(ctx,nome="desconhecido",idade="desconhecida",cidade ="desconhecida" ):
    await ctx.send(f"Olá,{nome},que tem {idade} anos e mora em {cidade}")

@bot.command()
async def  como_você_esta(ctx):
    emoji_list = ["😀", "😂", "😎", "🤔", "🔥", "👍"] 
    chosen_emoji = random.choice(emoji_list)
    await ctx.send(f'Eu estou:',chosen_emoji)

    
memes = ["https://cdn.discordapp.com/attachments/1445871504616194079/1467057024885063855/RDT_20260130_1205496604839311278130901.gif?ex=6abc0f93&is=6ababe13&hm=484e4b1670ed3a6c8cd1123f04bfc297aab8d26511f15e8b806b70a12cf17aec",
         "https://tenor.com/view/roblox-bacon-hair-bacon-hair-dance-gif-18121336341116932036",
         "https://tenor.com/view/dog-bird-flying-gif-17884683403270491620",
         "https://tenor.com/view/partying-cat-party-cat-cute-cat-kitten-gif-22225605",
         "https://tenor.com/view/roblox-meme-gif-26540500",
         "https://tenor.com/view/resenha-alerta-cachorro-gif-gif-10267911655190229974","https://klipy.com/gifs/rat-mouse-21"]

@bot.command()
async def meme(ctx):
    await ctx.send(random.choice(memes))


