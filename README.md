# incredible-rosatom
Incredible solution which makes an optimal schedule

### Install all requirements

```
pip install matplotlib
```
Пайплайн программы состоит в следующем:
1) В третей ячейкe ```main.ipynb``` входой json-файл сериализирутся в объект класса ```DayData```
2) Предварительное равномерное распределение серий по печкам. Все серии помещаются в автомат, затем для каждой серии подбираются оптимальные печки-кандидаты по следующим факторам:
   а) Печки с операциями, необходимыми для серии
   б) -> Печки с начальной температурой равной температуре серии
   Среди кандидатов выбирается печка с наименьшей нагруженностью
3) Сортировка потока* в каждой печке с учетом ограничений (с 0:00 до 24:00, подряд идущие операции, смена температуры печи и т.п)
4) Запись выходных потоков в файл
5) Вычисление нагруженности всех печей
6) Визуализация решения

*Под потоком подразумевается массив распределенных серий под i-ую печку
