#include <bits/stdc++.h>
using namespace std;
int n, a[20], b[20], c[20][20], ans = 1e9, s = 0;
vector<int> as;
void Try(int x, vector<int> k)
{
    for (int i = 2; i <= n; i++)
    {
        if (!b[i])
        {
            a[x] = i;
            b[i]++;
            s += c[a[x - 1]][i];
            k.push_back(i);
            if (x == n && s + c[i][1] < ans)
            {
                ans = s + c[i][1];
                as = k;
            }
            else if (s < ans && x < n)
                Try(x + 1, k);
            s -= c[a[x - 1]][i];
            b[i]--;
            k.pop_back();
        }
    }
}
int main()
{
    cin >> n;
    for (int i = 1; i <= n; i++)
    {
        for (int j = 1; j <= n; j++)
        {
            cin >> c[i][j];
        }
    }
    a[1] = b[1] = 1;
    as.push_back(1);
    if (n == 1)
    {
        cout << 0;
        return 0;
    }
    Try(2, as);
    cout << "(";
    for (auto i : as)
        cout << i << ",";
    cout << 1 << ")" << endl;
    cout << ans;
}
