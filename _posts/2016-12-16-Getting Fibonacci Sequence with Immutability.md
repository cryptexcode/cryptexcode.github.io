Generating Fibonacci sequence is definitely not a complex problem to talk about. We all did it in our early stage of programming. So I am not going to explain what it is. Let's talk about the ways we can generate it in our familiar languages. 

When we were just a beginner if anyone asked us to generate this sequence up to nth values, we used to give a big smile and wrote the code using a for loop, right? We all know the way, so let's skip it too. After a while, we learned about recursion and used recursion to generate the sequence like this,

``` 
public static List<Integer> recursiveFibonacci(int position){ 
    if(position == 1) 
        return Arrays.asList(1);
    
    if(position == 2)  
        return Arrays.asList(1, 1);
        
    List<Integer> previousSequence = recursiveFibonacci(position - 1);  
    List<Integer> newSequence = new ArrayList<Integer>(previousSequence);
    newSequence.add(previousSequence.get(previousSequence.size() - 1) +
        		previousSequence.get(previousSequence.size() - 2));
 
    return newSequence;      
}
```
<p>Here we are using lists and modifying it right? But what if we want to do the same task without modifying any object that means by maintaining immutability? In my previous post, I showed a demo of Stream in Java. Let's have a look at another demo of it.</p>

```
public static List<Integer> immutableFibonacci(int position){
    return Stream.iterate(
                   new int[]{1, 1}, e -> new int[]{e[1], e[0] + e[1]})
                  .map(e -> e[0])
                  .limit(position)
                  .collect(Collectors.toList());
}
```
<p>One liner right? ;) Honestly, I never even thought about doing this with one line of code.</p>
<p>Immutability is a mandatory part of functional programming. Is Java functional? Java 8 supports functional programming basically.<br />How would this code look like in a functional language like Scala?</p>

```
def immutableFibonacci(position: Int) = {
    (0 to position-1).foldLeft(List(1,1)) {
           (list, i) => list:::List(list.last + list.init.last) 
    }.take(position)
}
```

<p>But Scala also supports imperative programming, right? So what about a purely functional language like Erlang? Run this code ;)</p>

```
tl(lists:reverse( lists:foldl( 
         fun(N, ListF) -> [hd(tl(ListF)) + hd(ListF)] ++ ListF end, 
         [1, 0], 
         lists:seq(0, position-2))
)).
```

<p> </p>
<p>Thanks for reading this. Here is a bonus code of Python for the same purpose.</p>

```
reduce(lambda sequence, _: sequence + [sequence[-1] + sequence[-2]],
                            range(position - 1), [1, 1])[:position]
```