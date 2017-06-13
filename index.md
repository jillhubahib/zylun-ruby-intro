title: Introduction to Ruby
subtitle: CoDev's Developer Meetup
description: CoDev's Developer Meetup
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
![Matz joins Heroku](https://heroku-blog-files.s3.amazonaws.com/posts/1473343689-matz.png)

!SLIDE

![Ruby History](https://image.slidesharecdn.com/rochester-on-rails-introduction-to-ruby-1198772254216925-5/95/rochester-on-rails-introduction-to-ruby-4-728.jpg?cb=1198743460)

## Versions

- 0.95
- 1.8
- 1.9
- 2.0
  * 2.1
  * 2.2
- 2.3
- 2.4

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

<aside class="notes">
Dynamic type checking is the process of verifying the type safety of a program at runtime.
</aside>

!SLIDE

| Dynamically Typed | Statically Typed |
| ------------- |:-------------:|
| Types are bound at **execution time** | Types are bound at **compile time** |
| Flexibility ↑ | Flexibility ↓ |
| Execution Safety ↓ | Execution Safety ↑ |


## Duck Typing

![Quack Quack](https://userscontent2.emaze.com/images/ccbc2b01-3a6a-41b3-87c4-7d08794d3902/15a45dd5799004cf3f3fd4c5834339d0.jpeg)

<aside class="notes">
In Ruby, we rely less on the type (or class) of an object and more on its capabilities. Hence, Duck Typing means an object type is defined by what it can do, not by what it is. Duck Typing refers to the tendency of Ruby to be less concerned with the class of an object and more concerned with what methods can be called on it and what operations can be performed on it. In Ruby, we would use respond_to? or might simply pass an object to a method and know that an exception will be raised if it is used inappropriately.
</aside>

!SLIDE

<pre><code class="hljs">
>> 'A string'.respond_to?(:to_str)
=> true
>> Exception.new.respond_to?(:to_str)
=> false
>> 4.respond_to?(:to_str)
=> false
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
<br/><br/>
Reflection is the ability of a computer program to examine, introspect, and modify its own structure and behavior at runtime.
</aside>

## Why Ruby

- Easy and Fun
- Productive
- Awesome Community

<aside class="notes">
Programmers use the term syntactic sugar to refer to special rules that let you write your code in a way that doesn't correspond to the normal rules but that is easier to remember how to do and looks better.
</aside>

!SLIDE

![Ruby Hug](https://yuneoh.com/wp-content/uploads/2017/01/LTK-701-044-RubyConf-Bohol-2017_1200x6308.jpg`)

!SLIDE

![Rubies](https://raw.githubusercontent.com/alexch/ruby_notes/master/rubies.png)

## Implementations

- MRI (**M**atz’s **R**uby **I**nterpreter) or CRuby
- [JRuby](http://jruby.org/)
- [Rubinius](http://rubini.us/)
- [MacRuby](http://www.macruby.org/)
- [mruby](http://mruby.org/)
- [IronRuby](http://www.ironruby.net/)
- [MagLev](http://ruby.gemstone.com/)
- [Cardinal](https://github.com/parrot/cardinal)


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

## Rubygems

[https://rubygems.org/](https://rubygems.org/)

![Rubygems](https://i2.wp.com/www.nextofwindows.com/wp-content/uploads/2015/01/2015-01-26_1724.png)

## Strings and Variables

<pre><code class="hljs">
'Hello, CoDev!'

name = 'CoDev'     # => "CoDev"
"Hello, #{name}!"  # => "Hello, CoDev!"
</code></pre>

<aside class="notes">
Credits to https://www.slideshare.net/Narnach/an-introduction-to-ruby-2449085
</aside>

## Methods

<pre><code class="hljs">
str = 'Hello, CoDev!'
str.size                        # => 17
str.sub('CoDev', 'World')       # => "Hello, World!"

def greet(name='Jill')
  "Greetings, #{name}!"
end

puts greet                      # => Greetings, Jill!
puts greet('CoDev')             # => Greetings, CoDev!
</code></pre>

## Numbers

<pre><code class="hljs">
1 + 2          # => 3
1 + 2.1        # => 3.1
2**10          # => 1024
9 / 2          # => 4
5 % 3          # => 2
-3.abs         # => 3
1.class        # => Fixnum
(2**50).class  # => Bignum
1.3.class      # => Float
</code></pre>

## Arrays

<pre><code class="hljs">
Array.new                # => []
[1,2,3]                  # => [1, 2, 3]
[1] + [2] << 3           # => [1, 2, 3]
[1,2,3] - [2,3]          # => [1]
␠%w[one two]             # => ["one", "two"]
[1,2,3].pop              # => 3
[1,2].push(3)            # => [1, 2, 3]
[1,2,3].shift            # => 1
[2,3].unshift(1)         # => [1, 2, 3]
[1,3].insert(1,2)        # => [1, 2, 3]
</code></pre>

## Hashes

<pre><code class="hljs">
options = {name: 'CoDev'}
h = Hash.new         # => {}
h['string'] = 1
h[:symbol]  = 1
h                    # => {:symbol => 1, "string" => 1}
h.keys               # => [:symbol, "string"]
h[:symbol]           # => 1
</code></pre>

## Iterators

<pre><code class="hljs">
for n in 0..2
  puts n
end

(0..2).each do |n|
  puts n
end

[0,1,2].each {|n| puts n}
</code></pre>

## Enumerable

<pre><code class="hljs">
ary = [1,2,3]
ary.map {|n| n * 2}              # => [2, 4, 6]
ary.select {|n| n % 2 == 0}      # => [2]
ary.inject(0) {|sum, n| sum + n} # => 6
</code></pre>

## Control Structures

<pre><code class="hljs">
if some_condition
  # ...
elsif other_condition
  # ...
else
  # ...
end

while condition
  # ...
end

puts 'lol' if funny?
</code></pre>

## Regular Expressions

<pre><code class="hljs">
str = 'Hello, world!'
str.gsub(/[aeiou]/, '*')      # => "H*ll*, w*rld!"
str =~ /w(or)ld/              # => 7
$1                            # => 'or'
match = str.match(/w(or)ld/)  # => #<MatchData "world" 1:"or">
match[0]                      # => "world"
match[1]                      # => "or"
</code></pre>

## Error Handling

<pre><code class="hljs">
begin
  raise 'Standard error'
rescue => e
  p e
end

begin
  raise StandardError.new('Oh, oh')
rescue RuntimeError
  puts 'runtime'
rescue StandardError
  puts 'standard'
end
</code></pre>

## System Interaction

<pre><code class="hljs">
system 'ls'
output = `ls`

ARGV

File.open('test.txt', 'w') do |file|
  file.write("line\n")
  file.puts("line")
end

File.read('test.txt')
</code></pre>

## Classes

<pre><code class="hljs">
class Calc
  attr_accessor :factor

  def initialize(factor=2)
    @factor = factor
  end

  def multiply(value)
    @factor * value
  end
end

calc = Calc.new
calc.multiply 5  # => 10
calc.factor = 3
calc.multiply 5  # => 15
</code></pre>

## Inheritance

<pre><code class="hljs">
class Foo
  def greet
    "Hi, #{value}"
  end
  def value
    "foo"
  end
end
class Bar < Foo
  def value
    "bar"
  end
end
Foo.new.greet # => "Hi, foo"
Bar.new.greet # => "Hi, bar"
</code></pre>

## Mixins & Open Classes

<pre><code class="hljs">
  module Even
    def even?
      self % 2 == 0
    end
  end

  class Fixnum
    include Even
  end

  1.even? # => false
  2.even? # => true
</code></pre>

## Class methods

<pre><code class="hljs">
class Foo
  def self.bar
    "BAR!"
  end

  def bar
    "bar"
  end
end

Foo.bar      # => "BAR!"
Foo.new.bar  # => "bar"
</code></pre>

## EXERCISES

__SKIP__
<aside class="notes">
</aside>

<pre><code class="hljs">
</code></pre>
__END__