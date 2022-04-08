#include <bits/stdc++.h>
using namespace std;
bool a[1001][1001];
int main()
{
    int t;
    cin >> t;
    while (t--)
    {
        string s;
        cin >> s;
        int n = s.size(), ans = 1;
        for (int i = 0; i < n; i++)
            a[i][i] = 1;
        for (int i = 1; i < n; i++)
        {
            for (int j = 0; j < n - 1; j++)
            {
                int k = i + j;
                if (i + j < n)
                {
                    a[j][k] = ((j + 1 > k - 1 || a[j + 1][k - 1]) && s[j] == s[k]);
                    if (a[j][k])
                        ans = i + 1;
                }
            }
        }
        cout << ans << endl;
    }
}
