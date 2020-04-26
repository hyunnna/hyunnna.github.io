---
layout: post
title:  "greedy Algorihm"
date:   2020-04-26 08:43:59
author: hyunnna
categories: algorism
tags:	learning
cover:  "/assets/instacode.png"
---

# Greedy Algorihm
#### : 최적해를 구하는 상황에서 사용 

***

#### **<span style = "color:blue">특징</span>**
- 불필요한 탐색시간 삭제                                 
- 시간적으로 효율적        
- **<span style = "color:red">언제나 적합한 해를 구하지는 못함**    
     * 마시멜로 실험 : 그리디 알고리즘에 따르면 바로 마시멜로를 먹는것이 적합한 해로 인식되겠지만        **기다리면 두개를 먹을 수 있다** 라는 최적해로 가지 못한다.

***

#### 문제

> 동물원에 n마리의 원숭이가 있고 모든 원숭이들은 1부터 n까지의 번호가 매겨져있다.     
> 원숭이 1, 2번이 서로 싫어하는 관계일 경우 둘은 같은 우리에 넣으면 안된다.       
> 앙숙인 원숭이가 2개 이상인 원숭이를 다른 우리로 옮겨주면 된다.


#### 코드
<pre><code>
#include <bits/stdc++.h>
using namespace std;

int n;
vector<int> g[101010];

int pos[101010];

bool relax(){
    bool ret = 0;
    for(int i=1; i<=n; i++){
        if(pos[i]) continue;
        int cnt = 0;
        for(int j=0; j<g[i].size(); j++) cnt += pos[g[i][j]] == 0;
        if(cnt > 1) pos[i] = 1, ret = 1;
    }
    for(int i=1; i<=n; i++){
        if(!pos[i]) continue;
        int cnt = 0;
        for(int j=0; j<g[i].size(); j++) cnt += pos[g[i][j]] == 1;
        if(cnt > 1) pos[i] = 0, ret = 1;
    }
    return ret;
}

int main(){
    ios_base::sync_with_stdio(0); cin.tie(0);
    cin >> n;
    for(int i=1; i<=n; i++){
        int cnt; cin >> cnt;
        while(cnt--){
            int t; cin >> t; g[i].push_back(t);
        }
    }

    while(1){
        if(!relax()) break;
    }

    int a = 0, b = 0;
    for(int i=1; i<=n; i++){
        if(pos[i]) b++;
        else a++;
    }
    cout << a << " "; for(int i=1; i<=n; i++) if(!pos[i]) cout << i << " ";
    cout << "\n";
    cout << b << " "; for(int i=1; i<=n; i++) if(pos[i]) cout << i << " ";
}
</code>
</pre>

	**출처 : [문제](https://www.acmicpc.net/problem/2516)**        

	**        [코드](https://justicehui.github.io/koi/2019/11/18/BOJ2516/)**

**풀이를 보면 3n/2번 옮기면 항상 답이 나온다.**

이 문제를 응용해서 옛날에 봤던 수수께끼도 알고리즘으로 풀 수 있지 않을까 생각해보았다.

>>늑대, 양, 풀이 있는데 한 번에 하나씩 밖에 옮길 수 없고, 사람이 없으면 늑대는 양을, 양은 풀을 먹어버린다. 모두 무사히 건너기 위해서는 어떻게 해야할까?