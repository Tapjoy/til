# Each with index

### .each
```ruby
>> %w(foo bar baz).each { |item, index| puts "#{item}: #{index}" }
foo:
bar:
baz:
```

### .each_with_index
```ruby
>> %w(foo bar baz).each_with_index { |item, index| puts "#{item}: #{index}" }
foo: 0
bar: 1
baz: 2
```

Note that we can't set starting offset with `each_with_index`

```ruby
>> %w(foo bar baz).each_with_index(3) { |item, index| puts "#{item}: #{index}" }
ArgumentError: wrong number of arguments (1 for 0)
        from (irb):4:in `each'
        from (irb):4:in `each_with_index'
        from (irb):4
        from /Users/wook/.rvm/rubies/ruby-2.1.5/bin/irb:11:in `<main>'
```

### .each.with_index(offset)
```ruby
>> %w(foo bar baz).each.with_index(3) { |item, index| puts "#{item}: #{index}" }
foo: 3
bar: 4
baz: 5
```

Of course we could use `with_index` without argument
```ruby
%w(foo bar baz).each.with_index { |item, index| puts "#{item}: #{index}" }
foo: 0
bar: 1
baz: 2
```

### References
- [each_with_index](https://apidock.com/ruby/Enumerator/each_with_index)
- [with_index](https://apidock.com/ruby/Enumerator/with_index)

Aug 19 2019, by @jeongwooklee
