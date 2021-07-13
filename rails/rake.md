# Parse args

```ruby

namespace :example do
  desc "Example"
  task first_task: :environment do
    options = {}

    p = OptionParser.new
    p.banner = "Usage: rake demo:create -- [options]"
    p.on("-y", "--year={YEAR}", Integer) { |v| options[:year] = v }
    p.on("-m", "--month={MONTH}", Integer) { |v| options[:month] = v }
    args = p.order!(ARGV) {}
    p.parse!(args)

    p(p.banner) && abort if options[:year].blank?
    p(p.banner) && abort if options[:month].blank?
  end
end
```

```sh
rake example:first_task -- --year=2021 --month=4
```
