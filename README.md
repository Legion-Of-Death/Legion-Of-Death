```python
import discord
import requests
from bs4 import BeautifulSoup

TOKEN = "1128426752646066238"
CHANNEL_ID =1112654203102437462

client = discord.Client()

@client.event
async def on_ready():
    print("Бот готов к работе")

@client.event
async def on_message(message):
    if message.author == client.user:
        return
    
    if message.content.startswith("!скидки"):
        books = get_discounted_books()
        
        if books:
            await message.channel.send("Книги со скидкой:")
            for book in books:
                await message.channel.send(f"Название: {book['title']}, Автор: {book['author']}, Скидка: {book['discount']}%")
        else:
            await message.channel.send("Увы, книг со скидкой не найдено")
    

def get_discounted_books():
    books = []
    
    # код для мониторинга книжных онлайн магазинов и получения информации о книгах со скидкой
    
    return books

client.run(1128426752646066238)
``
