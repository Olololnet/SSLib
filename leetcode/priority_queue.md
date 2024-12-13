`priority_queue<int>` -> default pq max, top() returns highest element; `priority_queue<int> pq_max`, add `std::greater<T>` to get smallest element to be as `top()`: `priority_queue<int, vector<int>, greater<int>> pq_min;`

`push(val)` - add element, sort the container

`top()` -> return first/top element

`pop()` -> drop first/top element

Custom comparator, that make pq min for pair<int, int> where someval bounded with it's index:

```
      priority_queue<pair<int, int>, vector<pair<int, int>>, decltype([](const pair<int, int>& a, const pair<int, int>& b)
      {if (a.first == b.first)
          return a.second > b.second;
          
          return a.first > b.first;
      })> pq;
```
Nuances: comparator can't be lambda directly, as constructor expects comparator as type.
