//# LIST-STL-C-stl-
//LIST | STL C++ | Библиотека стандартных шаблонов (stl). Обучение С++
#include<iostream>
#include<list>
using namespace std;	
template<typename T>
void PrintList(const list<T> &lst)
{
	for (auto i = lst.cbegin(); i != lst.cend(); ++i)
	{
		cout << *i << endl;
	}
}
//ф-ция принимает конст ссылку на лист, чтоб не могли ничего изменить
//итерация с помощью префиксного инкремента


int main() 
{
	/*list<int> myList;*/
	list<int> myList = { 2,5,89 };//list<int> myList;
	myList.push_back(5);// добавить эл-т в к. списка
	myList.push_front(151);// добавить эл-т в начало  списка
	myList.sort();//сортиурет от наименьшего эл-та к наибольшему
	myList.pop_back();//удаляет послед эл-т списка
	myList.pop_front();//удаляет первый эл-т списка
	cout << myList.size() << endl;//выводит кол-во элементов в списке



	PrintList(myList);
	list<int>::iterator it = myList.begin();//создаем итератор
	//auto it=myList.begin(); можно так
	cout << *it << endl;//151

	for (auto i = myList.begin(); i !=myList.end(); i++)
	{
		cout << *i << endl;
	}


	return 0;
}

int main()
{

	list<int> myList = { 99, 2,87,99,5,89,99,99,99 };
	myList.unique();//удаляет все дубликаты(одинаковые числа), кторые идут последовательно
	myList.reverse();//вывод элементов в обратном порядке
	/*myList.clear();*///очистить
	auto it = myList.begin();//итератор н. для метода insert
	++it;//добавим уже не на первый эл-т, а на второй
	//it += 3; на нескоько эл-в лист сдвинуть нельзя как вектор, для этого  есть advance
	advance(it, 3);// парам 1 -где сдвинуть, парам 2 -на какой эл-т
	myList.insert(it,111);//парам 1-куда вставляем, парам 2-что вставляем, для этого метода н. итератор
	myList.erase(it);//удаляет эл-т, работает как insert

	myList.remove(99);//удаляет конкретное число,если оно есть в списке
	myList.assign(3,1565);//заполняет лист элементами,причем те, что были удалет.
	//парам 1 -кол-во элементов,которыми будем заполнять лист,парам 2 -
	//значение элементов,которыми б.заполнять лист
	
	PrintList(myList);

	return 0;
}

int main()
{

	list<int> myList = { 99, 2,87,99,5,89, };
	list<int> myList2 = { 8,55,12};
	myList.assign(myList2.begin(), myList2.end());//все элементы второго листа скопируем в первый
	/*myList.assign(3, 1565);*///заполняет лист элементами,причем те, что были удалет.
	//парам 1 -кол-во элементов,которыми будем заполнять лист,парам 2 -
	//значение элементов,которыми б.заполнять лист

	PrintList(myList);

	return 0;
}
