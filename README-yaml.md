# YAML Formatting Guide

YAML (YAML Ain't Markup Language) is a human-readable data serialization format commonly used for configuration files.

## Basic Syntax

```yaml
# Comments start with #
key: value
number: 42
boolean: true
null_value: ~
```

## Strings

```yaml
plain: hello world
quoted: "contains: special characters"
single: 'also valid'
multiline: |
  preserves
  line breaks
folded: >
  joins lines
  into one
```

## Collections

```yaml
# List
fruits:
  - apple
  - banana
  - cherry

# Inline list
colors: [red, green, blue]

# Nested map
server:
  host: localhost
  port: 8080
```

## Common Pitfalls

- Always use **spaces**, never tabs
- Strings with `:`, `#`, `{`, `[`, or leading `*`/`&` need quoting
- `yes`, `no`, `on`, `off` are parsed as booleans — quote them if you mean strings
- Indentation must be consistent within a block
