# Using various flow control structures

When we write flow control logic we consider flow structures what we use.

Very simply we can use `if` and convert it to `cond`
and after clarifying conditions we can use `case`.
And then we can change it to multiple function clauses with guard if needed.

Below codes are all same, using different flow control structures.

```elixir
def get(env, key, force \\ false) do
  if env == :prod || force do
    fetch_and_update(key)
  else
    load_from_cache(key)
  end
end
```

Using `cond`:

```elixir
def get(env, key, force \\ false) do
  cond do
    env == :prod || force -> fetch_and_update(key)
    _ -> load_from_cache(key)
  end
end
```

And, using `case`, see below example code.

To use `case`, the conditions should be restructured.
We can create a tuple which contains all variables and use it for `case`:

```elixir
def get(env, key, force \\ false) do
  case {env, force} do
    {:prod, _} -> fetch_and_update(key)
    {_, true}  -> fetch_and_update(key)
    {_, false} -> load_from_cache(key)
  end
end
```

Finally, we can convert `case` as Erlang style:

```elixir
def get(:prod = _env, key, _force \\ false), do: fetch_and_update(key)
def get(_, key, true),                       do: fetch_and_update(key)
def get(_, key, false),                      do: load_from_cache(key)
```
(And I used `_env`, `_force` as variable name which are not required. They are for specifying `get` function scheme.)

We can not say which is better than others and the choice is yours.
~/tj/til(elixir/various-flow-control-structures ✗)                                                                                                                 (elixir/various-flow-control-structures|…)

February 12 2017, by dongyoonlee
