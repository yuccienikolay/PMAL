# PMAL
Polygon Model and Attachments for Love2d engine.

__PMAL__ - это контейнер вида model.pmal, содержащий свойства и связи с объектами, для упрощенного моделирования и привязки двухмерных моделей к физическому _Box2d._

## В репозитории
- PASTLEME.lua - функция, котороя расшифровывает контейнер. Возращает обеъект `Drawable` и `Body`. __Подробная инструкция ниже__
__В релизе находится генератор PMAL файлов__

## В контейнер входят:
- Функция возврата данных `return`, чтоб обеспечить простоту извлечения контейнера.
- Данные о построении [выпуклых](https://ru.wikipedia.org/wiki/%D0%92%D1%8B%D0%BF%D1%83%D0%BA%D0%BB%D1%8B%D0%B9_%D0%BC%D0%BD%D0%BE%D0%B3%D0%BE%D1%83%D0%B3%D0%BE%D0%BB%D1%8C%D0%BD%D0%B8%D0%BA "Выпуклый многоугольник") многоугольных мешей в виде: `{1,1, 2,2, 3,8, ... xn,yn}`
- Данные о представлении многоугольников в `love.draw()` _(разделяются запятой)_:
    1. Метод отрисовки: `fill` или `line`
    2. Цвет отрисовки в hex представлении.
- Данные для привязки изображения к мешу _(могут быть не указаны, в случае отсутствия изображения)_:
    1. Имя файла изображения __(изображение должно находится в той же директории, что и файл pmal!)__
    2. Ширина изображения. Для точного наложения на меш.
    3. Высота изображения. Для точного наложения на меш.
    4. X оффсет изображения. Для точного наложения на меш.
    5. Y оффсет изображения. Для точного наложения на меш.
    __ПРИ ОТСУТСТВИИ ДАННЫХ ОФФСЕТА БУДЕТ ВЗЯТЫ ПОЛОВИНЫ ШИРОТЫ И ВЫСОТЫ ИЗОБРАЖЕНИЯ. ПРИ ОТСУТСТВИИ ДАННЫХ ВЫСОТ И ШИРОТ ИЗОБРАЖЕНИЯ, БУДУТ ИСПОЛЬЗОВАТЬСЯ ИХ РАЗМЕР В ПИКСЕЛАХ__

## Пример данных
__то есть все данные которые в себе содержит контейнер .pmal__
_для изображения трехугольника:_
`return {1,0, 1,-1, -1,1}, "fill", "#cacaba"`
`return {1,0, 1,-1, -1,1}, "triangleface.png"` 
`return {1,0, 1,-1, -1,1}, "triangleface.png", 15, 15, 5, 5`
