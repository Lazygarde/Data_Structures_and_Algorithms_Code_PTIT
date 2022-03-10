#include <bits/stdc++.h>
#define endl "\n"
using namespace std;

struct matrix
{
	long long a[5][5] = {};
};

long long n = 4, MOD = 1e15 + 7;

long long nhan(long long x, long long y)
{
	if (y == 1)
		return x % MOD;
	if (y == 0)
		return 0;
	long long tmp = nhan(x, y / 2) % MOD;
	if (y % 2 == 0)
		return (2 * tmp) % MOD;
	return ((2 * tmp) % MOD + x % MOD) % MOD;
}

matrix mulMatrix(matrix A, matrix B)
{
	matrix tmp;
	for (int i = 1; i <= n; i++)
	{
		for (int j = 1; j <= n; j++)
		{
			long long sum = 0;
			for (int k = 1; k <= n; k++)
				sum = (sum % MOD + nhan(A.a[i][k], B.a[k][j]) % MOD) % MOD;
			tmp.a[i][j] = sum;
		}
	}
	return tmp;
}

matrix operator^(matrix A, long long k)
{
	if (k == 1)
		return A;
	matrix tmp = A ^ (k / 2);
	matrix c = mulMatrix(tmp, tmp);
	if (k % 2 == 0)
		return c;
	return mulMatrix(c, A);
}

matrix createI()
{
	matrix res;
	for (int i = 1; i <= n; i++)
		res.a[i][i] = 1;
	return res;
}

matrix operator+(matrix A, matrix B)
{
	matrix c;
	for (int i = 1; i <= n; i++)
		for (int j = 1; j <= n; j++)
			c.a[i][j] = (A.a[i][j] + B.a[i][j]) % MOD;
	return c;
}

matrix sumPowMatrix(matrix A, long long k)
{
	if (k == 1)
		return A;
	long long h = k / 2;
	matrix c = mulMatrix((createI() + (A ^ h)), sumPowMatrix(A, h));
	if (k % 2 == 1)
		c = c + (A ^ k);
	return c;
}
int main()
{
	ios_base::sync_with_stdio(0);
	cin.tie(0);
	int t;
	cin >> t;
	while (t--)
	{
		long long k, ans = 0;
		matrix A;
		cin >> k;
		if (k <= 3)
		{
			cout << k * (k + 1) / 2 << endl;
			continue;
		}
		A.a[1][1] = 1; A.a[1][2] = 1; A.a[1][3] = 0; A.a[1][4] = 0;
		A.a[2][1] = 0; A.a[2][2] = 1; A.a[2][3] = 1; A.a[2][4] = 1;
		A.a[3][1] = 0; A.a[3][2] = 1; A.a[3][3] = 0; A.a[3][4] = 0;
		A.a[4][1] = 0; A.a[4][2] = 0; A.a[4][3] = 1; A.a[4][4] = 0;
		matrix B = A ^ (k - 2);
		for (int i = 2; i <= n; i++)
		{
			ans += nhan(B.a[1][i], (5 - i));
			ans %= MOD;
		}
		ans += nhan(B.a[1][1], 3);
		ans %= MOD;
		cout << ans << endl;
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
