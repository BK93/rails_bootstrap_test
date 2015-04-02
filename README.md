## railsにbootstrapを入れる。

### 1. bootstrapのzipファイルをダウンロード
```
1. $ curl -o /tmp/bootstrap.zip -L https://github.com/twbs/bootstrap/releases/download/v3.1.1/bootstrap-3.1.1-dist.zip
2. $ unzip /tmp/bootstrap.zip -d /tmp
```
### 2. 展開が終わったらvendor/assets配下にcss/jsファイルを配置
```
$ cp /tmp/bootstrap-3.1.1-dist/css/bootstrap.min.css vendor/assets/stylesheets/
$ cp /tmp/bootstrap-3.1.1-dist/js/bootstrap.min.js vendor/assets/javascripts/
```

### 3. application.jsとapplication.cssに追記

app/assets/javascripts/application.js

```
// ...
//= require jquery
//= require jquery_ujs
//= require turbolinks
//= require bootstrap.min // ←追記
//= require_tree .
```

app/assets/stylesheets/application.css

```
/*
 *
 * ...
 *= require_tree .
 *= require bootstrap.min /* 追記 */
 *= require_self
 */
```

## サンプルは [app/views/layouts/application.html.erb](https://github.com/soyanchu/rails_bootstrap_test/blob/master/app/views/layouts/application.html.erb)参照
