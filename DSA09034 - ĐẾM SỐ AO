#include <bits/stdc++.h>
#define endl "\n"
using namespace std;
int n, m, dx, dy, s = 0;
char a[105][105];
int rx[] = {1, 1, 1, -1, -1, -1, 0, 0};
int ry[] = {1, 0, -1, 1, -1, 0, 1, -1};
void dfs(int x, int y)
{
    for (int i = 0; i < 8; i++)
    {
        dx = x + rx[i];
        dy = y + ry[i];
        if (dx >= 1 && dx <= n && dy >= 1 && dy <= m && a[dx][dy] == 'W')
        {
            a[dx][dy] = '.';
            dfs(dx, dy);
        }
    }
}
int main()
{
    ios_base::sync_with_stdio(0);
    cin.tie(0);
    cin >> n >> m;
    cin.ignore(0);
    for (int i = 1; i <= n; i++)
    {
        for (int j = 1; j <= m; j++)
            cin >> a[i][j];
    }
    for (int i = 1; i <= n; i++)
    {
        for (int j = 1; j <= m; j++)
        {
            if (a[i][j] == 'W')
            {
                a[i][j] = '.';
                dfs(i, j);
                s++;
            }
        }
    }
    cout << s;
}
