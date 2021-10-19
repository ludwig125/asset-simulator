## Jekyll を使用して GitHub Pages サイトを作成する

https://docs.github.com/ja/pages/setting-up-a-github-pages-site-with-jekyll/creating-a-github-pages-site-with-jekyll

> Jekyll を使用して GitHub Pages サイトを作成する前に、Jekyll と Git をインストールする必要があります。

#### Jekyll on Ubuntu インストール

https://jekyllrb.com/docs/installation/ubuntu/
```
sudo apt-get install ruby-full build-essential zlib1g-dev

echo '# Install Ruby Gems to ~/gems' >> ~/.zshrc
echo 'export GEM_HOME="$HOME/gems"' >> ~/.zshrc
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc

gem install jekyll bundler
```

> Jekyll をインストールし動作させるのには Bundler を使うようおすすめします。

https://bundler.io/

```
gem install bundler
```

#### 新しい Jekyll サイトを作成するには、jekyll new コマンドを使用します。

```
$ jekyll new --skip-bundle .
```

以下のファイルができた
```
404.html
Gemfile
README.md
_config.yml
_posts/
about.markdown
index.markdown
```

Gemfileを編集

```
# gem "github-pages" で始まる行を編集して github-pages を追加します。 行を次のように変更します。

gem "github-pages", "~> GITHUB-PAGES-VERSION", group: :jekyll_plugins
GITHUB-PAGES-VERSION をサポートされている最新バージョンの github-pages gem に置き換えます。 このバージョンについては、「依存関係バージョン」を参照してください。
```

https://pages.github.com/versions/
> github-pages	219

```
gem "github-pages", "~> 219", group: :jekyll_plugins

```


## 必要に応じて、サイトをローカルでテストします。 詳しい情報については、「Jekyll を使用して GitHub Pages サイトをローカルでテストする」を参照してください。

Jekyll を使用して GitHub Pages サイトをローカルでテストする
https://docs.github.com/ja/pages/setting-up-a-github-pages-site-with-jekyll/testing-your-github-pages-site-locally-with-jekyll

```
bundle install

bundle exec jekyll serve
(サーバが起動する)
 Auto-regeneration: enabled for '/home/ludwig125/go/src/github.com/ludwig125/asset-simulator'
    Server address: http://127.0.0.1:4000/

```

http://localhost:4000/ でサイトが見られる
