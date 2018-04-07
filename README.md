# bubbleAndSelectionSort
Two different types of sorting algorithms
#include "stdafx.h"
#include<iostream>
using namespace std;

void bubbleSort(int[], int); 		//in prototype dont use variable names, only types.
void selectionSortArray(int[], int);
void showArray(const int[], int);

const int SIZE = 8;

int main()
{
	int numbersListA[SIZE] = { 105,102,107,103,106,100,104,101 };
	int numbersListB[SIZE] = { 105,102,107,103,106,100,104,101 };
	bubbleSort(numbersListA, SIZE);
	selectionSortArray(numbersListB, SIZE);
	system("pause");
	return 0;
}

void bubbleSort(int array[], int elements)  //in function definition the parameters can be renamed when passing by value
{
	cout << "Now performing the bubble sort" << endl;
	cout << "------------------------------" << endl;
	bool swap;
	int temp;
	int count = 1;
	do
	{
		swap = false;
		for (int i = 0; i < (elements - 1); i++)
		{
			if (array[i] > array[i + 1])
			{
				temp = array[i];
				array[i] = array[i + 1];
				array[i + 1] = temp;
				swap = true;
			}
			cout << "After pass " << count << ":  ";
			showArray(array, SIZE);
			count = count + 1;
		}

	} while (swap); 	//end do-while loop
}

void selectionSortArray(int array[], int elements)
{
	int minCount, minValue;
	cout << "\n\nNow performing the selection sort" << endl;
	cout << "---------------------------------" << endl;

	for (int i = 0, counter = 1; i<(elements - 1); i++, counter++)
	{
		minCount = i;
		minValue = array[i];

		for (int j = i + 1; j<elements; j++)
		{
			if (array[j] < minValue)
			{
				minValue = array[j];
				minCount = j;
			}
		}
		array[minCount] = array[i];
		array[i] = minValue;
		cout << "After pass " << counter << ": ";
		showArray(array, elements);
	}
}

void showArray(const int array[], int SIZE)
{
	for (int i = 0; i<SIZE; i++)
		cout << array[i] << " ";
	cout << endl;
}
