# Supported tags and respective `Dockerfile` links

-	[`2.3.4-xenial` (*2.3.4-xenial/Dockerfile*)](https://github.com/wanderio/docker/blob/master/2.3.4-xenial/Dockerfile)

# Quick reference

-	**Where to file issues**:  
	[https://github.com/wanderio/docker/issues](https://github.com/wanderio/docker/issues)

-	**Maintained by**:  
	[Wanderio](https://github.com/wanderio/docker)

# What is Ruby?

Ruby is a dynamic, reflective, object-oriented, general-purpose, open-source programming language. According to its authors, Ruby was influenced by Perl, Smalltalk, Eiffel, Ada, and Lisp. It supports multiple programming paradigms, including functional, object-oriented, and imperative. It also has a dynamic type system and automatic memory management.

> [wikipedia.org/wiki/Ruby_(programming_language)](https://en.wikipedia.org/wiki/Ruby_%28programming_language%29)

![logo](https://raw.githubusercontent.com/docker-library/docs/01c12653951b2fe592c1f93a13b4e289ada0e3a1/ruby/logo.png)

# How to use this image
This image is a fork of official Ruby image maintained by Docker. Find all details at https://hub.docker.com/_/ruby/.

## Create a `Dockerfile` in your Ruby app project

```dockerfile
FROM ruby:2.3.4-xenial

#install bundler
RUN gem install bundler

#add Gemfiles
ADD Gemfile Gemfile
ADD Gemfile.lock Gemfile.lock

#install Gems
RUN bundle install

#add rest of the code
ADD . .

CMD ["./your-daemon-or-script.rb"]
```

Put this file in the root of your app, next to the `Gemfile`.

You can then build and run the Ruby image:

```console
$ docker build -t my-ruby-app .
$ docker run --name my-running-script my-ruby-app
```


# License

View [license information](https://www.ruby-lang.org/en/about/license.txt) for the software contained in this image.
