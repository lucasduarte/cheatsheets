# Ruby
## Procs and Lambdas
### Differences
`Procs` and `lambdas` are both blocks of code, the differences between them is that a lambda checks the number of arguments passed to it, it will throw and error if you pass a wrong number of arguments, a proc will ignore unexpected arguments and assign `nil` to the missing ones.

When a lambda returns it passes controll back to the calling method, when a proc returns, it does immediately, without going back to the calling method.

- **Lambda**
    ```ruby
    #lambda
    my_lambda = lambda { |parameter| puts "Do Stuff!!" }
    ```
    
- **Proc**
    ```ruby
    #proc
    my_proc = Proc.new { |p| puts "Do Stuff!" }
    ```
### Usage
    ```ruby
    arr = [1,2,3,4]
    #Double it with proc
    double_proc = Proc.new { |n| n * 2 }
    arr.map(&double_proc)
    
    #Double it with lambda
    double_lambda = lambda { |n| n * 2 }
    arr.map(&double_lambda)
    ```

## Classes
### How 'super' handles arguments when called
- Called with no argument list (empty or otherwise), super automatically forwards the arguments that were passed to the method from which it’s called.
- Called with an empty argument list—super()—it sends no arguments to the
higher-up method, even if arguments were passed to the current method.
- Called with specific arguments—super(a,b,c)—it sends exactly those
arguments.

## Implementations of Built in functions

### "times" function from Integer class
```ruby
class Integer
  def my_times
    (0..self).each do |n|
      yield(n)
    end
    self
  end
end  
```

### "each" function from Array class
```ruby
class Array
  def my_each
    i = 0
    until i == self.length
      yield(self[i])
      i += 1
    end
    self
  end    
end
```
