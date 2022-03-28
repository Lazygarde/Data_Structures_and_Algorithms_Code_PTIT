#include <bits/stdc++.h>
#define endl "\n"
using namespace std;
string op = "+-*/";
bool check(char k)
{
    for (int i = 0; i < op.size(); i++)
    {
        if (op[i] == k)
            return 1;
    }
    return 0;
}
int deg(char k)
{
    if (k == '*' || k == '/')
        return 10;
    else if (k == '+' || k == '-')
        return 20;
    else
        return 100;
}
string topost(string a)
{
    string res = "";
    stack<char> st;
    st.push('#');
    for (int i = 0; i < a.size(); i++)
    {
        if (a[i] == '(')
        {
            st.push(a[i]);
            continue;
        }
        else if (a[i] == ')')
        {
            while (st.size() && st.top() != '(')
            {
                res += st.top();
                st.pop();
            }
            st.pop();
            continue;
        }
        else if (check(a[i]))
        {
            while (st.size() && deg(st.top()) <= deg(a[i]))
            {
                res += st.top();
                st.pop();
            }
            st.push(a[i]);
            continue;
        }
        long long so = 0, ok = 0;
        while (i < a.size() && a[i] != ')' && !check(a[i]))
        {
            long long ss = a[i] - '0';
            i++;
            so = so * 10 + ss;
            ok = 1;
        }
        if (ok == 1)
            i--;
        res += "(";
        res += to_string(so);
        res += ")";
    }
    while (st.size() && st.top() != '#')
    {
        res += st.top();
        st.pop();
    }
    return res;
}
long long tinh(string a)
{
    stack<long long> st;
    int i = 0;
    while (i < a.size())
    {
        if (a[i] == '(')
        {
            i++;
            long long so = 0;
            while (a[i] != ')')
            {
                so = so * 10 + (a[i] - '0');
                i++;
            }
            i++;
            st.push(so);
        }
        else if (st.size() > 1)
        {
            long long tmp1 = st.top();
            st.pop();
            long long tmp2 = st.top();
            st.pop();
            if (a[i] == '+')
                st.push(tmp1 + tmp2);
            else if (a[i] == '-')
                st.push(tmp2 - tmp1);
            else if (a[i] == '*')
                st.push(tmp1 * tmp2);
            else if (a[i] == '/')
                st.push(tmp2 / tmp1);
            i++;
        }
    }
    return st.top();
}
int main()
{
    ios_base::sync_with_stdio(0);
    cin.tie(0);
    int t;
    cin >> t;
    while (t--)
    {
        string a;
        cin >> a;
        cout << tinh(topost(a)) << endl;
    }
}
/* Do Xuan Huong
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@@@@@@@@@@@@@@@@@@@@@@##################@@@@@@@@@@@@@@@@@@@@@
@@@@@@@@@@@@@@@@#############################@@@@@@@@@@@@@@@@
@@@@@@@@@@@@&####################################@@@@@@@@@@@@
@@@@@@@@@@##########################################@@@@@@@@@
@@@@@@@@##############################################@@@@@@@
@@@@@@#################################################@@@@@@
@@@@@####################################################@@@@
@@@%#####################@@@@@@@@@@@######################@@@
@@@###################@@@@@@@@@@@@@@@@@####################@@
@@##################@@@@@@         @@@@@@##################@@
@@#################@@@@@             @@@@###################@
@@@@@@@@@@@@@@@@@@@@@@@@             @@@@@@@@@@@@@@@@@@@@@@@@
@                  &@@@@             @@@@           .......@@
@@                  @@@@@@         @@@@@@           .......@@
@@                    @@@@@@@@@@@@@@@@@            .......@@@
@@@                      @@@@@@@@@@@               ......@@@@
@@@@                                              ......@@@@@
@@@@@@                                           ......@@@@@@
@@@@@@@                                         .....@@@@@@@@
@@@@@@@@@                                     .....@@@@@@@@@@
@@@@@@@@@@@@                                ....@@@@@@@@@@@@@
@@@@@@@@@@@@@@@@                         ....@@@@@@@@@@@@@@@@
@@@@@@@@@@@@@@@@@@@@@%                .@@@@@@@@@@@@@@@@@@@@@@
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
*/
