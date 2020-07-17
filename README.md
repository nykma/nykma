```elixir
defmodule NykMa do
  import Integer, only: [is_odd: 1]
  import System, only: [find_executable: 1]

  def basic(:pronoun), do: "Nick Ma"
  def basic(:aka),     do: ~w(MeNyK moenayuki)
  def basic(:title),   do: "DevOps" ++ (if :rand.uniform(2) |> is_odd(), do: " maybe?", else: "")
  def basic(:tz),      do: "Asia/Shanghai"
  def basic(:geo),     do: basic(:timezone)
  def basic(:blog),    do: [ zh_CN: "https://nyk.ma" ]
  def basic(:email),   do: "aUBueWsubWE=" |> :base64.decode()
  def basic(:editor),  do: find_executable("emacs") || find_executable("sed")
  def basic(:gpg),     do: "https://keybase.io/nykma/pgp_keys.asc"

  def programming_language(:active_use) do
    ~w(elixir ruby php typescript emacslisp dart)a
  end
  def programming_language(:familiar) do
    ~w(python c sql html css)a
  end
  def programming_language(:know) do
    ~w(java go rust clojure ocaml)a
  end

  def framework(:active_use) do
    [
      ops: ~w(docker kubernetes helm ldap)a,
      elixir: ~w(phoenix ecto)a,
      ruby: ~w(rails sinatra)a,
      php: ~w(laravel)a,
      dart: ~w(flutter)a,
    ]
  end

  def human_language(:active_use), do: ~w(zh_CN en_US ja_JP)a
  def human_language(:know), do: ~w(de_DE ko_KR)a
end
```
