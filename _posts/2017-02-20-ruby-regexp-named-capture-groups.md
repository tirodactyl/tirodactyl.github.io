---
layout: post
title: Ruby Regexp Named Capture Groups
date: 2017-02-20 13:10:29 -0800
tags: ruby regex regexp string notes
---
FYI, `String#=~` and `Regexp#=~` work slightly differently. I discovered
accidentally that strings captured from named capture groups are only assigned
to local variables with `Regexp#=~`.

Turns out it says this right in the Ruby String docs, but I just missed it and
discovered this through the console.

```ruby
"My name is Fred" =~ /My name is (.*)$/ #=> 0
$1 #=> "Fred"

"My name is Fred" =~ /My name is (?<name>.*)$/ #=> 0
$name #=> nil

/My name is (?<name>.*)$/ =~ "My name is Fred" #=> 0
$name #=> "Fred"

# Note that when using the above syntax, the Ruby parser will also define a
# local variable and assign the result of the capture group to that variable.
name #=> "Fred"

# This will only work if the parser detects 'regex literal =~ string' pattern.
regex = /(?<word>.*)/
regex =~ test #=> 0
word #=> undefined local variable

# Nor will it work if the parser detects a regexp literal using interpolation.
test = "test"
/(?<word>#{test})/ =~ test #=> 0
word #=> undefined local variable
```
