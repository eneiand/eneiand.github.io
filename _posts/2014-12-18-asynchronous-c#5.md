#### The Await Keyword
* The case for using async
  * await -> continue when this has completed please
  * there is some framework support but mostly compiler doing heavy lifting
  * the remaining of the method can be thought of as a continuation
* Await Basics
  * What can we await?
    * Task of T
    * Anything that implements the awaitable pattern
      * INotifyCompletion
      * not an actual interface but does require
        * GetAwaiter()
        * IsCompleted
        * GetResult()
        * OnCompleted(Action continuation)
          * if IsCompleted returns false, OnCompleted gets called with continuation
* A Walk Through Decompiled Async Code
  *  
