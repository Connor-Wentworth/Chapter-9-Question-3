#include <iostream>
using namespace std;

void sortScores(int* arr, int size);
double calculateAverage(int* arr, int size);

int main()
{
    int arr[10] = {};
    int* nums = arr;

    cout << "Enter 10 numbers:\n";

    for (int i = 0; i < 10; i++) {
        cin >> nums[i];
    }

    // Sort the array first
    sortScores(arr, 10);

    // Calculate average with lowest score dropped
    double average = calculateAverage(arr, 10);

    cout << "\nThe numbers in increasing order are:\n";

    for (int i = 0; i < 10; i++) {
        cout << nums[i] << " ";
    }

    cout << "\n\nLowest score dropped: " << arr[0];
    cout << "\nAverage score (without lowest): " << average << endl;

    return 0;
}

void sortScores(int* arr, int size)
{
    for (int i = 0; i < size - 1; i++) {
        for (int j = i + 1; j < size; j++) {

            // Swap if numbers are out of order
            if (*(arr + i) > *(arr + j)) {

                int temp = *(arr + i);
                *(arr + i) = *(arr + j);
                *(arr + j) = temp;
            }
        }
    }
}

double calculateAverage(int* arr, int size)
{
    int sum = 0;

    // Start at index 1 to skip the lowest score
    for (int i = 1; i < size; i++) {
        sum += *(arr + i);
    }

    // Divide by size - 1 because one score was dropped
    return static_cast<double>(sum) / (size - 1);
}
