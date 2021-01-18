```
  require 'sidekiq/api'

  Sidekiq::Queue.all.each {|x| x.clear}

  Sidekiq::Stats.new
```
