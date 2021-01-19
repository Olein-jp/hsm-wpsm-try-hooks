# HAPPY SNOW MONKEY と Snow Monkey とのコラボ企画用リポジトリ

- 配信日時：2021年1月19日(火)10:00〜

## 配信で取り扱うフック候補リスト
- 見た目にわかりやすいアクションフックをどれか１つ（単純にHTML出力デモでOK？
-
-

### snow_monkey_get_template_part_args_{slug}

テンプレートパートの引数を書き換えるためのフック。例えば固定ページにシェアボタンを表示するために `templates/view/content-page` の `_display_top_share_buttons` を `true` にする。

### snow_monkey_template_part_render_{slug}

HTML を書き換えるためのフック。記事タイトルの下にサブタイトルを追加したいなど。

```
add_filter(
	'snow_monkey_template_part_render_template-parts/content/entry/header/header',
	function( $html ) {
		return preg_replace(
			'|(<h1 class="c-entry__title">.+?</h1>)|ms',
			'$1<span>サブタイトル</span>',
			$html
		);
	}
);
```

### snow_monkey_get_template_part_{slug}

テンプレートをつくらずにテンプレートの上書きをするためのフック。

### Snow Monkey のアクションフック一覧

https://github.com/inc2734/snow-monkey/wiki/Action-hooks

### Snow Monkey のフィルターフック一覧

https://github.com/inc2734/snow-monkey/wiki/Filter-hooks
