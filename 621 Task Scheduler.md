1. Right code

```
class Solution:
    def leastInterval(self, tasks: List[str], n: int) -> int:
        rooms = [i for i in Counter(tasks).values()]
        rooms.sort()
        max_freq = rooms.pop()-1
        m = len(tasks)
        idle_room = max_freq * n
        while rooms and idle_room > 0:
            idle_room -= min(rooms.pop(),max_freq)
        return m + max(0,idle_room)
 ```
 
 2. Thoughts
 
 (1). The line inside the while loop is very important. It categorizes the problems into two cases
 First： If there is only one element has most occurences, then every time we have idle_room -= rooms.pop /
 
 Second: If there are two elements have most occurences, then the first time idle_room - max_freq. For example, if top two occurrences are A,B, max_freq= 3, n=2 //
 then the initial arrangement should be: "A,B,idle, A,B,idle, A,B". 
       
