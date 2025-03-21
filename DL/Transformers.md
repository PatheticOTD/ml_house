![[transformer_architecture.png]]

Трансформер - моделька, состоящая из стаков декодеров и енкодеров. 

Енкодер:
![[Pasted image 20250118093630.png]]
состоит из слоя [[Self-Attention]] и обычной фид форвард нейросети. Вообще, трансформеры используют сразу несколько attention heads. Каждая голова, по идее, отвечает за разные задачи: [[Multi-head Attention]].
Для того, чтобы трансформер понимал, что слова в предложении имеют порядок, применяют специальный [[Positional embedding]].

В целом, блок энкодинга можно представить, как поток, к которому присосался атеншн: ![[Pasted image 20250120095033.png]]
x_i - это энкодинг токена, а h_i - это аутпут.

Здесь мы два раза используем [[Layer Norm]].
Следует заметить, что единственный компонент енкодера, который берет инфу из предыдущих токенов - это мультихед атеншн. Получается, что можно представить, будто бы информация движется от одного потока, к другому.

Из-за того, что при вычислении матрицы $QK^T$ мы получим скоры для каждого квери значения и для каждого кей значения, используют [[Masking out the future]], так как модель не будет учиться предсказывать следующие слова, если уже знает ответ.

#### Language Modeling Head
Работа language modeling head-а заключается в том, чтобы на последнем слое трасформера из последнего n-ого токена предсказать токен n+1:
![[Pasted image 20250120124621.png]]
unembedding layer - это обычный линейный слой. E - это матрица эмбеддингов. Транспонированная E служит для того, что бы возвращать эмбединги обратно в вектора. 
![[Pasted image 20250120130318.png]]
