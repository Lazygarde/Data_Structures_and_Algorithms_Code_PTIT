#include <bits/stdc++.h>
using namespace std;
int main()
{
    int t;
    cin >> t;
    while (t--)
    {
        int n;
        cin >> n;
        int a[n], b, c, k, ans = 0;
        for (int i = 0; i < n; i++)
            cin >> a[i];
        for (int i = 1; i < n; i++)
        {
            b = min(a[i], a[i - 1]);
            c = max(a[i], a[i - 1]);
            k = log2(c / b);
            if (pow(2, k) * b == c && k > 0)
                k--;
            ans += k;
        }
        cout << ans << endl;
    }
}
