# STUDENT-REPORT
#include <stdio.h>
struct student {
    int roll;
    char name[20];
    int marks;
    char course[50];
};
int main() {
    int n, s;
    char ch, a;
    printf("Enter the number of entries you want to enter: ");
    scanf("%d", &n);
    struct student detail[n];
    for (int i = 0; i < n; i++) {
        printf("\nDetails of student %d: ", i + 1);
        printf("\nRoll Number: ");
        scanf("%d", &detail[i].roll);
        printf("Name: ");
        scanf("%s", detail[i].name);
        printf("Marks: ");
        scanf("%d", &detail[i].marks);
        printf("Course/Department: ");
        scanf("%s", detail[i].course);
    }
    for (int i = 0; i < n; i++) {
        printf("\nDetails of student %d:\n", i + 1);
        printf("Roll Number       : %d\n", detail[i].roll);
        printf("Name              : %s\n", detail[i].name);
        printf("Marks             : %d\n", detail[i].marks);
        printf("Course/Department : %s\n", detail[i].course);
    }
search_again:
    printf("\nDo you want to search details of any student? (Y / N)\n");
    scanf(" %c", &ch);
    if (ch == 'Y' || ch == 'y') {
        printf("Enter the Roll Number you want to search: ");
        scanf("%d", &s);
        for (int i = 0; i < n; i++) {
            if (s == detail[i].roll) {
                printf("\nRoll Number found. The details of the student are:\n");
                printf("Roll Number       : %d\n", detail[i].roll);
                printf("Name              : %s\n", detail[i].name);
                printf("Marks             : %d\n", detail[i].marks);
                printf("Course/Department : %s\n", detail[i].course);
            } 
            else{
                printf("The Roll Number you searched is not there.");
            }
            printf("\n\nDo you want to search again? (Y / N): ");
            scanf(" %c", &a);
            if (a == 'Y' || a == 'y') {
                goto search_again;
            }
        }
    }
    printf("\nTHANK YOU!");
    return 0;
}
