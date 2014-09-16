# bundle install した時 nokogiri が "libiconv is missing."でインストールできなかった時

## Macの場合
```
# homebrew公式に libiconv が無いので libiconv formula を追加
brew tap homebrew/dupes

# libxml2、libxslt、libiconv のインストール
brew install libxml2 libxslt libiconv
brew link --force libxml2 libxslt libiconv

# nokogiri 用のビルド設定をbundlerにいれてやる
bundle config build.nokogiri --use-system-libraries

# 無事インストールできるはず
bundle install
```

## CentOSの場合
```
sudo yum -y install libxml2-devel
sudo yum -y install libxslt-devel
```
