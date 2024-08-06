[[rmsprop]], [[adagrad]], [[sgd with momentum]], [[sgd with nesterov momentum]] и тд имеют один недостаток, они не гарантируют нахождение глобального минимума. 

![[Screenshot from 2024-08-06 17-28-22.png]]

Адам (adaptive moment estimation) - модификация рмс пропа, в формулу рмс прома решили добавить импульс. причем оба 