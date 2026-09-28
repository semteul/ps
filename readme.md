\# 26/09/23

\## 완전범죄 389480

```C++

\#include <vector>

\#include <algorithm>

using namespace std;



static const int INF = 100000;



int solution(vector<vector<int>> info, int n, int m) {

&#x20;   int size = info.size();

&#x20;   vector<vector<int>> dp(size + 1, vector<int>(m, INF));



&#x20;   dp\[0]\[0] = 0;



&#x20;   for (int i = 1; i <= size; i++) {

&#x20;       int a = info\[i - 1]\[0];

&#x20;       int b = info\[i - 1]\[1];



&#x20;       for (int j = 0; j < m; j++) {

&#x20;           dp\[i]\[j] = min(dp\[i]\[j], dp\[i - 1]\[j] + a);



&#x20;           if (j + b < m) {

&#x20;               dp\[i]\[j + b] = min(dp\[i]\[j + b], dp\[i - 1]\[j]);

&#x20;           }

&#x20;       }

&#x20;   }



&#x20;   int minv = INF;

&#x20;   for (int j = 0; j < m; j++) {

&#x20;       minv = min(dp\[size]\[j], minv);

&#x20;   }



&#x20;   return minv >= n ? -1 : minv;

}

```



\## 26/09/24

\# 서버 증설 횟수 389479

```C++

\#include <string>

\#include <vector>



// 그리디



using namespace std;



int solution(vector<int> players, int m, int k) {

&#x20;   int answer = 0;

&#x20;   

&#x20;   vector<int> return\_server(players.size() + k); // 시간에 따라 반납해야 하는 서버 수

&#x20;   

&#x20;   int servers = 0; // 현재 증설 서버 수

&#x20;   int add\_sum = 0; // 증설 횟수

&#x20;   

&#x20;   for (int i=0;i<players.size(); i++) {

&#x20;       int current\_players = players\[i]; // 현재 이용자 수

&#x20;       servers -= return\_server\[i]; // 줄어든 서버 반영

&#x20;       

&#x20;       int add = 0;

&#x20;       if (current\_players >= m\*(servers+1)) { // 서버 이용자가 많다면 

&#x20;           add = (current\_players - m\*(servers+1))/m + 1;

&#x20;           return\_server\[i+k] = add;

&#x20;           servers += add;

&#x20;           add\_sum += add;

&#x20;       }

&#x20;   }

&#x20;   

&#x20;   answer = add\_sum;

&#x20;   

&#x20;   return answer;

}

```



\## 26/09/27

```

\#include <iostream>



using namespace std;



int main(void) {

&#x20;   string message = "

Let's go!

";



&#x20;   cout << "3

\\n

2

\\n

1" << endl;

&#x20;   cout << message << endl;



&#x20;   return 0;

}

```

