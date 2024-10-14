`priority_queue<int>` -> default pq max, top() returns highest element; `priority_queue<int> pq_max`, add `std::greater<T>` to get smallest element to be as `top()`: `priority_queue<int, vector<int>, greater<int>> pq_min;`

`push(val)` - add element, sort the container

`top()` -> return first/top element

`pop()` -> drop first/top element
