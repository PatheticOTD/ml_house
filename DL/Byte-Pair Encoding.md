В начале [[Token learner]] находит два символа, которые чаще других встречаются вместе. Соединяет их в один и заменяет им каждые два встречающихся рядом символа. И так делает k раз.
В конце [[Token segmenter]] проходится по тестовой выборке и преобразует символы в токены, в таком порядке, в каком были добавлены в словарь токены токен лернером.