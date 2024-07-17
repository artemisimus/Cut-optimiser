# инструкция

Для того, чтобы создать план раскроя с помощью программы, надо ввести длины и количество деталей и заготовок, а также ширину пропила в текстовый файл “input.txt”. Каждую деталь нового типа необходимо вводить на новую строку. Отделять количество от длины необходимо через пробел или табуляцию. После ввода количества, весь последующий текст в строке будет игнорироваться.

### Структура файла input.txt:
первый блок данных – длины и количества деталей, второй блок данных – длины и количества заготовок. Каждый блок заканчивается вводом нуля.  В последней строке вводится ширина распила. 
Если во входных данных, при вводе длины, число слилось с буквой, то такая строка будет проигнорирована, а если слилось с количеством, то такая деталь будет учтена как одна.

#### Пример ввода в input.txt:
```
2550 6		// Вначале вводятся длины деталей
1550 3
690е	5	//Эта деталь не будет учтена, т.к. присутствует буквенная величина
590 4
290 0		//Если ввести 0 штук, то деталь будет исключена из плана
390		//Если не указать количество, то это воспримется, как одна деталь
490 10
0		//Конец ввода деталей
		//Пробельная строка не обязательна
5995 4		//Затем вводятся длины заготовок
0		//Конец ввода длин заготовок

2		// Ввод ширины пропила. «0» после - не нужен
		все последующие числа будут игнорироваться
```

Затем запускается программа, и после расчёта она сохраняет план в файл “output.txt”. 
В файле с выводом для каждой заготовки будет выводиться 2 ряда чисел. В 1-м будет набор длин вырезаемых деталей, а во 2-м — расстояния от начала заготовки, до конца детали.

#### Вывод в output.txt:
```
План раскроя:

Заготовка №1 (5995)
Детали:    2550; 1550;  690;  590;  590;                                                
От начала: 2550; 4102; 4794; 5386; 5978;

Заготовка №2 (5995)
Детали:    2550;  490; 1550;  590;  590;                                                
От начала: 2550; 3042; 4594; 5186; 5778;

Заготовка №3 (5995)
Детали:    2550; 2550;                                                            
От начала: 2550; 5102;

Заготовка №4 (5995)
Детали:    2550; 2550;                                                            
От начала: 2550; 5102;

Невместившиеся детали: 1550; 2550;
```

