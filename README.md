```nix
{
  description = "Nyk Ma";
  inputs = {
    nixpkgs.url = "github:NixOS/nixpkgs/nixpkgs-unstable";
  };
  outputs = { nixpkgs, ... }:
    let
      system = "x86_64-linux";
      pkgs = import nixpkgs { inherit system; };
    in
    {
      meta = rec {
        username = "nykma";
        pronoun = "Nick Ma";
        title = "Senior DevOps";
        tz = "Asia/Shanghai";
        geo = tz;
        blog = [{
          zh_CN = "https://nyk.ma";
        }];
        email = "aUBueWsubWE=";
        editors = with pkgs; [ emacs ];
        gpg = builtins.fetchurl "https://keybase.io/nykma/pgp_keys.asc";
      };
      
      programmingLanguage = {
        favorite = pkgs.rustc;
        activeUse = with pkgs; [ gcc rustc typescript go solc emacs nix ];
        familiar = with pkgs; [ ruby elixir php python3 postgresql16 ];
        know = with pkgs; [ jdk dart clojure ocaml ];
      };

      framework = {
        activeUse = {
          cxx = with pkgs; [ drogon ];
          ops = with pkgs; [ nix docker kubernetes kubernetes-helm openldap ];
          golang = [ "gin" "gorm" "xorm" "ent" "go-ethereum" ];
          rust = [ "tokio" "warp" "async_graphql" "diesel" "aragog" ];
        };
        familiar = {
          elixir = [ "phoenix" "ecto" ];
          ruby = with pkgs.rubyPackages; [ sinatra rails ];
          php = [ "laravel" ];
        };
        know = {
          java = with pkgs; [ spring-boot-cli ];
          dart = [ pkgs.flutter ];
        };
      };

      tools.must = with pkgs; [ emacs fish git bat btop exa mosh zellij pueue st ];

      humanLanguage = {
        activeUse = [ "zh_CN" "en_US" "ja_JP" ];
        know = [ "de_DE" "ko_KR" ];
      };
    };
}
```
