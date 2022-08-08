```elixir
defmodule NykMa do
  import System, only: [find_executable: 1]

  def basic(:pronoun), do: "Nick Ma"
  def basic(:aka),     do: ~w(MeNyK moenayuki)
  def basic(:title),   do: "Senior DevOps"
  def basic(:tz),      do: "Asia/Shanghai"
  def basic(:geo),     do: basic(:tz)
  def basic(:blog),    do: [ zh_CN: "https://nyk.ma" ]
  def basic(:email),   do: "aUBueWsubWE=" |> :base64.decode()
  def basic(:editor),  do: find_executable("emacs") || find_executable("sed")
  def basic(:gpg),     do: "https://keybase.io/nykma/pgp_keys.asc"

  def programming_language(:active_use) do
    ~w(rust typescript golang solidity emacslisp)a
  end
  def programming_language(:familiar) do
    ~w(ruby elixir php python c sql html css)a
  end
  def programming_language(:know) do
    ~w(java dart clojure ocaml)a
  end

  def framework(:active_use) do
    [
      ops: ~w(docker kubernetes helm ldap)a,
      golang: ~w(gin gorm xorm ent go-ethereum)a,
      rust: ~w(tokio warp async_graphql diesel aragog)a,
      ruby: ~w(rails)a,
    ]
  end
  def framework(:familiar) do
    [
      elixir: ~w(phoenix ecto)a,
      ruby: ~w(sinatra)a,
      php: ~w(laravel)a,
    ]
  end

  def framework(:know) do
    [
      java: ~w(spring_boot)a,
      dart: ~w(flutter)a,
    ]
  end

  def tools_preference(:must) do
    [basic(:editor)] ++ ~w(fish bat btop exa)
  end

  def human_language(:active_use), do: ~w(zh_CN en_US ja_JP)a
  def human_language(:know), do: ~w(de_DE ko_KR)a
end
```
