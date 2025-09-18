`priority_queue<int>` -> default pq max, top() returns highest element; `priority_queue<int> pq_max`, add `std::greater<T>` to get smallest element to be as `top()`: `priority_queue<int, vector<int>, greater<int>> pq_min;`

`push(val)` - add element, sort the container

`top()` -> return first/top element

`pop()` -> drop first/top element

Custom comparator, that makes pq min for pair<int, int> where someval bounded with it's index:

```
      priority_queue<pair<int, int>, vector<pair<int, int>>, decltype([](const pair<int, int>& a, const pair<int, int>& b)
      {if (a.first == b.first)
          return a.second > b.second;
          
          return a.first > b.first;
      })> pq;
```
Nuances: comparator can't be lambda directly, as the pq constructor expects comparator as a type.

Task pattern: priority_queue, but priority could be changed. Core idea for this: pq stores elements and additional map tracks <unique_element_pointer, realPriority>. Thus, on priority editing -> add element to queue as the new one, edit priotity with tracking map. On using pq: if top element doesnt't match with tracking map (or no element in map -> element actually is used or deleted), this means it's false/outdated element -> just drop it.
