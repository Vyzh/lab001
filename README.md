/*
* lab01.cpp - главный файл проекта.
* Copyright (C) 2013 Выжгин Д.Ю. <Vyzhgin.dima@yandex.ru>
*
* Данная программа решает задачу табулирования функции.
* Дата последней редакции 13.09.2015
* Программа доступна по лицензии GNU
*/
 
#include <stdio.h> //Подключение заголовочного файла библиотеки ввода/вывода
#include <locale.h> //Подключение заголовочного файла библиотеки для работы с локалями
#include <windows.h> //Подключение заголовочного файла системной библиотеки
#include <math.h>//Математические функции
#include <ctime>//время
#include <iostream>//функции прямого потока
#define param 10 //Предопределяем значение параметра функции
 
float f(float x, float a)
/*
* Функция f(x,a) возвращает значение функции  для заданных a и x.
* Формат вызова f(x,a)
*/
{
return (x+(15/(x*x+3)));
} //конец функции f(x,a)
 using namespace std;
int main()
{
 float begin, //Левая граница интервала
 end, //Правая граница интервала
 x, //Аргумент функции
 h; //Шаг табулирования
 int n; //Количество интервалов разбиения
 //Установление кодировки
 setlocale( LC_ALL,"Russian" );
 printf("Выжгин Дмитрий Юрьевич,1 курс,ФИиТ,1Б\n");
 printf("Введите левую границу интервала: ");
 scanf("%f",&begin);
 printf("Введите правую границу интервала: ");
 scanf("%f",&end);
 printf("Введите количество точек разбиения: ");
 scanf("%d",&n);
 h=(-begin+end)/n;
 x=begin;
 printf(" x \t \t f(x)\n");
 while (x<=end)
 {
printf(" %f \t %f\n",x,f(x, param));
 x=x+h;
 }//end while (x<=end)
 time_t t;
t=time(0);
cout << puts(ctime(&t)); 
 system("PAUSE");
 return EXIT_SUCCESS;
}//конец функции main()
