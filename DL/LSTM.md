Long Short-Term Memory - модель нейронной сети, которая управляет контекстом. То что не нужно - забывает. 
![[Pasted image 20250109145642.png]]
На картинке представлен блок lstm. Зеленая линия - это long-term память, красная - это short-term, её еще называют hidden state. 
Она использует *ворота* для контроля потока информации. Ворота имеют схожий паттерн дизайна:
каждая состоит из feed-forward слоя и использованием сигмоиды и поэлементным умножением со слоем, перед которым стоят ворота. Сигмоида используется для того, чтобы аутпут был либо 1 либо 0. Этот эффект схож с эффектом от применения бинарной маски.

**Первый** тип ворот - забывающие. Они удаляют информацию их контекста. Забывающие ворота находятся в голубом прямоугольнике.


**Второй** - добавляющие. 
Добавляющие ворота состоят из двух частей:
1. Часть, которая выбирает какую информацию запомнить из short-term памяти. Использует сигмоиду.
2. Часть, которая выбирает сколько нужно запомнить. Использует tanh функцию.
Добавляющие ворота находятся в зеленом и желтом прямоугольниках.

**Третий** - ворота выхода, которые решают, какая информация нужна для текущего hidden state.
На рисунке они обозначены фиолетовым и красным прямоугольниками.

Так как [[RNN]]  и [[LSTM]] не способны запоминать нормально всю информацию из прошлых состояний, придумали механизм [[Attension]].