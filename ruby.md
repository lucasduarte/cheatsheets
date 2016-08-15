# Ruby
## Procs and Lambdas
### Differences
`Procs` and `lambdas` are both blocks of code, the differences between them is that a lambda checks the number of arguments passed to it, it will throw and error if you pass a wrong number of arguments, a proc will ignore unexpected arguments and assign `nil` to the missing ones.

When a lambda returns it passes controll back to the calling method, when a proc returns, it does immediately, without going back to the calling method.
- **Lambda**
    ```ruby
    my_lambda = lambda { |parameter| puts "Do Stuff!!" }
    ```
- **Proc**
    ```ruby
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