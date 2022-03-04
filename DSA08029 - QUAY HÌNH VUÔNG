#include <bits/stdc++.h>
#define endl "\n"
#define fi first
#define se second
using namespace std;
int l[6] = {3, 0, 2, 4, 1, 5};
int r[6] = {0, 4, 1, 3, 5, 2};
string rleft(string a)
{
    string b = "";
    for (int i = 0; i < 6; i++)
        b += a[l[i]];
    return b;
}
string rright(string a)
{
    string b = "";
    for (int i = 0; i < 6; i++)
        b += a[r[i]];
    return b;
}
int main()
{
    ios_base::sync_with_stdio(0);
    cin.tie(0);
    int t;
    cin >> t;
    while (t--)
    {
        string a, b;
        int x;
        for (int i = 0; i < 6; i++)
        {
            cin >> x;
            a += to_string(x);
        }
        for (int i = 0; i < 6; i++)
        {
            cin >> x;
            b += to_string(x);
        }
        pair<string, int> d, k, e;
        d.fi = a;
        d.se = 0;
        queue<pair<string, int>> c;
        c.push(d);
        while (c.size())
        {
            k = c.front();
            c.pop();
            if (k.fi == b)
            {
                cout << k.se << endl;
                break;
            }
            e.se = k.se + 1;
            e.fi = rleft(k.fi);
            c.push(e);
            e.fi = rright(k.fi);
            c.push(e);
        }
    }
}
