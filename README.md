<h1>Synchronous and Asynchronous JavaScript</h1>
<p>JavaScript is a single-threaded language, which means that it can only execute one task at a time. However, there are two ways to perform tasks in JavaScript: synchronous and asynchronous.</p>

<h2>Synchronous JavaScript</h2>

<p>Synchronous JavaScript is executed in a sequence, one task at a time. This means that the next task can only start after the previous task has finished executing. Here's an example of synchronous JavaScript:</p>

<pre>
  console.log("Task 1");
  console.log("Task 2");
  console.log("Task 3");
</pre>

<p>In this example, Task 1 is executed first, followed by Task 2 and then Task 3. The code waits for each task to complete before moving on to the next task.</p>

<h2>Asynchronous JavaScript</h2>

<p>Asynchronous JavaScript, on the other hand, allows tasks to be executed simultaneously without waiting for each other to finish. This is achieved through the use of callbacks, promises, and async/await.</p>

<h3>Callbacks</h3>

<p>Callbacks are functions that are passed as arguments to another function and are executed when the main function completes its task. Here's an example:</p>

<pre>
function task1(callback) {
  console.log("Task 1");
  callback();
}

function task2() {
  console.log("Task 2");
}

task1(task2);
console.log("Task 3");
</pre>

<p>In this example, task1 takes a callback function as an argument and executes it after Task 1 is completed. Task 2 is passed as the callback function to task1 and is executed after Task 1 is finished. Task 3 is executed last, as it is outside of the callback function.</p>

<h3>Promises</h3>

<p>Promises are objects that represent a value that may not be available yet. They are used to handle asynchronous operations in JavaScript. Here's an example:</p>

<pre>
function task1() {
  return new Promise(function(resolve, reject) {
    console.log("Task 1");
    resolve();
  });
}

function task2() {
  console.log("Task 2");
}

task1().then(task2);
console.log("Task 3");
</pre>

<p>In this example, task1 returns a Promise object, which resolves when Task 1 is completed. Task 2 is executed using the then method after Task 1 is resolved. Task 3 is executed last, as it is outside of the Promise.</p>

<h3>Async/await</h3>

<p>Async/await is a newer feature in JavaScript that allows for cleaner and easier-to-read code when handling asynchronous tasks. Here's an example:</p>

<pre>
async function task1() {
  console.log("Task 1");
}

async function task2() {
  console.log("Task 2");
}

async function main() {
  await task1();
  task2();
}

main();
console.log("Task 3");
</pre>

<p>In this example, the main function is marked as async and awaits Task 1 before executing Task 2. Task 3 is executed last, as it is outside of the main function.</p>

<h2>Conclusion</h2>

<p>Synchronous and asynchronous JavaScript are two ways to perform tasks in JavaScript. Synchronous JavaScript executes tasks in sequence,

while asynchronous JavaScript allows tasks to be executed simultaneously without waiting for each other to finish. Asynchronous JavaScript can be achieved through the use of callbacks, promises, and async/await. Choosing the appropriate method depends on the use case and requirements of the task at hand. It is important to understand the differences between synchronous and asynchronous JavaScript and how to use them effectively to write efficient and scalable code.

<h2>References</h2>

<ul>
	<li><a target="_blank" href="https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Asynchronous/Introducing">MDN Web Docs: Introducing asynchronous JavaScript</a></li>
	<li><a target="_blank" href="https://www.w3schools.com/js/js_asynchronous.asp">W3Schools: Asynchronous JavaScript</a></li>
	<li><a target="_blank" href="https://blog.bitsrc.io/understanding-asynchronous-javascript-the-event-loop-74cd408419ff">Understanding Asynchronous JavaScript: The Event Loop</a></li>
</ul>


