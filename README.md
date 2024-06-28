#  log.txt Format
A simple plain-text file format for recording events. Inspired by the simplicity and utility of the [todo.txt](https://github.com/todotxt/todo.txt).

## Example

```
2024-6-23T12:30 Eat lunch calories:659
2024-6-23T14:17 Amazon purchase price:24.33 category:home
2024-6-23T12:30 Eat dinner calories:712 
2024-6-24T06:32,2024-6-24T07:30 Workout
2024-6-24T08:13 Mood: feeling good
2024-6-25T11:22:33 Something down to the second
```

## Rules
- A single line in your log.txt file represents a single event.
- Events always begin with a date-time string.
- If the event has a duration, a comma `,` directly followed by another date-time string representing the stop time may be included
- Start and stop dates are in ISO 8601 date-time format or a valid substring of the format. The date portion is required (e.g. `2024-11-05`). Time segments are optional, but included time segments must have greater time segments defined. For example, `2024-11-05T12:55` is valid and but `2024-11-05T55` is invalid.
- A single space (` `) separates the date(s) from the event text
- The event text may contain colon (`:`) separated key value pairs. Where keys are non-empty word character (`\w+`) strings and values are non-whitespace character strings. (`[^\s]*`) separated by a colon and the value contains no whitespace. For example, `price:$12.43` is valid and `book:"Some Title"` is invalid.
- The event text may contain an single unnamed value at the end of the event. Any text after a colon followed by a space (`: `) will be considered this value. For example, in `2024-11-05T12:55 Read book score:7/10: Some Title`, the unnamed value would be `Some Title`
