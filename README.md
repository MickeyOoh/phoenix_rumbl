# Rumbl

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