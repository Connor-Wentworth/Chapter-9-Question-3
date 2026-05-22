#include <iostream>
using namespace std;

void sortScores(int* arr, int size);

int main()
{
    int arr[10] = {};
    int* nums = arr;

    cout << "Enter 10 numbers:\n";

    for (int i = 0; i < 10; i++) {
        cin >> nums[i];
    }

    // Sort the array
    sortScores(arr, 10);

    cout << "\nThe numbers in decreasing order are:\n";

    for (int i = 0; i < 10; i++) {
        cout << nums[i] << " ";
    }

    return 0;
}

void sortScores(int* arr, int size)
{
    for (int i = 0; i < size - 1; i++) {
        for (int j = i + 1; j < size; j++) {

            // Swap if numbers are out of order
            if (*(arr + i) < *(arr + j)) {

                int temp = *(arr + i);
                *(arr + i) = *(arr + j);
                *(arr + j) = temp;
            }
        }
    }
}
