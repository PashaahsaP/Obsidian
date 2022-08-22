Это когда поток А ждет когда освободиться ресурс занятый потоком Б, а поток Б ждет освобождения ресурса занятый потоком A.
Потоку А для выполнения своей работы требуеться выполнения заданий в потоке Б, также потоку Б требуеться для его работы выполнения заданий в потоке А. То есть эти потоки зависят друг от друга и им нужно ждать друг друга. Когда такое ожидание наступает одновременно происходит deadlock.
![[220px-Two_processes,_two_resources 1.gif]]
а) A single process goes through.
b) The later process has to wait.
c)  A deadlock occurs when the first process locks the first resource at the same time as the second process locks the second resource.
d)  The deadlock can be resolved by cancelling and restarting the first process.[[Multythreading]]