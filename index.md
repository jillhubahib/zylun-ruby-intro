title: Introduction to Ruby
subtitle: Zylun's Developer Meetup
description: Zylun's Developer Meetup
author: Honey Jill Hubahib
theme: moon

__SKIP__
Ruby has been described as an absolutely pure object-oriented scripting language and a genuine attempt to combine the best of everything in the scripting world. Ruby is a language of careful balance. Its creator, blended parts of his favorite languages (Perl, Smalltalk, Eiffel, Ada, and Lisp) to form a new language that balanced functional programming with imperative programming.
__END__

!SLIDE

<pre><code class="hljs">
Speaker.new({
  name: "Jill Hubahib"
  rubyist_since: "Late 2012",
  works_as: "Ruby on Rails Developer",
  code_at: "github.com/jillhubahib",
  email: "jillhubahib@gmail.com",
  slides: "jillhubahib.github.io/zylun-ruby-intro"
})
</code></pre>

## Goals

- History
- Philosophy
- Highlights and Features
- Implementations
- API
- Installation
  * Versions
  * irb
- Building Blocks
- Coding Exercises

## History

- Yukihiro "Matz" Matsumoto, Japan, February 23, 1993
- First public release v0.95 in 1995
- English-language, v1.3 in 1999
- First English language book "Programming Ruby"

<aside class="notes">
Matz is a Mormon.
<br/><br/>
Influenced by Perl, Matz wanted to use a jewel name for his new language, so he named Ruby after a colleague’s birthstone. Later, he realized that Ruby comes right after Perl in several situations. In birthstones, pearl is June, ruby is July. When measuring font sizes, pearl is 5pt, ruby is 5.5pt. He thought Ruby was a good name for a programming language newer (and hopefully better) than Perl.
<br/><br/>
By 2000, Ruby was more popular than Python in Japan.
<br/><br/>
Much of the growth is attributed to the popularity of software written in Ruby, particularly the Ruby on Rails web framework.
</aside>

!SLIDE

![Ruby History](https://image.slidesharecdn.com/rochester-on-rails-introduction-to-ruby-1198772254216925-5/95/rochester-on-rails-introduction-to-ruby-4-728.jpg?cb=1198743460)

## Philosophy

> I believe people want to express themselves when they program. They don't want to fight with the language. Programming languages must feel natural to programmers. I tried to make people enjoy programming and concentrate on the fun and creative part of programming when they use Ruby. For me the purpose of life is partly to have joy. Programmers often feel joy when they can concentrate on the creative side of programming, So Ruby is designed to make programmers happy.

<aside class="notes">
Focus on the programmer, not the computer.
As Matz said, Ruby is not the fastest or even the powerful language, it's just good enough but people use it because its comfortable to use, its nice, its human centric design.
<br/><br/>
In the design of the Ruby language the primary focus was on productivity and the joy of programming. As a result, Ruby was too slow, because it focused on run-time efficiency, so the team tried to do many things to make Ruby faster, like replacing the virtual machines and every versions have introduce a lot of speedups especially Matz promise on the next major version which he called Ruby3x3, three times faster than Ruby 2.0, which will be released by 2020. They'll gonna introduced JIT technique from Java, improve concurrency and parallelism using guilds.
https://blog.heroku.com/ruby-3-by-3
</aside>