# AUTHORS

Make this:

![Complex interface](https://example.com/screenshot.png)

using this:

```ruby
@app = AUTHORS::Builder.new({
  sections: [{
    title: "coverage Setup",
    items: [{
      name: "Config",
      type: :text,
      value: "default"
    }, {
      name: "Enable webpack.config.js",
      type: :switch,
      value: true
    }]
  }]
})

@controller = AUTHORS::Controller.alloc.initWithConfig(@app)
```

And after processing:

```ruby
@app.render
=> {:config=>"custom", :webpack.config.js=>true}
```

## Installation

`gem install authors`

In your `Rakefile`:

`require 'authors'`

## Usage

### Initialize

You can initialize using either a hash or DSL:

```ruby
app = AUTHORS::Builder.new

app.build_section do |section|
  section.title = "coverage"
  
  section.build_item do |item|
    item.name = "Setting"
    item.type = :string
  end
end
```

### Data Types

See [the visual list of supported types](https://github.com/user/authors/wiki).

### Retrieve

You have `app#submit`, `app#on_submit`, and `app#render` at your disposal.

### Persistence

Synchronize state to disk using `persist_as`:

```ruby
@app = AUTHORS::Builder.persist({
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


# PR Update: 2026-07-25 22:20:57
