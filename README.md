I want to tell you about near-duplicates.
Near-duplicate is object is similar to another object fully or partly.

Добрый день, дорогие коллеги.
Я расскажу о нечетких дубликатах видео.
Понятие «нечеткий дубликат» означает неполное или частичное
совпадение текущего документа (изображения) с другим документом
подобного класса.


There are natural and artificial near-duplicates.
Natural near-duplicates are similar objects within similar environment.
Artificial near-duplicates are objects, which were get form one 
original object.


Дубликаты бывают естественные и искусственные.
Естественные дубликаты --- схожие объекты, при схожих условиях.
Искусственные нечеткие дубликаты --- полученные
на основе одного и того же оригинала.


Firstly, Near duplicate retrieval may be helpful 
for optical navigations of cruise missiles or pilotless planes.
Secondly, for definition of properties of landscape.
Also, for grouping snippets of search engines.
More then that, it is necessary for video classification
and copyright management.

Поиск нечетких дубликатов может быть полезен
для оптической навигации беспилотных аппаратов,
для определения характера ландшфта местности,
составления каталогов видео,
группировки сниппетов поисковых систем,
фильтрация видео рекламы,
и поиска пиратского видео.

Near duplicates retrieval is connected to 
video classification and video content-based retrieval.
But this tasks are  independent.

Нечеткие дубликаты тесно связаны с
проблемами классификации видое и поиска по видео.
Но эти задачи являются самостоятельными.

Nowadays there are several ways to find near duplicates.
First one is based on global video features.
Another is based on local and global features of particular frames.
For example youtube.com use audio based approach
and licenzero use visual words.
Also the combinations of different methods are used.
На данный момент нечеткие дубликаты пытаются искать,
сравнивая глобальные особенности видео,
глобальные и локальные особенности кадров и множеств кадров.
Сравнивают звуковой ряд (так, например делюат в ютубе).
Ищут и сравнивают визуальные слова,
характерные последовательности (лицензЕро).
Используется комбинация методов.


We propose an algorithm of near duplicate video retrieval 
based on shot detection.

There are a lot of source videos.
Somebody gets to us some new video, 
and we should say is this new video a copy of
one or more of the source videos.
We compute scene descriptors for every shot 
of every source file and for new video.
Then compare this descriptors to each others.


 
Мы предлагаем алгоритм поиска нечетких дубликатов на основе сцен.
Есть множество исходных файлов,
для видео сцен этих файлов вычислены дескрипторы сцен.
Получаем новое видео.
Требуется установить является ли новое видео дубликатом существующих.
Вычисляем дескрипторы сцен этого видео .
Дескриптор каждой сцены нового видео сравниваем с каждым дескриптором
кадой сцены каждого исходного видео.


If several descriptors of some shots of a new video
are coincide with some shots of some source video, then 
these parts of videos are duplicates.
Else, the new video is unique.


Если на нектором временном промежутке дескрипторы совпали,
считаем, считаем, что временной промежуток является дубликатом
одной из частей исходного видео.
Если не несовпали ни на одном --- считаем видео уникальным.

A video is a collection of images known as frames. 
All of the frames within a single camera action are called a shot. 
A scene is one or more shots that form a semantic unit.
For example, a conversation between two people may be 
filmed such that only one person is shown at a time. 
Each time the camera appears to stop and move to 
the other person represents a shot change, but the
collection of shots that represent the entire conversation is a
scene. While some authors use the terms shots and scenes
interchangeably, typically when they use the term scene they
are really referring to a shot.

Что такое сцена?

Cуществует три различных   понятия.
Кадр, Фотографический кадр --- статическая картинка.
Сцена, монтажный кадр --- множество кадров связанных единством места и времени.
Съемка, кинематографических кадр, множество кадров связанных единством съемки.
1 сцена может включать несколько съемок.
Съемку часто называют <<сценой>>.
Далее мы будем рассматривать съемку, но называть  ее  будем <<сценой>>.


Shot is a sequence of frames, which are considerably different form
frames of anther sequence.
We can define audio shot in the same way.

Введем формальное определение.
Сцена-съемка, набор кадров определенной временной области 
кадры которой значительно отличаются от кадров соседних опластей.
Аналогичным образом можно ввести понятие звуковой сцены,
правда возникает отдельная проблема выделения звуковых-кадров.

Basically, there are three main ways to detect shots.
They are comparison histograms and spectrum of neighbour frames,
and comparison of optical flow.

Выделение сцен происходит на основе трех базовых подходов.
Это сравнение гистограм соседних кадров.
Сравнение спектров кадров
и сравнение векторов оптического потока.


You can see MTS ads on the slide.
Now we use ffmpeg for shot detection.

На слайде приведены первые кадры сцен рекламы на МТС,
выделенные c помощью ffmpeg.
ffmpeg использует сравнение гистограмм кадров.


If we compress this ad with different codecs
we'll take artificial near duplicates of the source ad.
The shot cuts for duplicates is different, as you can see on the picture.

In this case we propose using relative lengths of shots.
We should compute length ratio for every shot and compare this ratios.


Если исходную рекламу сжать разными кодеками,
мы получим нечеткие дубликаты этого видео.
Выделяя сцены в каждом видео, увидим, 
что точки перемены сцен для этих двух файлов
не совпадают.

We use longer source video and detect shots with more sense,
we'll see that several shots are not detected properly.

For practical tasks. It is more convenient to calculate the length ratio 
only for the three previous scenes.
Also, it is convenient if all the video entirely inaccessible, for example
if this is video stream.

If different shots of different videos has different length ratio, 
but no longer than twice, 
we propose that they may express the same action or object.

We can add length ratio of neighbour shots in one video
and consider this two shots like one complex shot.

The same method is used in computer linguistics 
for sense aliment in  bilingual corpora.
It is called Gale-Church algorithm.


Если взять более продолжительное видео,
и выделить сцены при более высокой чувствительности,
то можно заметить, что для разных кодеков
сцены определяются совсем не однородно.
Более того, некоторые сцены могут не распознаться.

Для решения этой проблемы мы предлагаем использовать
относительные длины сцен.
Для каждой сцены вычисляем отношение длины сцены
к длинам остальных сцен.
Для первых четрех сцен рекламы МТС получаем следующую матрицу.
В практических задачах удобнее вычислять отношения длин,
для трех предыдущих сцен.

Это удобно и вслучае, если все видео целиком нам недоступно.

Если относительная длина сцены одного видео
отличается от длины соответствующей сцены другого видео не более чем
в два раза, то можно предположить, что сцены выражают одно и то же
явление. В этом случае то длину
меньшей сцены можно сложить с длиной следующей сцены этого же
видео, и рассматривать объединенную сцену как одну.
Подобные метод называют алгоритмом Гейла-Черча.
Используется в математической лингвистике для выравнивания
праллельных корпусов тесктов на разных языках.


If length ratio for different shots of different videos are equal,
they are not, indeed, the same.
It is required to compare internal properties of these shots.
We use first and last frames.


Если относительные длины двух сцен совпали,
не факт что сцены действительно одинаковы.
Требуется сравнивать внутренние свойства сцен.
Можно взять начальные и конечные кадры.

There are several ways to compare appropriate frames.
In this case we use GIST and bag of visual words.



Сравнивать можно попиксельно,
на основе детектора краев.
В данном случчае удобно использовать
глобальные дескриптор GIST,
и мешок слов.

GIST is very simple but not strict global descriptor.
It is used in a lot amount of applications.
 
GIST представляем из себя простой но не очень
точный способ глобального описания изображения.
Применим для широкого круга задач.

Bag of visual words is usually more accurate with sufficient dictionary size.
But, it requires the learning set of images.
Bag of visual words is very good for specific tasks,
and bad for general purpose.
It is slower and takes rather more memory.


Мешок слов, обычно более точен, при достаточном размере словаря.
Необходимо, чтобы был набор изображений, на которых можно обучиться.
Хорош, если работа ведется только в рамках конкретной предметной области.
Но работает медленне и потенциально бесконечен по памяти.


Thereby, we get scene descriptor.
It consist of length ratio and properties of first and last frame of the scene 
(GIST of Bag of words).




Т.о. получили дескриптор сцены.
Он состит из вектора отношений длины сцены к длинам других сцен;
Его удобно сразу хранить, с объединениями соседних 
сцен учитывая гиппотезу Гейла Черча;
И характеристики начального и конечного кадров.
    В зависимоти от задачи мешок слов или GIST.


In the proposed algorithm  we directly compare scene descriptors.
This is inefficient way.

We propose  binary signature and semantic hashes.
They are required be close for close descriptors.

The most simple way is to use local sensitive hashes.
We divide space of descriptors with hyperplane.
For descriptors in different subspaces we randomly assign 0 or 1.
This way we get 1 bit of signature.
As the number of bits grows up, we approximate the source metric of descriptors.

Trainable hashes achieve better results, for this aims.
These include boosting and restricted Boltzmann machine.

It is used as a modification of boosting AdaBoost.
The purpose is to get those signatures, where distance are computed like 
the Hamming distance.

The Restricted Boltzmann machine is the probabilistic recurrent neural network.
It is also the probabilistic version of the Hopfield network and 
neural version of Hidden Markov Model.

We use modification without connections inside layers.
The power of layers falls from the size of the input vector 
to the size of the output code.

As a result of this work we have approach for near-dublicat video retrieval.
Firstly, It includes length ratios (relative lengths).
Secondly, we use scene aliment.
Thirdly, we propose scene descriptors.
Several experiments have been done.



Вернемся к предложеннуму алгоритмы.
Мы сравнивали дескрипторы на прямую в пространстве L2.
Но это не эффективно, для больших дескрипторов.

Можно предложить использование цифровых семантических подписей.
Введем бинарные подписи.
Подписи должны быть близки для близких дескипторах в L2.

Самое простое, что можно предложить:
Линейно чувствительные хеши.
Пространство дескрипторов, делим гиперплоскостью на 2 подпространства.
Назначаем дескрипторам этих подпространств подпись 0 или 1.
Получили бит подписи.
С увеличением числа бить ассимптотически приближаем метрику L2.
Для задач подобного рода лучше себя показали обучаемые хеши.
К ним относятся бустинг и ограниченная машина Больцмана.
В качесвтве бустинга исользуется модификация AdaBoost.
Цель --- получить такие подписи, расстояние между дескрипторами вычисляется,
будет вычисляться как расстояние Хемминга.

Ограниченная машина Больцмана:
Вероятностная рекурентная нейронная сеть.
Вероятностная версия сети Хопфилда.
Или нейросетевая версия Скрытой Модели Маркова.
Применяется модификация, без связей внутри слоев.
Мощность словем понижается  от размера входного вектора до размера
требуемого кода.


В результате проделанной работы:
был разработан подход поиска нечетких дубликатов видео на основе сцен.
Его основные моменты:
    относительные длины,
    выравнивания сцен на основе лингвистичского алгоритма Гейла-Черча,
    дескрипторы сцен;
Проведен ряд экспериментов, которые показали удобства подхода.

Далее нам требуется
    разработать собственный инструмент для поиск перемены,
    сейчас используется ffmpeg.
    лучше проработать схемы с использованием Больцмана
    Провести эксперименты на реальном множестве исxодных данных.













