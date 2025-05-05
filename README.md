1)
#include <iostream>

int main() {
    int size = 5;
    int* array = new int[size] {1, 2, 3, 4, 5};

    size--;

    std::cout << "After Deleted in end: ";
    for (int i = 0; i < size; ++i)
        std::cout << array[i] << " ";

    delete[] array;
}
2)
#include <iostream>

int main() {
    int size = 4;
    int* array = new int[size] {1, 2, 4, 5};

    int newElement = 3;
    int insertIndex = 2;

    int* newArray = new int[size + 1];

    for (int i = 0; i < insertIndex; ++i)
        newArray[i] = array[i];

    newArray[insertIndex] = newElement;

    for (int i = insertIndex; i < size; ++i)
        newArray[i + 1] = array[i];

    delete[] array;
    array = newArray;
    size++;

    std::cout << "After addition: ";
    for (int i = 0; i < size; ++i)
        std::cout << array[i] << " ";

    delete[] array;
}
