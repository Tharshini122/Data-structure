#include <stdio.h>

int main() {
    int arr[5] = {2, 4 ,6,8,10};
    int choice, num, pos;

    printf("Array elements: ");
    for (int i = 0; i < 5; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");

    printf("Enter your choice:\n");
    printf("1. Insert\n");
    printf("2. Delete\n");
    printf("3. Search\n");
    printf("4. Update\n");
    scanf("%d", &choice);

    switch (choice) {
        case 1:
            printf("Enter number to insert: ");
            scanf("%d", &num);
            printf("Enter position: ");
            scanf("%d", &pos);
          
            for (int i = 4; i >= pos; i--) {
                arr[i] = arr[i - 1];
            }
            arr[pos - 1] = num;
            break;

        case 2:
            printf("Enter position to delete: ");
            scanf("%d", &pos);
            
            for (int i = pos - 1; i < 4; i++) {
                arr[i] = arr[i + 1];
            }
            break;

        case 3:
            printf("Enter number to search: ");
            scanf("%d", &num);
          
            int found = 0;
            for (int i = 0; i < 5; i++) {
                if (arr[i] == num) {
                    printf("Number found at position %d\n", i + 1);
                    found = 1;
                    break;
                }
            }
            if (!found) {
                printf("Number not found\n");
            }
            break;

        case 4:
            printf("Enter position to update: ");
            scanf("%d", &pos);
            printf("Enter new number: ");
            scanf("%d", &num);
          
            arr[pos - 1] = num;
            break;

        default:
            printf("Invalid choice\n");
    }

    printf("Updated array: ");
    for (int i = 0; i < 5; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");

    return 0;
}
