# Skip confirmation

```
# app/model/<name_model>.rb

before_create :skip_email

def skip_email
  self.skip_confirmation!
end

```

# Protect admin route

```
# config/routes.rb

Rails.application.routes.draw do
  # ...
  scope "/#{ENV.fetch("ADMIN_ROUTE_SECRET")}" do
    devise_for :admin, ...

    namespace :admin do
      resource ...

      root "..."
    end
  end
end
```

```
# app/controllers/admin/base_controller.rb

class Admin::BaseController < ApplicationController
  def after_sign_in_path_for(_resource)
    admin_root_path
  end
end
```
