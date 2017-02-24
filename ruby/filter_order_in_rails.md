# Filter Order in Rails

This is a simple but confusing problem we frequently face when reading rails code. In fact, I always search google to check this out if the order of the filters is important.
I've got some simple test code and result from http://blog.tahnok.me/post/filter-order-in-rails.html

Test code:

```ruby
before_filter :before1
after_filter :after1
around_filter :around1
before_filter :before2
after_filter :after2
aroud_filter :around2

def index
  render text: "Hi"
end
```


Result:

```
before1
around1 (before)
before2
around2 (before)
Hi
around2 (after)
after2
around1 (after)
after1
```
