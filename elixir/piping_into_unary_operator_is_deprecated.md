# Piping into a unary operator is deprecated

Using elixir, piping is very attractive but also tricky. As a beginner, I tend to use it everywhere possible.
This is the error I faced recently.

```shell
iex(15)> %{til: %{ruby: [], elixir: []}} |> &(&1[:til])
warning: piping into a unary operator is deprecated. You could use e.g. Kernel.+(5) instead of +5
```

Solution is simple.

```shell
iex(8)> %{til: %{ruby: [], elixir: []}} |> Map.get(:til, nil)
%{elixir: [], ruby: []}
```

But I've got to confess that I tried it this way at first.

```shell
iex(11)> %{til: %{ruby: [], elixir: []}} |> (fn(x) -> x[:til] end).()
%{elixir: [], ruby: []}
```

Sadly this is the general solution but I don't think we would meet this situation frequently. Therefore in conclusion, today's lesson is "Use existing modules and helper methods effectively". 

Jan 25, 2017 by YoonjungKoh
