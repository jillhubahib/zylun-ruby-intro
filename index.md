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

[https://www.ruby-lang.org](https://www.ruby-lang.org)

![Programmer's bestfriend](https://dab1nmslvvntp.cloudfront.net/wp-content/uploads/2015/06/14352535061.png)

<aside class="notes">
The official Ruby Home Page, originally written in Japanese and translated to English.
Tag line: A Programmer's Bestfriend.
<br/><br/>
Let me hold that thought in your mind, and hopefully as we go along it will unfold its own meaning, and together we'll assess this statement.
</aside>

## Ruby.is_a?

- Dynamic, reflective, general-purpose programming language
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

<aside class="notes">
Ruby is a very high level language, which means Ruby abstracts away (i.e. handles for you) most of the complex details of the machine. Thus, you can quickly build something from scratch with less lines of code.
<br/><br/>
Dynamic type checking is the process of verifying the type safety of a program at runtime.
<br/><br/>
Reflection is the ability of a computer program to examine, introspect, and modify its own structure and behavior at runtime.
<br/><br/>
CLU is a pioneering programming language created at the Massachusetts Institute of Technology (MIT) by Barbara Liskov and her students between 1974 and 1975. While it did not find extensive use, it introduced many features that are used widely now, and is seen as a step in the development of object-oriented programming (OOP).
</aside>

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
He works for the Japanese open source company, netlab.jp. Matsumoto is known as one of the open source evangelists in Japan. He has released several open source products, including cmail, the Emacs-based mail user agent, written entirely in Emacs Lisp. Ruby is his first piece of software that has become known outside Japan.
<br/><br/>
His demeanor has brought about a motto in the Ruby community: "Matz is nice and so we are nice," commonly abbreviated as MINASWAN.
<br/><br/>
Matz is a Mormon.
</aside>

!SLIDE
![Matz joins Heroku](https://heroku-blog-files.s3.amazonaws.com/posts/1473343689-matz.png)

<aside class="notes">
As of 2011, Matsumoto is the Chief Architect of Ruby at Heroku, an online cloud platform-as-a-service in San Francisco.
<br/><br/>
The name "Heroku" is merger of "heroic" and "haiku".[14][15] The Japanese theme is a nod to Matz for creating Ruby. The creators of Heroku did not want the name of their project to have a particular meaning, in Japanese or any other language, and so chose to invent a name.
</aside>

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

<aside class="notes">
Ruby 1.8 was initially released in August 2003, was stable for a long time, and was retired June 2013.
Ruby 1.8 has been the subject of several industry standards. JIS and ISO. Around 2005, interest in the Ruby language surged in tandem with Ruby on Rails, a web framework written in Ruby. Rails is frequently credited with increasing awareness of Ruby.
<br/><br/>
Ruby 1.9 was released in December 2007. Ruby 1.9 introduces many significant changes over the 1.8 series.
The VM in 1.8 is replace and runs many times faster.
<br/><br/>
Ruby 2.0 is released on February 24, 2013
<br/><br/>
Ruby 2.1.0 was released on Christmas Day in 2013. The release includes speed-ups, bugfixes, and library updates. Introduced generational garbage collection.
<br/><br/>
Ruby 2.2.0 was released on Christmas Day in 2014.
Ruby 2.2 introduces incremental GC algorithm to achieve shorter pause time due to GC.
<br/><br/>
Ruby 2.3.0 was released on Christmas Day in
<br/><br/>
Ruby 2.4.0 was released on Christmas Day in 2016.
<br/><br/>

</aside>

## Philosophy

> I believe people want to express themselves when they program. They don't want to fight with the language. Programming languages must feel natural to programmers. I tried to make people enjoy programming and concentrate on the fun and creative part of programming when they use Ruby. For me the purpose of life is partly to have joy. Programmers often feel joy when they can concentrate on the creative side of programming, So Ruby is designed to make programmers happy.

<aside class="notes">
In the design of the Ruby language the primary focus was on productivity and the joy of programming. As a result, Ruby was too slow, because it focused on run-time efficiency, so the team tried to do many things to make Ruby faster, like replacing the virtual machines and every versions have introduce a lot of speedups especially Matz promise on the next major version which he called Ruby3x3, three times faster than Ruby 2.0, which will be released by 2020. They'll gonna introduced JIT technique from Java, improve concurrency and parallelism using guilds.
https://blog.heroku.com/ruby-3-by-3
<br/><br/>
Focus on the programmer, not the computer.
As Matz said, Ruby is not the fastest or even the powerful language, it's just good enough but people use it because its comfortable to use, its nice, its human centric design.
<br/><br/>
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
<br/><br/>
2.4.1 :010 > 1.class
 => Integer
2.4.1 :011 > 1.class.superclass
 => Numeric
2.4.1 :012 > 1.class.superclass.superclass
 => Object
2.4.1 :013 > 1.class.superclass.superclass.superclass
 => BasicObject
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

!SLIDE

![Monkey-Patching](http://4.bp.blogspot.com/-WmuA8WUESDw/ULd2dAWD2cI/AAAAAAAAJls/eDxKoBO_tAQ/s1600/ruby-monkey-patch.jpg)

<aside class="notes">
Modification of an existing class at runtime with an intent to modify or extend existing functionality.
What can we patch in Ruby? Everything.
Light Side: Workaround for bugs in 3rd party code, testing, code instrumentation
Dark Side: Implicit changes, undocumented changes, unpredictable behaviour, patching the same.
So monkey-patch safely.
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
Dynamic types are bound at execution time while static types are bound at compile time.
In dynamic, flexibility is high yet execution safety is low. Static has the opposite case.
</aside>

## Duck Typing

![Quack Quack](https://userscontent2.emaze.com/images/ccbc2b01-3a6a-41b3-87c4-7d08794d3902/15a45dd5799004cf3f3fd4c5834339d0.jpeg)

<aside class="notes">
If it walks like a duck and quack likes a duck, then it must be a duck.
<br/><br/>
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

!SLIDE

<pre><code class="hljs">
class Duck
  def quack
    'Quack!'
  end

  def swim
    'Paddle paddle paddle...'
  end
end

class Goose
  def honk
    'Honk!'
  end

  def swim
    'Splash splash splash...'
  end
end

class DuckRecording
  def quack
    play
  end

  def play
    'Quack!'
  end
end

def make_it_quack(duck)
  duck.quack
end
puts make_it_quack(Duck.new)
puts make_it_quack(DuckRecording.new)

def make_it_swim(duck)
  duck.swim
end
puts make_it_swim(Duck.new)
puts make_it_swim(Goose.new)
</code></pre>

## Mixins

<pre><code class="hljs">
class MyArray
  include Enumerable
end
</code></pre>

<aside class="notes">
Unlike many object-oriented languages, Ruby features single inheritance only, on purpose. But Ruby knows the concept of modules (called Categories in Objective-C). Modules are collections of methods and constants. They cannot generate instances, the class does.
<br/><br/>
Modules may be mixed in to classes and other modules. The mixed in module’s constants and methods blend into that class’s own, augmenting the class’s functionality. Classes, however, cannot be mixed in to anything.
A class may inherit from another class, but not from a module.
A module may not inherit from anything.
<br/><br/>
Classes can mixin a module and receive all its methods for free. For example, any class which implements the each method can mixin the Enumerable module, which adds a pile of methods that use each for looping.
</aside>

!SLIDE

<pre><code class="hljs">
class Animal
  include Comparable

  attr_reader :legs

  def initialize(name, legs)
    @name, @legs = name, legs
  end

  def <=>(other)
    legs <=> other.legs
  end

  def inspect
    @name
  end
end

c = Animal.new("cat", 4)
s = Animal.new("snake", 0)
p = Animal.new("parrot", 2)

c < s             # => false
s < c             # => true
p >= s            # => true
p.between?(s, c)  # => true
[p, s, c].sort    # => [snake, parrot, cat]
</code></pre>

## Other features

- Simple syntax
- Exception handling
- [Garbage collection](https://blog.heroku.com/incremental-gc)
- Easy to extend
- Thread
- Cross platform
- Iterators and closures
- Introspection, reflection and Meta programming

<aside class="notes">
Ruby has exception handling features, like Java or Python, to make it easy to handle errors.
<br/><br/>
Why talk about GC? Run code faster. Chance to look at some of the more interesting algorithms in CS
Garbage collectors do much more than just collect garbage. Three things: Allocate memory, identify which objects are garbage, reclaim the memory from the identified garbage.
Body metaphor: We usually write business logic - the brain. GC is the beating heart: Provides memory, new objects, blood and nutrients. If your heart stops beating, you die. If your GC slows down (high blood pressure, clogged arteries), you suffer.
Ruby features a true mark-and-sweep garbage collector for all Ruby objects. No need to maintain reference counts in extension libraries. As Matz says, “This is better for your health.” <br/>
As compare to python: http://patshaughnessy.net/2013/10/24/visualizing-garbage-collection-in-ruby-and-python
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

<aside class="notes">
Many Ruby developers find it fun to work with Ruby, and fun is a great motivator when learning to code.
<br/><br/>
Ruby was made popular by the Ruby on Rails framework, a full-stack web framework that makes prototyping a breeze, making it a web framework of choice for many startups and coding beginners alike.
<br/><br/>
Ruby is not the universal solution for programmers' problems. There will always be times when you'll need a particular language: the environment may dictate it, you may have special libraries you need, performance concerns, or simply an issue with training.
<br/><br/>
There are plenty of introductions, tutorials, articles and essays of different sorts which aim to guide the novice and advise the guru on how to get the most out of Ruby.
<br/><br/>
Programmers use the term syntactic sugar to refer to special rules that let you write your code in a way that doesn't correspond to the normal rules but that is easier to remember how to do and looks better.
</aside>

!SLIDE

![Ruby Hug](https://yuneoh.com/wp-content/uploads/2017/01/LTK-701-044-RubyConf-Bohol-2017_1200x6308.jpg)

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

![Ruby speedup](https://pragtob.files.wordpress.com/2017/01/rubykon_2_speedup1.png)

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

## Interactive ruby

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
name = 'CoDev'               # => "CoDev"
"Hello, #{name}!"            # => "Hello, CoDev!"
"I l" + "o" * 5 + "ve Ruby!" # => "I looooove Ruby!"
</code></pre>

<aside class="notes">
Credits to https://www.slideshare.net/Narnach/an-introduction-to-ruby-2449085
<br/><br/>
The meaning of + depends on the object receiving that method.
<br/><br/>
# Substring <br/>
greeting = "Hello Codev!" <br/>
greeting[0..4] <br/>
# Common String Methods <br/>
<br/><br/>
greeting.length
<br/><br/>
sentence = "This is my sample sentence." <br/>
sentence.split
<br/><br/>
numbers = "one,two,three,four,five" <br/>
numbers.split(",")
<br/><br/>
greeting = "Hello Everyone!"
greeting.gsub("Everyone!","Friends!")
</aside>

## Naming Variables

### VM Requirement
- always start with a lowercase letter (underscore is permitted, though uncommon)
- have no spaces
- do not contain most special characters like $, @, and &

### Common Style
- use snake case where each word in the name is lowercase and connected by underscores (_)
- are named after the meaning of their contents, not the type of their contents
- aren’t abbreviated

!SLIDE

<pre><code class="hljs">
class Email
  def initialize(str, string2, headers_hash)
    # ...
  end

  # more methods ...
end

an_email = Email.new("Hi there, Ruby Monstas!", "2015-01-02", { :from => "Ferdous" })
</code></pre>

<pre><code class="hljs">
class Email
  def initialize(subject, date, headers)
    # ...
  end
end

email = Email.new("Hi there, Ruby Monstas!", "2015-01-02", { :from => "Ferdous" })
</code></pre>

<aside class="notes">
Note that it makes sense to try and pick names that reveal your intention. Just like programmers are obsessed about formatting, they also care a lot about how to name the things they create.
Choosing good names for your variables, methods, and classes is important, because this makes your code more expressive and easy to read.
<br/><br/>
But what’s the purpose of the first two arguments? All we know the author wants them to be strings.
<br/><br/>
The prefix an_ doesn’t add any kind of information. It’s just noisy, and adds clutter.
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

<aside class="notes">
Ruby philosopy is also the OO idea of telling the object to do something, instead of doing something with the object. So you don't do string(10) but 10.to_s.
<br/><br/>
Ruby methods that modify an object in-place and end in an exclamation mark are known as bang methods. By convention, the bang labels a method as dangerous - specifically, as the dangerous equivalent of a method with the same name but without the bang.
<br/><br/>
"hello".capitalize    #=> "Hello" <br/>
a = "hello" <br/>
a.capitalize!   #=> "Hello" <br/>
a               #=> "Hello"<br/>
<br/><br/>
The question mark has no special meaning to the Ruby interpreter. However, by convention, any method whose name ends with ? returns a value that answers the question posed by the method invocation. The empty? method of an array, for example, returns true if the array has no elements.
<br/><br/>
"hello".start_with?("hell")               #=> true
<br/><br/>
You can omit the return keyword in Ruby. The last line executed in a block of code is the value that is returned.
<br/><br/>
Ruby's use of parenthesis in a method is optional but base from a community best coding style to better use it.
</aside>

## Memoization

Is the process of storing a computed value to avoid duplicated work by future calls. Basic memoization is always going to fix into the following pattern:

- Perform some work
- Store the work result
- Use stored results in future calls

<pre><code class="hljs">
def current_user
  @current_user ||= User.find(session[:user_id])
end
</code></pre>

## Keyword Arguments

<pre><code class="hljs">
def hello_message(first_name:, last_name:)
  "Hello, #{first_name} #{last_name}"
end
hello_message(last_name: "Doe", first_name: "John")

def generate_thumbnail(name, width, height)
  # ...
end
dimensions = [240, 320]
generate_thumbnail("headshot.jpg", *dimensions)

def argument_capturing_method(*args)
  args
end
argument_capturing_method(1, 2, 3) # => [1, 2, 3]

def dual_argument_capturing_method(*args, **keyword_args)
  {args: args, keyword_args: keyword_args}
end

dual_argument_capturing_method(1, 2, 3, key: "value") # => {:args=>[1, 2, 3], :keyword_args=>{:key=>"value"}}
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

!SLIDE

<pre><code class="hljs">
number = 2 + 3 * 4
</code></pre>

<pre><code class="hljs">
number = 2.+(3.*(4))
</code></pre>

<aside class="notes">
If everything is an object then numbers are objects. If “doing things” means operating with methods by the way of calling them, then operators are methods.
<br/><br/>
But if we call methods on objects using that dot . notation, then where are the dots in 2 + 3 * 4? The trick is: Ruby adds them for you, silently.
<br/><br/>
Fun, isn’t it? These operators are all methods on numbers, and they can be called just like any other method. (The same is true for lots of other operators, as you can see in IRB, when you run 1.methods.sort.) The code above is valid Ruby code, and both lines do exactly the same.
This is something called “syntax sugar”, because it makes the language more sweet (no kidding).
http://ruby-for-beginners.rubymonstas.org/operators/methods.html
</aside>

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

<aside class="notes">
one = ["this", "is", "an", "array"] <br/>
one.sort <br/>
one <br/>
Try experimenting with these common methods on Array: first, last, shuffle
<br/><br/>
Parallel Assignment <br/>
a, b = [1, 2]
<br/><br/>
Arrays can contain all kinds of objects. Arrays are zero based, and can be nested.
<br/><br/>
Things to do with arrays <br/>
Add <br/>
[1, 2] + [3, 4] <br/>
Subtract <br/>
[:one, :two, :three, :four] - [:three, :four] <br/>
Multiple <br/>
["Ruby", "Monstas"] * 3 <br/>
Find Intersection <br/>
[1, 2, 3] & [2, 3, 4] <br/>
[1, 2, 3].first <br/>
[1, 2, 3].last <br/>
[1, 2, 3].length <br/>
[3, 1, 2].sort <br/>
[1, nil, 2, 3, nil].compact <br/>
[1, 2, 3].index(3) <br/>
[1, 2, 3, 4].rotate(2) <br/>
[[1, 2, 3], [4, 5, 6], [7, 8, 9]].transpose <br/>
</aside>

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

<aside class="notes">
A hash is an unordered collection where the data is organized into "key/value pairs", its like dictionaries.
A Hash assigns values to keys, so that values can be looked up by their key, which is basically the main purpose of a Hash.
Hashes can use any kind of objects as keys and values.
<br/><br/>
Symbol. It’s like a String, but it’s used like an identifier. They’re different from Strings and all symbols with the same name share the same memory.
> "a string".object_id
=> 70358630335100 <br/>
> "a string".object_id <br/>
=> 70358640625960 <br/>
> :a_symbol.object_id <br/>
=> 1086748 <br/>
> :a_symbol.object_id <br/>
=> 1086748 <br/>
<br/><br/>
Merge <br/>
{ "one" => "eins" }.merge({ "two" => "zwei" }) <br/>
> dictionary = { "one" => "eins" } <br/>
> dictionary.fetch("one") <br/>
=> "eins" <br/>
> dictionary.fetch("two") <br/>
KeyError: key not found: "two" <br/>
dictionary.length <br/>
dictionary.size <br/>
</aside>

## Blocks and Iterators

<pre><code class="hljs">
for n in 0..2
  puts n
end

(0..2).each do |n|
  puts n
end

[0,1,2].each {|n| puts n}

def threeTimes
  yield
  yield
  yield
end
threeTimes { puts "Hello" }

numbers = [1, 2, 3, 4, 5].collect.with_index do |number, index|
  number + index
end
p numbers
</code></pre>

<aside class="notes">
A block, essentially, is the same thing as a method, except it does not have a name, and does not belong to an object. A block is a piece of code that accepts arguments, and returns a value. A block is always passed to a method call.
A big advantage of having block is the principle Inversion of control. By accepting a block, from you as a programmer, the method can pass control to you. “Control” in this context refers to the question who gets to decide how things work.
<br/><br/>
Within the method, the block may be invoked, almost as if it were a method itself, using the yield statement. Whenever a yield is executed, it invokes the code in the block.
<br/><br/>
Methods on arrays and hashes that take a block are also called iterators.
<br/><br/>
Iterators in Ruby are chainable.
</aside>

## Enumerable

<pre><code class="hljs">
ary = [1,2,3]
ary.map {|n| n * 2}              # => [2, 4, 6]
ary.select {|n| n % 2 == 0}      # => [2]
ary.inject(0) {|sum, n| sum + n} # => 6
</code></pre>

<aside class="notes">
The Enumerable module provides a set of methods to traverse, search, sort and manipulate collections.
</aside>

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
puts 'cry' unless funny?
</code></pre>

## Regular Expressions

<pre><code class="hljs">
//.class    # Regexp

str = 'Hello, world!'
str.gsub(/[aeiou]/, '*')      # => "H*ll*, w*rld!"
str =~ /w(or)ld/              # => 7
$1                            # => 'or'

match = str.match(/w(or)ld/)  # => #<MatchData "world" 1:"or">
match[0]                      # => "world"
match[1]                      # => "or"
</code></pre>

<aside class="notes">
A regular expression is simply a way of specifying a pattern of characters to be matched in a string.<br/>
We can also use the match operator =~ to match a string against a regular expression. If the pattern is found in the string, =~ returns its starting position, otherwise it returns nil.
<br/><br/>
https://regexone.com/
</aside>

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

!SLIDE

![Ruby Exceptions](http://rubylearning.com/images/exception.jpg)

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

class Person
  def initialize(name)
    @name = name
  end

  def name
    @name
  end

  def password=(password)
    @password = password
  end
end
</code></pre>

<aside class="notes">
attr_accesor method which is used to define attributes for instances of a class.
<br/><br/>
Instance methods are defined inside the class body.
<br/><br/>
The special method initialize is called under the hood when the object has been created by the class method new.
<br/><br/>
Instance variables live in, and are visible everywhere in the object’s scope.
<br/><br/>
Objects have state (instance variables) and behaviour (methods).
</aside>

## Access Controls

- **Public** methods can be called by everyone
- **Protected** methods can be invoked only by objects of the defining class and its subclasses.
- **Private** methods cannot be called with an explicit receiver

<aside class="notes">
Instance and class variables are encapsulated and effectively private, and constants are effectively public.
</aside>

!SLIDE

<pre><code class="hljs">
class ClassAccess
  def m1          # this method is public
  end
  protected
    def m2        # this method is protected
    end
  private
    def m3        # this method is private
    end
end
ca = ClassAccess.new
ca.m1

class ClassAccess
  def m1       # this method is public
  end
  public :m1
  protected :m2, :m3
  private :m4, :m5
end

class Person
  def initialize(age)
    @age = age
  end
  def age
    @age
  end
  def compare_age(c)
    if c.age > age
      "The other object's age is bigger."
    else
      "The other object's age is the same or smaller."
    end
  end
  protected :age
end

chris = Person.new(25)
marcos = Person.new(34)
puts chris.compare_age(marcos)
#puts chris.age
chris.send(:age)
</code></pre>

<aside class="notes">
In Ruby, the inheritance hierarchy or the package/module don't really enter into the equation, it is rather all about which object is the receiver of a particular method call. When a method is declared private in Ruby, it means this method can never be called with an explicit receiver. Any time we're able to call a private method with an implicit receiver it will always succeed. This means we can call a private method from within a class it is declared in as well as all subclasses of this class
<br/><br/>
The variable scoping in Ruby (public, protected, private) is merely a suggestion and not a hard barrier like it is in other languages. There’s also this way of calling a private method: obj.send(:any_private_method?)
</aside>

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

## Overriding Private Methods

<pre><code class="hljs">
class ActiveRecord
  private
  def hi
    'I am private'
  end
end

class ActiveRecord
  def greet
    hi
  end
  private
  def hi
    'I am redefining you'
  end
end

a = ActiveRecord.new
p a.greet # => I am redefining you
-----------------------
class Client
  def print
    say
  end
  private
  def say
    "hello"
  end
end

class MyClient < Client
  def say
    "hello from an overridden private method"
  end
end

puts MyClient.superclass
my_client = MyClient.new
puts my_client.print
</code></pre>

<aside class="notes">
Inheritance creates tight coupling to the super class. Prefer delegation over inheritance to create elegant designs.
</aside>

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

<aside class="notes">
In Ruby, modules are somewhat similar to classes: they are things that hold methods, just like classes do. However, modules can not be instantiated. I.e., it is not possible to create objects from a module. And modules, unlike classes, therefore do not have a method new.
<br/><br/>
So, what are modules useful for?
With modules you can share methods between classes: Modules can be included into classes, and this makes their methods available on the class, just as if we’d copied and pasted these methods over to the class definition.
<br/><br/>
- Use case: for DRY (to centralize), move out clutter and hide away in another file
</aside>

## Class methods

<pre><code class="hljs">
# Way 1
class Foo
  def self.bar
    puts 'class method'
  end
end

Foo.bar # "class method"

# Way 2
class Foo
  class << self
    def bar
      puts 'class method'
    end
  end
end

Foo.bar # "class method"

# Way 3
class Foo; end
def Foo.bar
  puts 'class method'
end

Foo.bar # "class method"
</code></pre>

<aside class="notes">
Class methods are methods that are called on a class and instance methods are methods that are called on an instance of a class.
<br/><br/>
So when would you use a class method? Class methods are for anything that does not deal with an individual instance of a class.
</aside>

!SLIDE

![Programmer's bestfriend](https://dab1nmslvvntp.cloudfront.net/wp-content/uploads/2015/06/14352535061.png)

<aside class="notes">
1) Ruby allows you to simply express many straightforward concepts that you'd use when coding that other languages are more verbose - compare a Ruby 'Hello world' program to one in Java or another popular language, and
2) Ruby takes care of much of the non-business logic parts of your program which other languages need you to configure - stuff like compiling, garbage collection even type-declaration I guess could go in this column.
More experienced developers will tell you more. But basically it's a "programmer's best friend" because it removes as much of the non-programming work from programming and thus lets you concentrate on having fun writing up a piece of software.
https://www.reddit.com/r/learnruby/comments/49jz2m/why_is_ruby_a_programmers_best_friend/
</aside>

## Interactive Tutorial

- [Try Ruby](http://tryruby.org/)
- [Ruby Koans](http://rubykoans.com/)
- [Ruby Monk](https://rubymonk.com/)

<aside class="notes">
Try Ruby! <br/>
An interactive tutorial that lets you try out Ruby right in your browser. This 15-minute tutorial is aimed at beginners who want to get a feeling of the language.
<br/><br/>
Ruby Koans <br/>
The Koans walk you along the path to enlightenment in order to learn Ruby. The goal is to learn the Ruby language, syntax, structure, and some common functions and libraries. We also teach you culture.
<br/><br/>
RubyMonk <br/>
Discover Ruby idioms, learn lessons and solve problems, all in your browser!
<br/><br/>
</aside>

## EXERCISES

__SKIP__
<aside class="notes">
</aside>

<pre><code class="hljs">
</code></pre>

RESOURCES:
http://rubylearning.com/satishtalim/tutorial.html
http://ruby-for-beginners.rubymonstas.org/index.html
http://tutorials.jumpstartlab.com/projects/ruby_in_100_minutes.html
__END__