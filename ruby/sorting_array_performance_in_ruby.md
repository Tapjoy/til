You can sort an array in a various way. Just keep in mind that there is a difference in performance.

Refer to the original article: [Stack Overflow Link](https://stackoverflow.com/questions/2642182/sorting-an-array-in-descending-order-in-ruby)
```ruby
#!/usr/bin/ruby

require 'benchmark'

ary = []
1000.times { 
  ary << {:bar => rand(1000)} 
}

n = 500
Benchmark.bm(20) do |x|
  x.report("sort")               { n.times { ary.sort{ |a,b| b[:bar] <=> a[:bar] } } }
  x.report("sort reverse")       { n.times { ary.sort{ |a,b| a[:bar] <=> b[:bar] }.reverse } }
  x.report("sort_by -a[:bar]")   { n.times { ary.sort_by{ |a| -a[:bar] } } }
  x.report("sort_by a[:bar]*-1") { n.times { ary.sort_by{ |a| a[:bar]*-1 } } }
  x.report("sort_by.reverse!")   { n.times { ary.sort_by{ |a| a[:bar] }.reverse } }
end
```

Here's my result from the script.
```
                           user     system      total        real
sort                   0.390000   0.010000   0.400000 (  0.398573)
sort reverse           0.400000   0.000000   0.400000 (  0.397368)
sort_by -a[:bar]       0.190000   0.000000   0.190000 (  0.195783)
sort_by a[:bar]*-1     0.190000   0.000000   0.190000 (  0.190759)
sort_by.reverse!       0.190000   0.000000   0.190000 (  0.195162)
```

Aug 19 2019, by @SantonyChoi
