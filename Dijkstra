#include <bits/stdc++.h>
#define up(i,a,b) for (int i = (int)a; i <= (int)b; i++)
#define down(i,a,b) for (int i = (int)a; i >= (int)b; i--)
#define pii pair<int, int>
#define f first
#define s second
#define all(x) x.begin(), x.end()
#define ep emplace_back
#define bit(x, i) ((x >> (i)) & 1)
using namespace std;

const int maxn = 1e5 + 10;
priority_queue<pii, vector<pii>, greater<pii> > Q;
vector<pii> a[maxn];
int n,m;
int st, fi;
bitset<maxn> dd;
int d[maxn];

void Dijkstra(int st){
    memset(d, 60, sizeof(int)*(n+1));
    d[st] = 0;
    dd[st] = 1;
    Q.push(make_pair(0, st));
    while (!Q.empty()){
        pii top = Q.top();
        Q.pop();
        int u = top.s;
        int curw = top.f;
        if (curw > d[u]) continue;
//        if (curw != d[u]){
//            cout << "curw != d[u] ?\n";
//        }
        for (auto x : a[u]){
            int v = x.f;
            int w = x.s;
//            if (dd[v]) continue;
            if (d[v] > curw + w){
                d[v] = curw + w;
//                dd[v] = 1;
                Q.push(make_pair(d[v], v));
            }
        }
    }
}

/*
- when take out a vertex v out of Q, d[v] is guaranteed to be the shortest distance from st to v
- dont't mark vertex has been arrived
  because a vertex can be optimized one more time from another path
- if (curw > d[u]) continue
  to make sure that
    +) do not go back to the vertex u such that u->v
    +) if current d[u] is good enough, don't have to consider the curw anymore.
*/

signed main(){
    ios_base::sync_with_stdio(false);
    cin.tie(0);
    #define Task "A"
    if (fopen(Task".inp", "r")){
        freopen(Task".inp", "r", stdin);
        freopen(Task".out", "w", stdout);
    }

    cin >> n >> m;
    up(i,1,m){
        int u,v,w;
        cin >> u >> v >> w;
        a[u].push_back(make_pair(v, w));
    }

    cin >> st >> fi;
    Dijkstra(st);
    cout << d[fi];
}

