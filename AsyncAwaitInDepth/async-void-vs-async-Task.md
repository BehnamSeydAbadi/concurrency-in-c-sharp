<h1 align="center">
   async void vs async Task
</h1>

- async void
   - Methods can not be called using await. In other words, when a method with the async void is called, it assigns to another thread without telling the current thread that its work is over.
   - These kinds of methods are useful for handling UI events. For example Click_Button event in WinForm applications.
   - Thrown exceptions inside of async void methods are rethrown on the Thread-pool.
   - Compiler uses "AsyncVoidMethodBuilder" to handle these types of methods.

- async Task
   - Methods can be called using await. It means that the whole process can be paused until the called method is finished. Then it can resume its work.
   - The use cases of these kinds of methods are common.
   - If the called method did not call with an await keyword, the thrown exception won't be raised until Garbage Collector tries to clean the task. But when it is called with and await, the exception shows itself when it gets thrown.
   - Compiler uses "AsyncTaskMethodBuilder" to handle these types of methods.
