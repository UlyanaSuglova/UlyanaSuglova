import asyncio
import config
from aiogram import Bot, Dispatcher, types, F
from aiogram.filters.command import Command
import logging
import random
from keyboards import keyboard

#Логирование
logging.basicConfig(level=logging.INFO)

# Объект бота и диспетчера
bot = Bot(token=config.token)
dp = Dispatcher()

@dp.message(Command(commands=['старт', 'start']))
@dp.message(F.text.lower()=='старт')
async def start(message: types.Message):
    await message.answer(f'Привет, {message.from_user.full_name}! Я тестовый бот для домашнего задания на курсе "Нейрохищник". В свободное время обожаю смотреть сериалы, времени у меня мало, поэтому коллекция еще только пополняется. Напиши мне жанр - детектив, ужасы, фантастика или триллер. Я обязательно тебе что-нибудь подберу! Если хочешь завершить наше общение, напиши - стоп. Либо воспользуйся меню', reply_markup=keyboard)

@dp.message(Command(commands=['стоп', 'stop']))
@dp.message(F.text.lower()=='стоп')
async def stop(message: types.Message):
    print(message.from_user.full_name)
    await message.answer(f'До скорых встреч, {message.chat.first_name}!')

@dp.message(Command(commands=['детектив', 'detective']))
@dp.message(F.text.lower()=='детектив')
@dp.message(F.text.lower()=='detective')
async def detective(message: types.Message):
    print(message.from_user.full_name)
    await message.answer(f'Думаю сериал "Шерлок" тебе точно понравится! Готов побыть Ватсоном и помочь в разгадке тайн?')

@dp.message(Command(commands=['ужасы', 'horrors']))
@dp.message(F.text.lower()=='ужасы')
@dp.message(F.text.lower()=='horrors')
async def horrors(message: types.Message):
    print(message.from_user.full_name)
    await message.answer(f'Постапокалиптическое будущее в сериале "Одни из нас" удивляет, пугает и ... Советую посмотреь своими глазами!')

@dp.message(Command(commands=['фантастика', 'fantasy']))
@dp.message(F.text.lower()=='фантастика')
@dp.message(F.text.lower()=='fantasy')
async def fantasy(message: types.Message):
    print(message.from_user.full_name)
    await message.answer(f'После сериала "Разделение" задумываешься, а готов ли ты отделить хирургическим путем рабочие воспоминания от личных...')

@dp.message(Command(commands=['триллер', 'thriller']))
@dp.message(F.text.lower()=='триллер')
@dp.message(F.text.lower()=='thriller')
async def thriller(message: types.Message):
    print(message.from_user.full_name)
    await message.answer(f'Хочешь разгадать тайну загадочного преступления из сериала "Переполненная комната"? Тогда почему ты еще тут? Скорее включай!')

@dp.message(F.text)
async def msg(message: types.Message):
    if 'детектив' in message.text.lower():
        await message.reply('Думаю сериал "Шерлок" тебе точно понравится! Готов побыть Ватсоном и помочь в разгадке тайн?')
    elif 'ужасы' in message.text.lower():
        await message.reply('Постапокалиптическое будущее в сериале "Одни из нас" удивляет, пугает и ... Советую посмотреь своими глазами!')
    elif 'фантастика' in message.text.lower():
        await message.reply('После сериала "Разделение" задумываешься, а готов ли ты отделить хирургическим путем рабочие воспоминания от личных...')
    elif 'триллер' in message.text.lower():
        await message.reply('Хочешь разгадать тайну загадочного преступления из сериала "Переполненная комната"? Тогда почему ты еще тут?')
    else:
        await message.reply('Не понимаю тебя...Возможно, эта команда мне еще не доступна, но обещаю скоро научиться. А пока можешь воспользоваться меню.')



async def main():
    await dp.start_polling(bot)


if __name__ == '__main__':
    asyncio.run(main())
