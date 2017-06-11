title: Introduction to Ruby
subtitle: Zylun's Developer Meetup
description: Zylun's Developer Meetup
author: Honey Jill Hubahib
theme: moon

<pre><code class="hljs">
Speaker.new({
  name: "Jill Hubahib"
  rubyist_since: "Early 2013",
  works_as: "Ruby on Rails Developer",
  code_at: "github.com/jillhubahib",
  email: "jillhubahib@gmail.com",
  slides: "jillhubahib.github.io/zylun-ruby-intro"
})
</code></pre>

!SLIDE

![Programmer's bestfriend](https://dab1nmslvvntp.cloudfront.net/wp-content/uploads/2015/06/14352535061.png)

## Ruby.is_a?

- Dynamic Interpreted Scripting Language
- Strong OOP
- High Level
- Best of everything in the scripting world
<pre><code class="hljs">
Ruby = [Smalltalk - unfamiliar syntax]
       + Perl's scripting power
       + Python's exception etc.
       + CLU's iterator
       + a lot more good things
</code></pre>

## Goals

- History
- Philosophy
- Features
- Why Ruby
- Implementations
- Installation
  * irb
- API
- Building Blocks
- Coding Exercises

<aside class="notes">
Many Ruby developers find it fun to work with Ruby, and fun is a great motivator when learning to code. Ruby is a very high level language, which means Ruby abstracts away (i.e. handles for you) most of the complex details of the machine. Thus, you can quickly build something from scratch with less lines of code.
<br/><br/>
Ruby was made popular by the Ruby on Rails framework, a full-stack web framework that makes prototyping a breeze, making it a web framework of choice for many startups and coding beginners alike.
<br/><br/>
Ruby is not the universal solution for programmers' problems. There will always be times when you'll need a particular language: the environment may dictate it, you may have special libraries you need, performance concerns, or simply an issue with training.
<br/><br/>
There are plenty of introductions, tutorials, articles and essays of different sorts which aim to guide the novice and advise the guru on how to get the most out of Ruby.
</aside>

## History

- Yukihiro "Matz" Matsumoto, Japan, February 23, 1993
- First public release v0.95 in 1995
- English-language, v1.3 in 1999
- First English language book "Programming Ruby"

<aside class="notes">
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

## Everything is an Object

<pre><code class="hljs">
1.class         # => Fixnum
'a'.class       # => String
:z.class        # => Symbol

class Foo
end
Foo.class       # => Class
Foo.new.class   # => Foo

5.times { print "We *love* Ruby -- it's outrageous!" }
</code></pre>

<aside class="notes">
In Ruby, everything is an object. Every bit of information and code can be given their own properties and actions. Object-oriented programming calls properties by the name instance variables and actions are known as methods.
<br/><br/>
In many languages, numbers and other primitive types are not objects. Ruby follows the influence of the Smalltalk language by giving methods and instance variables to all of its types. This eases one’s use of Ruby, since rules applying to objects apply to all of Ruby.
</aside>

## Flexibility

<pre><code class="hljs">
class Numeric
  def plus(x)
    self.+(x)
  end
end

y = 5.plus 6
# y is now equal to 11
</code></pre>

<aside class="notes">
Ruby is seen as a flexible language, since it allows its users to freely alter its parts. Essential parts of Ruby can be removed or redefined, at will. Existing parts can be added upon. Ruby tries not to restrict the coder.
<br/><br/>
For example, addition is performed with the plus (+) operator. But, if you’d rather use the readable word plus, you could add such a method to Ruby’s builtin Numeric class.
<br/><br/>
+, -, and the like are not operators but method calls. They can, therefore, be overloaded by new definitions.
</aside>

## Dynamically Typed

<pre><code class="hljs">
def foo(bar)
  bar * 2
end

foo(1)    # => 2
foo('a')  # => "aa"
</code></pre>

## Duck Typing

<pre><code class="hljs">
"a".respond_to? :size  # => true
1.respond_to? :+       # => true
1.respond_to? :inject  # => false
</code></pre>

## Mixins

<pre><code class="hljs">
class MyArray
  include Enumerable
end
</code></pre>

<aside class="notes">
Unlike many object-oriented languages, Ruby features single inheritance only, on purpose. But Ruby knows the concept of modules (called Categories in Objective-C). Modules are collections of methods.
<br/><br/>
Classes can mixin a module and receive all its methods for free. For example, any class which implements the each method can mixin the Enumerable module, which adds a pile of methods that use each for looping.
</aside>

## Other features

- Exception handling
- Garbage collection
- Easy to extend
- Thread
- Cross platform
- Introspection, reflection and Meta programming

<aside class="notes">
Ruby has exception handling features, like Java or Python, to make it easy to handle errors.
<br/><br/>
Ruby features a true mark-and-sweep garbage collector for all Ruby objects. No need to maintain reference counts in extension libraries. As Matz says, “This is better for your health.”
<br/><br/>
Writing C extensions in Ruby is easier than in Perl or Python, with a very elegant API for calling Ruby from C. This includes calls for embedding Ruby in software, for use as a scripting language. A SWIG interface is also available.
<br/><br/>
Ruby features OS independent threading. Thus, for all platforms on which Ruby runs, you also have multithreading, regardless of if the OS supports it or not, even on MS-DOS!
<br/><br/>
It is developed mostly on GNU/Linux, but works on many types of UNIX, Mac OS X, Windows, DOS, BeOS, OS/2, etc.
</aside>

## Why Ruby

- Easy and Fun
- Productive
- Awesome Community

!SLIDE

![Ruby Hug](https://brightonruby.com/images/2014/hone02.jpg)

!SLIDE

![Rubies](https://raw.githubusercontent.com/alexch/ruby_notes/master/rubies.png)

## Implementations

- MRI (*M*atz’s *R*uby *I*nterpreter) or CRuby (since it is written in C)
- [JRuby](http://jruby.org/) is Ruby atop the JVM
- [Rubinius](http://rubini.us/) is Ruby written in Ruby
- [MacRuby](http://www.macruby.org/) is a Ruby that’s tightly integrated with Apple’s Cocoa libraries for Mac OS X
- [mruby](http://mruby.org/) is a lightweight implementation of Ruby
- [IronRuby](http://www.ironruby.net/) is an implementation tightly integrated with the .NET Framework
- [MagLev](http://ruby.gemstone.com/) is a fast, stable, Ruby implementation with integrated object persistence and distributed shared cache.
- [Cardinal](https://github.com/parrot/cardinal) is a Ruby compiler for Parrot Virtual Machine (Perl 6)


<aside class="notes">
Ruby, as a language, has a few different implementations. They are often useful in certain situations, provide extra integration to other languages or environments, or have special features that MRI doesn’t (e.g. operational goals and technical constraints.)
<br/><br/>
JRuby is a Ruby atop the JVM (Java Virtual Machine), utilizing the JVM’s optimizing JIT compilers, garbage collectors, concurrent threads, tool ecosystem, and vast collection of libraries.
<br/><br/>
Rubinius is ‘Ruby written in Ruby’. Built on top of LLVM, Rubinius sports a nifty virtual machine that other languages are being built on top of, too.
<br/><br/>
mruby is a lightweight implementation of the Ruby language that can be linked and embedded within an application. Its development is led by Ruby’s creator Yukihiro “Matz” Matsumoto.
<br/><br/>
The real star in term of performance is Ruby+Truffle+Graal(experimental) JRuby backend being worked on by Oracle Labs. It implements Ruby with the Truffle AST framework and the Graal JIT VM. The claimed performance gains are already phenomenal – up to around 30x MRI in non-synthetic benchmarks. The results of this project could make us rethink what is possible with dynamic languages, and it may open Ruby to the worlds of scientific computing and artificial intelligence.
https://www.sitepoint.com/projects-that-are-making-blazing-fast-ruby-a-reality/
</aside>

!SLIDE

![rvm vs. rbenv](http://jonathan-jackson.net/images/rvm-rbenv-install.png)

## RVM

<pre><code class="hljs">
$ rvm install 2.1.1
$ rvm use 2.1.1
$ ruby -v
ruby 2.1.1p76 (2014-02-24 revision 45161) [x86_64-darwin12.0]
$ which ruby
/Users/rys/.rvm/rubies/ruby-2.1.1/bin/ruby
</code></pre>

## irb

<aside class="notes">
Show `ri`
</aside>

## API

[https://ruby-doc.org](https://ruby-doc.org)

- Core
- Standard

<aside class="notes">
By default, Ruby always loads its core classes and modules when a script is executed. Core objects like Numbers(integers, floats), Strings, Arrays, Hashes, Files, Regular Expressions, Symbols, Threads, Times and dates, etc. Most likely, this is not going to be enough. That’s when the Standard Library comes into play: it’s a large collection of internal libraries that ships with every Ruby implementations. There are libraries to connect to the Internet, to read/write to various file formats such as CSV or YAML, to work with files and paths, access system features, and so on.
Unlike core classes, standard libraries must be required specifically if needed, before they can be used.
https://h3rald.com/ruby-compendium/book/core-stdlib.html#core-stdlib
</aside>

__SKIP__
<aside class="notes">
</aside>

<pre><code class="hljs">
</code></pre>
__END__