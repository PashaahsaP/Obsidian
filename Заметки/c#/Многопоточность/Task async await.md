Асинк позволяет обозначить методы которые могут выполняться параллельно основному потоку, но только как в основном потоки понадобитсья данные с асинхронного метода и этих данных нет то поток останавливаеться и ждет, а если уже есть продолжает выполнение. Это удобно при работе с ui, когда на нажатие клавиши выполняеться какое то действие, основной потока также работает что в свою очередь не блокирует окно и контроллеры, только то поток может управлять контроллерами который их создал. Также и для работы с работы i/o операциями будет полезно пока получаем данные или отправляем мы может продолжать выполнение до того момента пока нам не понадобится результаты работы I/o.
	Отличие от thread в том что thread не может уведомить основной поток о выполнении сам, нужно еще добисывать код чтобы синхронизировать выполнение. И async использует ThreadPool.
Для отмены работы task можно использовать класс cancellation token source который может дать cancellation token для task, и через cts можно отменить task. С помощью интерфеса iProgress можно отслеживать прогресс выполнения task.
 Также отличием от таск являеться упрощение работы с кодом.
 Async/await упрощает ту часть асинхронного программирования которая отвечает за ожидания завершения вторичных потоков, извлечение результата из вторичного потока.

Результаты выполнения можно получить напрямую через await
https://docs.microsoft.com/en-us/archive/msdn-magazine/2011/february/msdn-magazine-parallel-computing-it-s-all-about-the-synchronizationcontext
https://devblogs.microsoft.com/pfxteam/await-and-ui-and-deadlocks-oh-my/?WT.mc_id=DT-MVP-5000058#comments
https://devblogs.microsoft.com/pfxteam/await-synchronizationcontext-and-console-apps/
https://docs.microsoft.com/en-us/dotnet/standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern
https://devblogs.microsoft.com/pfxteam/asyncawait-faq/?WT.mc_id=DT-MVP-5000058
[[Task]][[AsyncAwait]][[Asynchronous programming]][[SynchronizationContext]]