![[js-runtime.png]]
**Fig 1**: JS runtime

![[Pasted image 20260527105656.png]]
**Fig 2:** Chrome runtime (JS runtime + APIs provided by browsers + event loop + callback queue)

>**JavaScript** is a single-threaded programming language (single threaded runtime). It has a single call stack and can do only one thing at a time.

**But what happens when the things are really slow?**
If you make a network request, you'll have to wait until you get back a response. Your code execution is paused. This is problematic because we are running the code in the **browser**. If we want nice fluid UIs, we can't block the stack because if the browser is making a network request then you won't be able to do anything. Its like if you're downloading a video from youtube then you will have to wait until that video is downloaded to do anything else (watch another video while it is downloading).


The solution to above problem is **asynchronous callbacks**.

## Concurrency & the Event Loop 

>One thing at a time, except not really

JS runtime can only do one thing at a time. The reason we can do thing concurrently is because the browser is more than just the runtime.  In diagram 2 we have these web APIs provided by the browser, they are effectively threads that you can just make calls to and this way the concurrency kicks in.

![[Pasted image 20260527112015.png]]
Now `setTimeout()` call is essentially complete. So let's pop it out of the stack.

![[Pasted image 20260527112201.png]]

![[Pasted image 20260527112255.png]]
When web apis are done they push callbacks on the **task queue or callback queue**. This is where **event loop** kicks in, its job is to look at the stack and task queue. If the stack is empty then take the first thing on the task queue and push it onto the stack, which effectively runs it.

