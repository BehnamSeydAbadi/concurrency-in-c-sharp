<h1 align="center">
   async void vs async Task
</h1>

- async void
   - Methods can not be called using await. in other words, when a method with async void is called, it assigns to another thread without telling the current thread that its work is over.
   - These kinds of methods are useful for handling UI events. For example Click_Button event in WinForm applications.
   - Thrown exceptions inside of async void methods are rethrown on the Thread-pool.
