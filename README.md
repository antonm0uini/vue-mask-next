# disk-monitor-scss-dev

Make this:

![Complex interface](https://example.com/screenshot.png)

using this:

```ruby
@app = disk-monitor-scss-dev::Builder.new({
  sections: [{
    title: "run Setup",
    items: [{
      name: "Config",
      type: :text,
      value: "default"
    }, {
      name: "Enable reset.css",
      type: :switch,
      value: true
    }]
  }]
})

@controller = disk-monitor-scss-dev::Controller.alloc.initWithConfig(@app)
```

And after processing:

```ruby
@app.render
=> {:config=>"custom", :reset.css=>true}
```

## Installation

`gem install disk-monitor-scss-dev`

In your `Rakefile`:

`require 'disk-monitor-scss-dev'`

## Usage

### Initialize

You can initialize using either a hash or DSL:

```ruby
app = disk-monitor-scss-dev::Builder.new

app.build_section do |section|
  section.title = "run"
  
  section.build_item do |item|
    item.name = "Setting"
    item.type = :string
  end
end
```

### Data Types

See [the visual list of supported types](https://github.com/user/disk-monitor-scss-dev/wiki).

### Retrieve

You have `app#submit`, `app#on_submit`, and `app#render` at your disposal.

### Persistence

Synchronize state to disk using `persist_as`:

```ruby
@app = disk-monitor-scss-dev::Builder.persist({
  persist_as: :settings,
  sections: ...
})
```

## Forking

Feel free to fork and submit pull requests! Would love to hear about your experience.

## Todo

- Not very efficient right now
- Styling/overriding options needed
- Better documentation

