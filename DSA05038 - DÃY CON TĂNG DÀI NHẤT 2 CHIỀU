#include <bits/stdc++.h>
using namespace std;
int n, ans;
pair<int, int> a;
set<pair<int, int>> s[100000];
bool check(const pair<int, int> a, const pair<int, int> b)
{
    return ((a.first < b.first) && (a.second < b.second));
}
bool kt(set<pair<int, int>> &st)
{
    for (set<pair<int, int>>::iterator i = st.begin(); i != st.end(); i++)
    {
        if (check(*i, a))
            return 1;
        else if (i->first >= a.first)
            break;
    }
    return 0;
}
int binary_search(int l, int r)
{
    while (l < r)
    {
        int m = (l + r) / 2;
        if (kt(s[m]))
            l = m + 1;
        else
            r = m;
    }
    return l;
}
int main()
{
    cin >> n;
    for (int i = 0; i < n; i++)
    {
        cin >> a.first >> a.second;
        int pos = binary_search(0, n);
        if (pos < n)
        {
            set<pair<int, int>>::iterator k = ++s[pos].insert(a).first;
            while (k != s[pos].end())
            {
                if (check(a, *k))
                    s[pos].erase(k++);
                else
                    k++;
            }
        }
    }
    while (ans < n && s[ans].size())
        ans++;
    cout << ans;
}
