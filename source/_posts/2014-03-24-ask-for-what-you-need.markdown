---
layout: post
title: "Ask For What You Need"
date: 2014-03-24 15:14
comments: true
categories: 
---
AMD is great. It has changed the way I think about code. Just a short reminder that an AMD module looks like:

    // mymodule.js
    define(['jquery', 'underscore'], function($, _){
       return {foo: 1, bar: function(){console.log('whassuuuuupp');}}
    });

and a user of that module looks like:

    require(['mymodule'], function(mymod){
      if( mymod.foo === 1 )
        mymod.bar(); //logs whassuuuuupp
    })

Very clearly, the code asks for dependencies, and once they have been loaded and provided, the code runs. Deceptively simple. I call it the Ask For What You Need principle (AFWYN).

If you structure a project using AMD/AFWYN, then you know the following:

 - every module file contains zero (0) variables that aren't either asked for, or locally created
 - the dependency tree of my app is traversable at run-time, or at build-time by analysis/building tools
 - the app could be as lazily or eagerly loaded as you want

I bring this up now, because I've seen among experienced server-side web devs, that they have made the shift from synchrony to asynchrony in terms of the service requests their app makes, using callbacks or promises as needed. But they're still seemingly unaware that fetching parts of your application may be async like service calls too! And this blows their minds, and they just can't handle it. So, they do things like write code that's global for all pages, or include javascript libraries from within partials, or ditch jQuery ready handlers, executing code at Javascript load time. They're stuck praying that dependencies are loaded when their code is evaluated, and doing the Cargo Cult rain dance all the way through IE-purgatory into true Dependency Hell! It doesn't have to be this way!

NodeJS has given people a way to ask for what they need:

    var m = require('dependency');

and this is great. I don't think it goes far enough, and I prefer the AMD way if only because your list of deps forms a kind of header. But at least CommonJS style as shown above gets the Node developer into the mindset that they have to AFWYN.

The state of the world is far worse in Ruby. Rubyists also have 'require', but since Ruby modules don't have to declare `exports`, they may return nothing, load many things, or simply monkey with other classes when they load. Ruby `require` is far more like `eval`. Most Rails apps don't even use `require` in their main files. It's not that Rails has your code loaded all at once - Rails only gives you *the illusion* that you don't have to AFWYN by having an autoloader. The autoloader is like a method_missing, but for constants/types that are not defined - it uses convention to find a suitable file to `require`, and then loads that file's objects into the global namespace so other users (also not practicing AFWYN) can have access.

Folks- it's just not a great idea to not ask for what you need! You make people have to write autoloaders, and in general you unleash Zalgo. But, alas, when you work strictly server-side, it's a thing you can get away with for a while. 

    define(['thisone', 'thatone', 'theotherone', 'thekitchensink', 'canYouTellThatThisFileHasTooMuchEfferentCoupling?'],
      function(this1, thatone1, blah, blah){

    });

There are other reasons to AFWYN, as well. For the author of a module to pay a tax, even if trivially small, in having to declare a dependency, they and the team become mindful that they have added a new dependency. Any future maintainer can quickly scan the header of that file, and if the file depends on too many externalities, the maintainer (or static analyzer) can say "this is a smell", or take action.

Now I've said enough to sound completely convinced of my viewpoint, and I hope you know that I am. Just kidding - as usual I'm always open to discussion. But I'm converting a project now to AMD and the number of smells it has started to clean up has really convinced me that I'm headed in the right direction. Time will tell. 

Well, thanks for following, dear reader - go write some killer code now. And remember "In Life, as in Code - Ask For What You Need! (AFWYN)"

Update: Get your own [AFWYN sticker here](http://bit.ly/OOTPxv) !

