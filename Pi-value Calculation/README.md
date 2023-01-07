# Pi-value Calculation
В данной лабораторной работе был реализован алгоритм вычисления чилса **pi** методом Монте-карло на CPU и GPU. 
</br>
Для генерации случайного числа от 0 до 1 использовались следующие функции:
</br>
GPU - *xoroshiro128p_uniform_float32()* из библиотеки numba.cuda.random.
</br>
CPU - *random.uniform()* из библиотеки numpy.
</br>
Также для генерации случайных массивов на GPU была использованная функция create_xoroshiro128p_states() из библиотеки numba.cuda.random.
</br>
Ниже представленны полученные результаты:
</br>
![image](https://user-images.githubusercontent.com/83270014/211166438-4dfc2f35-5796-453d-9667-18449d194192.png)
</br>

</br>
![image](https://user-images.githubusercontent.com/83270014/211166485-e067e289-b2bb-4320-9e4f-abf7424250bf.png)
</br>
Первое значение времени выполнение на GPU выбивается из общей картины, возможно причиной этому служит задержка перед передачей данных GoogleColab, так как это повторяется из раза в раз.
</br
Также было посчитано ускорение:
</br>
![image](https://user-images.githubusercontent.com/83270014/211166532-54670e5a-fae0-4603-8082-2e2a9428e1c8.png)
</br>
график:
</br>
![image](https://user-images.githubusercontent.com/83270014/211166541-6824622b-2b5f-464e-be96-8bcd9fa1abeb.png)
</br>
Можем наблюдать, что вычесления на GPU идут быстрее с увеличением кол-ва случайных точек. Значение же числа **pi** на 401000 случайных точек можно считать удовлетворительным  (GPU - 3.144549, CPU - 3.145327). 
</br>
Код для вычисления на CPU находится в файле *Pi-value_Calculate_CPU.ipynb*. </br>
Код для вычесления на GPU находится на [Google Drive](https://colab.research.google.com/drive/1lCFZINNCBIYgrft1BRHGqxg1X25Ds5vo#scrollTo=GdNc62npJztP).
