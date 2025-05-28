+++
date = '2025-05-27T20:06:52-05:00'
draft = false
title = 'Shear the Sheep'
tags = ['architecture']
categories = ['programming']
+++

As code grows, it evolves; that is the natural progression of software. New features get added and older unused ones get removed. But what happens if they don't? More often than not, this happens because "we might need this in the future!". It ends up like a sheep that hasn't been sheared in years, covered in matted wool that makes it three times the size it needs to be.

Why do we do this to ourselves? I think there are a few reasons. The first as mentioned above, we think we'll need it in the future or we don't have confidence in removing that piece of code. This is due to not understanding the consumers of your code. I can't tell you how many times I've seen large blocks of commented out code that have been there for years, doing absolutely nothing. I think a second reason is a lack of understanding in git. I fear that many developers don't understand that git is a journal of the evolution of your code, they think of it just as a mechanism of getting code from their machine to the production machine.

So what do you do if you find yourself with one of these overgrown sheep? One of these labyrinths of dead code paths that take hours to debug? My personal advice is don't be afraid to get in there shear that sheep. You can start by letting your IDE identify all the dead code. Start at the service level and start deleting everything grayed out. Rinse and repeat through the repositories. Delete those commented out code blocks that don't add anything but noise. They're all still available if you need them, they're just one checkout away. But I'm telling you you won't. The ideas that code was built on are long since dead. No one is missing a function that can't get to.  From there you have a better view of what *might* be used and can start making calls on what to try to remove.

What you will get out of this pruning is a cleaner code base and a better understanding of what you're maintaining. If you can get rid of 100 lines of code, that's 100 lines you don't have to consider when debugging. Most likely you'll be getting rid of 1000 lines, not just 100. You'll also have a better understanding of that code base. Cleaning takes you through a lot of code paths, some that have no documentation and have "just worked" in some janky configuration for years. You'll get a small peek into what's there and maybe you can infer some of the asks of the previous maintainers through some of their dead code. 

In conclusion, keep your code base neat, shear that sheep. 

![sheep](/sheep.jpg)
*Image downloaded from [unsplash](https://unsplash.com/photos/a-shaggy-sheep-standing-in-a-grassy-field-UHLFYLSDC24)*