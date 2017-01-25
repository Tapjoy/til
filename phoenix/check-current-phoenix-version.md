# Check currently installed Phoenix version number

Unlike Rails on Ruby, the way to check a version number of currently installed Phoenix is not that clear and common.

I've tried to check the version of Phoenix by adopting familiar ways to the developer.
Like adding `--version` or `-v` tag after `phoenix` command and `mix` command.
But it didn't work.

After looking for it a bit, I found the way to find the version number of currently installed Phoenix. With `mix task`.

```shell
$ mix phoenix.new -v
Phoenix v1.2.0
```
Since *Phoenix Installer* that user get from Phoenix repository is just the application dependency, not an excutable. In order to do some stuff with Phoenix, you need to use `mix` task properly.
