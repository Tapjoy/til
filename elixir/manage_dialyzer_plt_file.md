# Manage dialyzer's PLT file

Dialyzer generates Persistent Lookup Table (PLT). Each elixir project manages their plt file including erts, kernel, stdlib, crypto, and own dependencies. 

[dialyxir](https://github.com/jeremyjh/dialyxir) adds OTP application dependencies to the plt file. 

> OTP application dependencies are (transitively) added to your PLT by default. The applications added are the same as you would see displayed with the command mix app.tree.

BTW, [elixir 1.4](https://github.com/elixir-lang/elixir/blob/v1.4/CHANGELOG.md) adds Application inference so we don't need to add all dependent OTP apps to applications list. 

> Mix v1.4 now automatically infers your applications list as long as you leave the `:applications` key empty.

It's a awesome change to simplify `mix.exs` and prevent errors. If you don't need to add a application to your runtime list, then just add `runtime: false` option.

```
{:plug_rails_cookie_session_store, "~> 0.1", runtime: false},
```

In this case, you need to add it to PLT manually.

```elixir
def project do
  [
    dialyzer: [
      plt_add_apps: [:plug_rails_cookie_session_store],
    ]
  ]
end
```

February 6 2017, by deepblue
