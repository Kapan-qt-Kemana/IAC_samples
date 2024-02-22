# event_examenesstudio

Make this:

![Complex interface](https://example.com/screenshot.png)

using this:

```ruby
@app = event_examenesstudio::Builder.new({
  sections: [{
    title: "playwright.config.js Setup",
    items: [{
      name: "Config",
      type: :text,
      value: "default"
    }, {
      name: "Enable mix.exs",
      type: :switch,
      value: true
    }]
  }]
})

@controller = event_examenesstudio::Controller.alloc.initWithConfig(@app)
```

And after processing:

```ruby
@app.render
=> {:config=>"custom", :mix.exs=>true}
```

## Installation

`gem install event_examenesstudio`

In your `Rakefile`:

`require 'event_examenesstudio'`

## Usage

### Initialize

You can initialize using either a hash or DSL:

```ruby
app = event_examenesstudio::Builder.new

app.build_section do |section|
  section.title = "playwright.config.js"
  
  section.build_item do |item|
    item.name = "Setting"
    item.type = :string
  end
end
```

### Data Types

See [the visual list of supported types](https://github.com/user/event_examenesstudio/wiki).

### Retrieve

You have `app#submit`, `app#on_submit`, and `app#render` at your disposal.

### Persistence

Synchronize state to disk using `persist_as`:

```ruby
@app = event_examenesstudio::Builder.persist({
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

