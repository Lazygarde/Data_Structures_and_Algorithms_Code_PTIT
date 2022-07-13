#include <bits/stdc++.h>
#define endl '\n'
using namespace std;
struct Node
{
    int val;
    Node *left, *right;
};
Node *createNode(int x)
{
    Node *k = new Node;
    k->val = x;
    k->left = k->right = NULL;
    return k;
}
Node *buildTree(int n, int *inorder, int *levelorder, int st, int e)
{
    if (n > 0)
    {
        Node *root = createNode(levelorder[0]);
        int idx = -1;
        unordered_map<int, int> m;
        for (int i = st; i <= e; ++i)
        {
            if (inorder[i] == levelorder[0])
            {
                idx = i;
                break;
            }
            m[inorder[i]]++;
        }
        int L[m.size()], R[e - st - m.size()], l, r;
        l = r = 0;
        for (int i = 1; i < n; ++i)
        {
            if (m[levelorder[i]])
                L[l++] = levelorder[i];
            else
                R[r++] = levelorder[i];
        }
        root->left = buildTree(idx - st, inorder, L, st, idx - 1);
        root->right = buildTree(e - idx, inorder, R, idx + 1, e);
        return root;
    }
    return NULL;
}
void postOrder(Node *root)
{
    if (root->left != NULL)
        postOrder(root->left);
    if (root->right != NULL)
        postOrder(root->right);
    cout << root->val << ' ';
}
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
        int inorder[n], levelorder[n];
        for (int i = 0; i < n; i++)
            cin >> inorder[i];
        for (int i = 0; i < n; i++)
            cin >> levelorder[i];
        Node *root = buildTree(n, inorder, levelorder, 0, n - 1);
        postOrder(root);
        cout << endl;
    }
}
