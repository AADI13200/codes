EXPERIMENT 1


#include <stdio.h>

// Function for Linear Search
int linearSearch(int arr[], int n, int key) {
    for (int i = 0; i < n; i++) {
        if (arr[i] == key)
            return 1;  // Found
    }
    return 0;  // Not found
}

// Function for Binary Search
int binarySearch(int arr[], int n, int key) {
    int low = 0, high = n - 1, mid;
    while (low <= high) {
        mid = (low + high) / 2;
        if (arr[mid] == key)
            return 1;
        else if (arr[mid] < key)
            low = mid + 1;
        else
            high = mid - 1;
    }
    return 0;
}

int main() {
    int arr[100], n, key, choice, found;

    printf("Enter number of students who attended the training: ");
    scanf("%d", &n);

    printf("Enter roll numbers of students:\n");
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }

    printf("\n--- Menu ---\n");
    printf("1. Linear Search (Random Order)\n");
    printf("2. Binary Search (Sorted Order)\n");
    printf("Enter your choice: ");
    scanf("%d", &choice);

    printf("Enter roll number to search: ");
    scanf("%d", &key);

    switch (choice) {
        case 1:
            found = linearSearch(arr, n, key);
            if (found)
                printf("Student attended the training program (Found using Linear Search).\n");
            else
                printf("Student did NOT attend the training program.\n");
            break;

        case 2:
            found = binarySearch(arr, n, key);
            if (found)
                printf("Student attended the training program (Found using Binary Search).\n");
            else
                printf("Student did NOT attend the training program.\n");
            break;

        default:
            printf("Invalid choice.\n");
    }

    return 0;
}
