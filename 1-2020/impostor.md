# JS - Made to be shared

The one big aspect of becoming a JavaScript developer was the community. But more specifically the obvious nature of being able to, at any level, spread knowledge learned and also learn form other everyday. One thing that I find that correlates very strongly to imposter syndrome is ego. Just like going ot the gym or any other working out scenerio if you let your ego get the best of you it will slow your progress and hurt you fast. This is no different in Programming and gaining knowledge from your peers around you.

Lately after two years of actual real world programming experience I've been trying to get rid of all imposter syndrom and as I learn things, big or small, share those things. In my job we pretty much rely on Vanilla JS for most of our App. I have known about IIFE's and pretty much how they act but never came across this use case until this week and had to share it since in my narrow JS workd it was pretty rare.

IIFE: Stands for Imediatly Invoked Function Expression
Example: (function runNow(){
console.log("Hello IIFE!")
})()

So this is the pattern I saw used in a IIFE that I saw this week and went down a rabbit hole exploring.

```
let counter = (function counterAdd() {

    let current = 0;

    return () => current = current + 1

}());

console.log(counter()); // 1
console.log(counter()); // 2
console.log(counter()); // 3



```

Which tripped me up when first seeing it maybe because of the conciseness but in esense what it is really doing is something simular to the following but we're just returning an anonomous function in the first version.

```
let counter = (function counterAdd() {

    let current = 0;

    return {
        getNext: () => current = current + 1

    };

}());

console.log(counter.getNext()); // 1
console.log(counter.getNext()); // 2
console.log(counter.getNext()); // 3

```

So what's really happening here is the first time the IIFE runs it is declaring the counter but since the variable now has the return function on it it will run that return function (which has access to the variable due to closure) and will not reset the counter to 0 each time.

After seeing how this code functioned I had a ah-hah moment and starting to defaulting to my oh cool I want to show this to someone but then the imposter syndrom started creeping in. If you're honest with yourself you know it. The "I'm going to show someone and their going to make that condensending face and be like yeah that has been around a while now." But then I thought what the hell is the point of working with a team and actually having a job with peers if we cannot share information and show eachother things learned.

The approach I use for this is to show my enthusiasm while showing the code. Think about it. If you pull a senior dev over and be like "Hey check this out this is pretty cool" and continue showoing them how the IIFE creates a state like environment almost like a stateful React component even if they know it they will see your enthusiasm for learning something new and that cannot be bad for anyone. So I did just that and the senior dev hasn't seen that exact use case before. This is one of the scenerios that's a win-win and should always be sought out in our profession in my opinion.

On top of that for VetsWhoCode we have a member that slacks out a code challenge daily so I im'ed him about possibly using this in a challenge and his reply back was...

![Comment to VetsWhoCode member recommending JS Book](https://thepracticaldev.s3.amazonaws.com/i/4kw3gjz2fqrb616rkd31.png)
