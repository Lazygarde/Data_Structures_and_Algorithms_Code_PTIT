#include <bits/stdc++.h>
#define endl "\n"
using namespace std;
int main()
{
    ios_base::sync_with_stdio(0);
    cin.tie(0);
    int t;
    cin >> t;
    while (t--)
    {
        int n;
        cin >> n;
        string s = "";
        vector<int> a(n), b(n);
        stack<string> st;
        for (int i = 0; i < n; i++)
            cin >> a[i];
        for (int i = 0; i < n; i++)
        {
            s += "[" + to_string(a[0]);
            for (int j = 1; j < n - i; j++)
            {
                s += " " + to_string(a[j]);
                b[j - 1] = a[j - 1] + a[j];
            }
            s += "]";
            st.push(s);
            s = "";
            for (int j = 0; j < n - i; j++)
            {
                a[j] = b[j];
            }
        }
        while (st.size())
        {
            cout << st.top() << " ";
            st.pop();
        }
        cout << endl;
    }
}
