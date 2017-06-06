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
- Load extension libraries dynamically if an OS allows
- OS independent threading
- Highly portable


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

!SLIDE

![Rubies](https://raw.githubusercontent.com/alexch/ruby_notes/master/rubies.png)

## Implementations

- MRI (“Matz’s Ruby Interpreter”) or CRuby (since it is written in C)
- [JRuby](http://jruby.org/) is Ruby atop the JVM
- [Rubinius](http://rubini.us/) is ‘Ruby written in Ruby’
- [MacRuby](http://www.macruby.org/) is a Ruby that’s tightly integrated with Apple’s Cocoa libraries for Mac OS X
- [mruby](http://mruby.org/) is a lightweight implementation of Ruby
- [IronRuby](http://www.ironruby.net/) is an implementation “tightly integrated with the .NET Framework”


<aside class="notes">
Ruby, as a language, has a few different implementations. They are often useful in certain situations, provide extra integration to other languages or environments, or have special features that MRI doesn’t.
<br/><br/>
JRuby is a Ruby atop the JVM (Java Virtual Machine), utilizing the JVM’s optimizing JIT compilers, garbage collectors, concurrent threads, tool ecosystem, and vast collection of libraries.
<br/><br/>
Rubinius is ‘Ruby written in Ruby’. Built on top of LLVM, Rubinius sports a nifty virtual machine that other languages are being built on top of, too.
<br/><br/>
mruby is a lightweight implementation of the Ruby language that can be linked and embedded within an application. Its development is led by Ruby’s creator Yukihiro “Matz” Matsumoto.
<br/><br/>
</aside>