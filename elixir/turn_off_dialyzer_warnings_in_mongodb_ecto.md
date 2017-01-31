# Turn off dialyzer warnings in mongodb_ecto

[Dialyzer](http://erlang.org/doc/man/dialyzer.html), a DIscrepancy AnaLYZer for ERlang programs, is a static analytics tool that helps to find common type errors. [dialyxir](https://github.com/jeremyjh/dialyxir) is useful mix tasks to make use of dialyzer simple in an elixir project.

I tried to use dialyzer on the phoenix project powered by mongodb_ecto and encountered warnings I cannot fix easily: 

```
lib/ltv/repo.ex:2: Call to missing or unexported function 'Elixir.Mongo.Ecto':rollback/2
lib/ltv/repo.ex:2: Call to missing or unexported function 'Elixir.Mongo.Ecto':'in_transaction?'/1
```

Attribute @dialyzer can be used for turning off warnings in a module by specifying functions or warning options. 

```elixir
defmodule Ltv.Repo do
  @dialyzer [
    {:nowarn_function, rollback: 1},
    {:nowarn_function, in_transaction?: 0},
    {:nowarn_function, insert_or_update: 2},
    {:nowarn_function, insert_or_update!: 2},
  ]

  use Ecto.Repo, otp_app: :ltv
end
```

January 30, 2017 by deepblue
