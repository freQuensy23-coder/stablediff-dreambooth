![](https://github.com/freQuensy23-coder/stablediff-dreambooth/blob/main/images/animation1.gif?raw=true)

(Нажмите [сюда](https://giphy.com/gifs/0h8BstKmNNgtrvZ7w5/fullscreen) если github не возпроизводит gif)

_Попробовать модель можно в huggingface spaces - [freQuensy23/diffusion-cloody](https://huggingface.co/freQuensy23/diffusion-cloody)_

**DreamBooth** - это технология позволяющая  до обучить диффузионную модель качественно генерировать картинки какого-то конкретного объекта (например героя своего комикса или домашнего животного) обучившись на небольшом наборе его фотографий.
При стандартном до обучении мы обозначаем наш обобьет каким то именем, которого  нет в промптах к исходной обучающей выборке модели (например \[V\]) и просто до обучаем ее веса.
Однако такой подход имеет две проблемы (которые были решены в данной статье)
1. **language drift** - модель предварительно обученная на большом корпусе текста и позже точно настроенная для конкретной задачи, постепенно теряет синтаксические и семантические знания языка. 
2. **Уменьшения разнообразия выходных данных.** Модели преобразования текста в изображение естественным образом обеспечивают большое разнообразие выходных данных. При точной настройке мы хотели бы иметь возможность создавать объект в новых ракурсах, позах. Однако из за переобучения вариативность выходных поз объекта сокращается.

![](https://github.com/freQuensy23-coder/stablediff-dreambooth/blob/main/images/Pasted%20image%2020230825160512.png?raw=true)

**Как мы видим на данном изображении из-за наличия в дообучающем датасете только фотографий сидячих собак, модель не может сгенерить ее в другом ракурсе, потому что забыла что собаки могут находиться и в других позах.** 

# Основная идея
Авторы статьи решают эту задачу дополнительным лоссом - class-specific prior preservation loss. Вначале обучаемая модель пытаться сгенерировать нашу собаку, и обучается по лоссу с фотографиями из выборки для дообучения. Затем она же генерирует произвольную собаку, и лосс считается с фотографиями, сгенерированными 
исходной моделью. **Таким образом, мы наказываем модель, за то что она забывает абстрактные признаки собак, концентрируясь на обучающей выборке.** Более лаконично на схеме:

![](https://github.com/freQuensy23-coder/stablediff-dreambooth/blob/main/images/Pasted%20image%2020230826014413.png?raw=true)

Или более строго:

```math
\begin{aligned}
& \mathbb{E}_{\mathbf{x}, \mathbf{c}, \boldsymbol{\epsilon}, \boldsymbol{\epsilon}^{\prime}, t}\left[\right.  \left.\lambda w_{t^{\prime}}\left\|\hat{\mathbf{x}}_\theta\left(\alpha_{t^{\prime}} \mathbf{x}_{\mathrm{pr}}+\sigma_{t^{\prime}} \boldsymbol{\epsilon}^{\prime}, \mathbf{c}_{\mathrm{pr}}\right)-\mathbf{x}_{\mathrm{pr}}\right\|_2^2\right]
\end{aligned}
```

# Результаты авторов
Как видно из картинок ниже, добавление class-specific prior preservation loss очень позитивно сказалось на возможности модели генерить исходный обьект в разных позах

![](https://github.com/freQuensy23-coder/stablediff-dreambooth/blob/main/images/Pasted%20image%2020230826022559.png?raw=true)

![](https://github.com/freQuensy23-coder/stablediff-dreambooth/blob/main/images/Pasted%20image%2020230826022737.png?raw=true)

Так же модель научилась видоизменять обьект в зависимости от промпта, генерируя полностью новые объекты на основе существующего:

![](https://github.com/freQuensy23-coder/stablediff-dreambooth/blob/main/images/Pasted%20image%2020230826023753.png?raw=true)
При этом сама модель не потеряла возможности генерировать обычные объекты (произвольных собак, отличных от той, на которой происходило до обучение)

![](https://github.com/freQuensy23-coder/stablediff-dreambooth/blob/main/images/Pasted%20image%2020230826113847.png?raw=true)

А так же такой подход очень хорошо сработал для задач style-transfer. Авторы смогли сгенерировать картинки в разных стилях, но с исходным обьектом

![](https://github.com/freQuensy23-coder/stablediff-dreambooth/blob/main/images/Pasted%20image%2020230826120014.png?raw=true)

# LoRA
При обучении модели нет смысла обучать все её веса, достаточно обучения небольших адаптеров. Подробнее о том как это работает написано в [моей статье на хабре.](https://habr.com/ru/articles/747534/)
# Воспроизведение результатов
Я до обучил [stable-diffusion-v1-5](https://huggingface.co/runwayml/stable-diffusion-v1-5) на двух собственных датасетах - [фотографии кошки (cloody-cat)](https://huggingface.co/datasets/freQuensy23/cloody-cat) и декоративного гриба.  Интерактивная демонстрация работы моей модели на hf -  [freQuensy23/diffusion-cloody](https://huggingface.co/freQuensy23/diffusion-cloody)
Весь код находится в данном репозитории. См [инструкцию](https://github.com/freQuensy23-coder/stablediff-dreambooth/edit/main/README.md) по развертыванию что бы повторить результат. 
