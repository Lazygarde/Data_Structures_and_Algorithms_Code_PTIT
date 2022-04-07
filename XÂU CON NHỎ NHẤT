#include <bits/stdc++.h>
using namespace std;
int main()
{
    int t;
    cin >> t;
    while (t--)
    {
        string s;
        cin >> s;
        int n = s.size(), k = 0, st = 0, ans = 1e9, x = 0, a[256] = {};
        if (n == 1)
        {
            cout << 1 << endl;
            continue;
        }
        map<char, int> m;
        for (int i = 0; i < n; i++)
        {
            if (!m[s[i]])
            {
                m[s[i]]++;
                k++;
            }
        }
        for (int i = 0; i < n; i++)
        {
            a[s[i]]++;
            if (a[s[i]] == 1)
                x++;
            if (x == k)
            {
                while (a[s[st]] > 1)
                {
                    if (a[s[st]] > 1)
                        a[s[st]]--;
                    st++;
                }
                int l = i - st + 1;
                ans = min(ans, l);
            }
        }
        cout << ans << endl;
    }
}
