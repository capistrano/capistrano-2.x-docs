Capistrano comes with a set of default log formatters to colorize your log output. If you want to disable all formatters, you can add the following line to your `deploy.rb` file:

```ruby
disable_log_formatters
```

You can add your own custom log formatters by using the `log_formatter` command in your `deploy.rb` file. You can call `log_formatter` multiple times, with either a hash or an array of hashes.

The options hash should have the following fields.
  
 * `:match`     - A regular expression of the row to match.
 * `:color`     - The color we want on the matching rows.
 * `:priority`  - What priority should this rule have (higher = more priority)
 * `:style`     - Special effect (:underline, :reverse, :blink)
 * `:level`     - Specify if this matcher should be bound to some of capistranos log levels (info,debug,...) 
 * `:prepend`   - Text to be prepended to the output
 * `:replace`   - Text to replace the matched regular expression.
 * `:timestamp` - Show current time with the output

### match 
 `:match` is a simple regular expression for the row that should be matched.

### color
 `:color` can have the following values:

 * `:hide`  (hides the row completely)
 * `:none`
 * `:black`
 * `:red`
 * `:green`
 * `:yellow`
 * `:blue`
 * `:magenta`
 * `:cyan`
 * `:white`

### priority
  `:priority` is an Integer defining the matchers priority.

### style
 `:style` can have the following values:

 * `:bright`
 * `:dim`
 * `:underscore`
 * `:blink`
 * `:reverse`
 * `:hidden`

## Example

```ruby
log_formatters = [
  { :match => /command finished/,      :color => :hide,    :priority => 10 },
  { :match => /executing command/,     :color => :blue,    :priority => 10, :style => :underscore },
  { :match => /^transaction: commit$/, :color => :magenta, :priority => 10, :style => :blink }
]

log_formatter(log_formatters)

log_formatter(:match => /git/, :color => :white, :priority => 20, :style => :reverse)
```