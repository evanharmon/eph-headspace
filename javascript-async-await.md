# JAVASCRIPT ASYNC AWAIT

# Await an Array of Promises
```
async function stall(time) {
  await new Promise(resolve => setTimeout(resolve, time));
}
const times = [5000, 3000, 1000];
async function run(arr) {
  for (let time of arr) {
  console.log("starting: ", time);
  await stall(time);
  console.log("completed: ", time);
  }
}
run(times);
```
