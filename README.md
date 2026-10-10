# daily-budget-content

Еженедельный «пакет» развлекательных выпусков для приложения «Б» (our-daily-budget.web.app).

- `packs/latest.json` — текущий пакет, его читает приложение (raw.githubusercontent.com).
- `packs/YYYY-wNN.json` — архив по неделям.

Пакет содержит только общий контент: никаких личных данных. Выпуски по данным пользователя собираются в самом приложении.

## Формат
```
{ "v":1, "week":"YYYY-MM-DD (понедельник)", "until":"YYYY-MM-DD", "city":"Москва",
  "episodes":[{ "id", "topic", "title", "theme", "days":[0-6]?, "from"?, "to"?,
     "slides":[{ "k":"надзаголовок", "t":"заголовок", "s":"текст", "art":"ключ иллюстрации",
                 "img":"wiki:ru:Название_статьи"?, "link":{"u","l"}?, "quiz":{"o":[...],"a":0,"why"}?,
                 "swatch":["#hex"]?, "end":1? }],
     "src":[...] }]}
```
Темы (`topic`): city, news, nature, art, recipe, quiz, holiday, selfcare, garden, design, joke, travel, music, movie, photo, word.
Иллюстрации (`art`): city, thread, eiffel, palette, film, sparkle, sun, turtle, owl, leaf, stars, comet, moon, pumpkin, pot, spoon, question, bread, wheat, breath, tulip, cup, heart, scale, cloud, rain, trophy, chart, dumbbell, wallet, fork, calendar, а также крупные картинки eye, pizza, donut, plate. Неизвестный ключ покажется как sparkle. Фон-фотография слайда: `"bg":"wiki:ru:Название_статьи"` (картинка статьи Википедии) или `"commons:Файл.jpg"`, подпись источника — `"cr"`. На таком слайде иллюстрация `art` не показывается, текст внизу поверх фото. Тема `photo` — красивые фотографии мест и природы. Признак `"end":1` ставится на уровне слайда; последний слайд эпизода всегда считается финальным.

Темы оформления (`theme`): violet, sunset, mint, peach, sky, sun, gold, night, berry, forest.
