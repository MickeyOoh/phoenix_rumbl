# Rumbl


Routes
-----

```
         page_path  GET     /                                      RumblWeb.PageController :index
          user_path  GET     /users                                 RumblWeb.UserController :index
          user_path  GET     /users/new                             RumblWeb.UserController :new
          user_path  GET     /users/:id                             RumblWeb.UserController :show
          user_path  POST    /users                                 RumblWeb.UserController :create
       session_path  GET     /session/new                           RumblWeb.SessionController :new
       session_path  POST    /session                               RumblWeb.SessionController :create
       session_path  DELETE  /session/:id                           RumblWeb.SessionController :delete
         video_path  GET     /videos                                RumblWeb.VideoController :index
         video_path  GET     /videos/:id/edit                       RumblWeb.VideoController :edit
         video_path  GET     /videos/new                            RumblWeb.VideoController :new
         video_path  GET     /videos/:id                            RumblWeb.VideoController :show
         video_path  POST    /videos                                RumblWeb.VideoController :create
         video_path  PATCH   /videos/:id                            RumblWeb.VideoController :update
                     PUT     /videos/:id                            RumblWeb.VideoController :update
         video_path  DELETE  /videos/:id                            RumblWeb.VideoController :delete
         video_path  GET     /manage/videos                         RumblWeb.VideoController :index
         video_path  GET     /manage/videos/:id/edit                RumblWeb.VideoController :edit
         video_path  GET     /manage/videos/new                     RumblWeb.VideoController :new
         video_path  GET     /manage/videos/:id                     RumblWeb.VideoController :show
         video_path  POST    /manage/videos                         RumblWeb.VideoController :create
         video_path  PATCH   /manage/videos/:id                     RumblWeb.VideoController :update
                     PUT     /manage/videos/:id                     RumblWeb.VideoController :update
         video_path  DELETE  /manage/videos/:id                     RumblWeb.VideoController :delete
live_dashboard_path  GET     /dashboard                             Phoenix.LiveView.Plug :home
live_dashboard_path  GET     /dashboard/:page                       Phoenix.LiveView.Plug :page
live_dashboard_path  GET     /dashboard/:node/:page                 Phoenix.LiveView.Plug :page
          websocket  WS      /live/websocket                        Phoenix.LiveView.Socket
           longpoll  GET     /live/longpoll                         Phoenix.LiveView.Socket
           longpoll  POST    /live/longpoll                         Phoenix.LiveView.Socket
          websocket  WS      /socket/websocket                      RumblWeb.UserSocket
```

**mix phx.gen.html Multimedia Category category name:string**
-----
This command generates a controller, view, and template on the frontend. On the backend, it generates a *Multimedia* context, a *Multimedia Category* schema, and a migration. This generator, and the similar *mix phx.gen.json* generator, are typically used when we want to define all conveniences to expose a resource over the web interface.


sample:
```
$ mix phx.gen.html Multimedia Video videos user_id:references:users \
url:string title:string description:text

* creating lib/rumbl_web/controllers/video_controller.ex
* creating lib/rumbl_web/templates/video/edit.html.eex
* creating lib/rumbl_web/templates/video/form.html.eex
* creating lib/rumbl_web/templates/video/index.html.eex
* creating lib/rumbl_web/templates/video/new.html.eex
* creating lib/rumbl_web/templates/video/show.html.eex
* creating lib/rumbl_web/views/video_view.ex
* creating test/rumbl_web/controllers/video_controller_test.exs

* creating lib/rumbl/multimedia/video.ex
* creating priv/repo/migrations/xxxxxxxxxxxx_create_videos.exs
* creating lib/rumbl/multimedia.ex
* injecting lib/rumbl/multimedia.ex
* creating test/rumbl/multimedia_test.exs
* injecting test/rumbl/multimedia_test.exs
```

* the name of the context: *Mutlimedia*
* The name of the module that defines the schema: *Video*
* The plural form of the schema name: *videos*
* Each field, with some type information

**mix phx.gen.context Multimedia Category categories name:string**
-----
This command makes a *Multimedia* context, a *Multimedia.Category* schema and the associated migration. This generator is useful for generating a resource with all of its context functions without exposing that resource via the web interface. Note that if the context already exists, which is the case for *Multimedia*, the generator will inject the new category functions into the existing context.

**mix phx.gen.schema MultiMedia.Category categories name:string**
-----
a schema with a migration. It's useful for creating a resource when you want to define the context functions yourself.

**mix ecto.gen.migration create_categories**
----
This generator builds a new empty migration. Useful when the schema and context are already laid out, and all you need is to update the database.

Chp07 Ecto Queries and Constraints
-----
