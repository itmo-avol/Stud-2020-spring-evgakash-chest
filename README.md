# game-server

Пример-основа для пошаговой игры на нескольких игроков.

Содержит в себе сервер HTTP для выдачи статики, и WebSocket для поддержания соединения с игроками.

В примере, каждый игрок последовательно загадывает число. Побеждает тот, чьё число будет наибольшим.

Игра запускается на двух игроков, но это настраивается в константе `PLAYERS_IN_SESSION` файла `server/game/game.ts`. Сервер последовательно соединяет двух подключившихся клиентов в игру.


npm run build - игра собирается
npm run start - можно начинать играть 
в браузере пишем: http://localhost:8000/

Правила: 
    Задача: набрать как можно больше сундучков (4 карты одного значения);
    Начало: игра начинается, когда подключаются 2 игрока. Раздаётся каждому по 4 карты.
    Ход: В углу экрана отображется надпись, обозначающая твой ход или противника.
        Если не твой, то ждёшь пока противник ошибётся.
        Если твой, то выбираешь карту из своей стороны. Значение из этой карты будет спрашиваться у другого игрока.
        Если такое значение есть у соперника, то дальше выбираешь количество таких карт, который возможно у него есть.
        Если угадал количество, то угадываешь сколько у него красных и чёрных карт.
        Если угадал количество чёрных и красных, то угадываешь масть.
        Если угадал, то тыполучаешь карту соперника, он же, соответственно, её теряет.
        Если у тебя на руках 4 карты одного значения, то они автоматически удаляются и становятся сундучком.
        Если на какаом-то из этапов ты не угадал, то получаешь карту из колоды и ход переходит к другому игроку.
    Конец: игра заканчивается, если один из играков прервал игру или сумма сундучков обоих стала равна 9
#   g a m e - s e r v e r  
 #   g a m e - s e r v e r  
 #   g a m e - s e r v e r  
 #   g a m e - s e r v e r  
 #   g a m e - s e r v e r  
 