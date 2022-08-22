находиться в system.threading.task.
основные метода это for,foreach and Invoke.
Вызывающий поток принимает участие в работе этих методов, а не вызывает потоки для вычисления и ждет результата.
Также можно использовать cancelation token[Task][[Multythreading]][