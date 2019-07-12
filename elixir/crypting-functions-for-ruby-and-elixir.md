# Crypting functions that return same result for ruby and elixir

Here is an useful matrix when exchanging data or porting to another language.

| Ruby                        | Elixir                                                   |
|-----------------------------|:--------------------------------------------------------:|
| URI.escape                  | URI.encode                                               |
| CGI.escape                  | URI.encode_www_form                                      |
| Digest::SHA256.hexdigest(s) | :crypto.hash(:sha256, s) |> Base.encode16(case: :lower)  |
| Digest::MD5.hexdigest       | :crypto.hash(:md5, token) |> Base.encode16(case: :lower) |

March 14 2017, by dongyoonlee
