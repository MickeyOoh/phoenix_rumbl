Annotation機能が動作しない。
----
エラー内容:
```
** (UndefinedFunctionError) function AnnotationView.__resource__/0 is undefined (module AnnotationView is not available)
```

原因:
`alias RumblWeb.AnnotationView` のAnnotationViewの定義がなかった

```video_channel.ex
01  alias RumblWeb.AnnotationView         # 追加した。
02
03  def join("videos:" <> video_id, _params, socket) do
04    video_id = String.to_integer(video_id)
05    video = Multimedia.get_video!(video_id)
06
07    annotations =
08          video
09          |> Multimedia.list_annotations()
10          |> Phoenix.View.render_many(AnnotationView, "annotation.json")
11
12    {:ok, %{annotations: annotations}, assign(socket, :video_id, video_id)}
13  end
```


感想:
本に従い、コード化しているのため、気がつかなかった。おそらく、いちからコードを作る場合は気がつくだろうと、思う。
また、コンパイラ時に、Line 10の `AnnotationView` の定義がどこにもないと明確に言ってくれたら良いのに、 **不親切なコンパイラ** だ。

