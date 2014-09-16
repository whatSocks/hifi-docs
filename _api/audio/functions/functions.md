---
layout: doc
title: Functions
collection: api
category: audio
developer: true
---

Click is a Python package for creating beautiful command line interfaces in a composable way with as little code as necessary. It's the Command
Line Interface Creation Kit. It's highly configurable but comes with sensible defaults out of the box.

It aims to make the process of writing command line tools quick and fun
while also preventing any frustration caused by the inability to implement
an intended CLI API.

Click in three points:

*   arbitrary nesting of commands
*   automatic help page generation
*   supports lazy loading of subcommands at runtime

What does it look like?  Here is an example of a simple Click program:

	{% highlight python linenos %}
	@click.command()
	@click.option('--count', default=1, help='Number of greetings.')
	@click.option('--name', prompt='Your name',
		help='The person to greet.')
	def hello(count, name):
		"""Simple program that greets NAME for a total of COUNT times."""
		for x in range(count):
			click.echo('Hello %s!' % name)
			
    if __name__ == '__main__':
		hello()
	{% endhighlight %}

And what it looks like when run:

	{% highlight bash %}
	$ python hello.py --count=3
    Your name: John
    Hello John!
    Hello John!
    Hello John!
	{% endhighlight %}

It automatically generates nicely formatted help pages:

	{% highlight sh %}
	$ python hello.py --help
    Usage: hello.py [OPTIONS]
	
	Simple program that greets NAME for a total of COUNT times.
	  
    Options:
      --count INTEGER  Number of greetings.
      --name TEXT      The person to greet.
      --help           Show this message and exit.
	{% endhighlight %}


You can get the library directly from PyPI:

	{% highlight bash %}
    $ pip install click
	{% endhighlight %}