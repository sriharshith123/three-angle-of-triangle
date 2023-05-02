#include <stdio.h>

int main() {
    int i, angle1, angle2, angle3, acuteCount = 0, rightCount = 0, obtuseCount = 0, wrongCount = 0;

    for (i = 1; i <= 5; i++) {
        printf("Enter the three angles of triangle %d:\n", i);
        scanf("%d %d %d", &angle1, &angle2, &angle3);

        if (angle1 + angle2 + angle3 > 180) {
            printf("Wrong entries. Sum of angles can't be greater than 180. Try again.\n");
            wrongCount++;
            i--;
            continue;
        }

        if (angle1 < 0 || angle2 < 0 || angle3 < 0) {
            printf("Wrong entries. Angles can't be negative. Try again.\n");
            wrongCount++;
            i--;
            continue;
        }

        if (angle1 + angle2 + angle3 == 180) {
            if (angle1 < 90 && angle2 < 90 && angle3 < 90) {
                acuteCount++;
            } else if (angle1 == 90 || angle2 == 90 || angle3 == 90) {
                rightCount++;
            } else {
                obtuseCount++;
            }
        } else {
            printf("Wrong entries. Sum of angles should be equal to 180. Try again.\n");
            wrongCount++;
            i--;
            continue;
        }
    }

    printf("Acute Angled Triangle: %d\n", acuteCount);
    printf("Right Angled Triangle: %d\n", rightCount);
    printf("Obtuse Angled Triangle: %d\n", obtuseCount);
    printf("Wrong Entries: %d\n", wrongCount);

    return 0;
}
