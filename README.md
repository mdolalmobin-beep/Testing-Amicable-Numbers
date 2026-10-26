# Testing-Amicable-Numbers
C program to find amicable pairs in a given range


#include <stdio.h>

int main()
{
    int sum[100001] = {0};
    int L, R, count;

    for (int i = 1; i <= 100000; i++)
    {
        for (int j = i * 2; j <= 100000; j += i)
        {
            sum[j] += i;
        }
    }

    while (1)
    {
        scanf("%d %d", &L, &R);

        if (L == 0 && R == 0)
            break;

        count = 0;

        for (int i = L; i <= R; i++)
        {
            int j = sum[i];

            if (j > i && j >= L && j <= R)
            {
                if (sum[j] == i)
                {
                    count++;
                }
            }
        }

        printf("%d\n", count);
    }

    return 0;
}
