#include <bits/stdc++.h>
using namespace std;
int main()
{
    int n, x, posl = 0, posc = 0;
    cin >> n;
    vector<int> pl, l, c;
    for (int i = 0; i < n; i++)
    {
        cin >> x;
        if (x % 2 == 1)
        {
            l.push_back(x);
            pl.push_back(i);
        }
        else
            c.push_back(x);
    }
    sort(c.begin(), c.end());
    sort(l.begin(), l.end(), greater<int>());
    for (int i = 0; i < n; i++)
    {
        if (posl < pl.size() && i == pl[posl])
            cout << l[posl++] << " ";
        else
            cout << c[posc++] << " ";
    }
}
