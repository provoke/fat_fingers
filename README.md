Fat Fingers
===========

A regex for fixing e-mail typos. (When "joe@gmail.com" enters in "joe@gmai.cm", fix it for him.)


### Let's help our users!

Just a few minutes ago, I got a "message failed to deliver" e-mail. Why? The user had entered in their e-mail address incorrectly. something@something.cm. So, now there's a bit of a hassle, where I have to fix their e-mail in the system, then re-initiate whatever process sent them that e-mail.

That's needless work.

**Fat Fingers is simply a Ruby method for cleaning up e-mail typos.**

It extends String objects with a method called `clean_up_typoed_email`.

All you need to do is attach that method to the user's e-mail address before you save them in the system.

There are some more instructions in the file itself, but it's really straightforward.


### So this isn't a library / plugin?

Nope! It's just a regex. A dozen or so lines of code, and we tell you where you can stick &rsquo;em!


### Does a mere regex deserve its own name?

Probably not. But too bad! This one got one!


### Aren't we disenfranchising users with this?

There's a similar tool, called [Mailcheck.js](https://github.com/Kicksend/mailcheck). It offers suggestions to the user, to check the e-mail they entered to make sure it's legit.

Fat Fingers is different, in that it does the work silently, without checking with the user.

Perhaps you want to roll with their approach. That's cool, and you'd be in good company. For my own projects, I'd rather not bother the user with something that's obviously wrong, if I can fix it on my own.

Put in other words, **there's absolutely no reason why a webapp should allow a user to register with the e-mail "@gmali.com", or "@gmail.ocm", or anything else that's clearly wrong.** And we shouldn't add friction to the signup process by asking them "are you sure you spelled your e-mail correctly?" (especially since they'll probably just say "of *course* I spelled my e-mail correctly", without actually checking it).


### Are there tests for this code? How can I know it won't false-positive something legitimate, like "@something.co"? ###

There *is* a full test suite for this code, baked right in. Just look at the [code](https://github.com/charliepark/fat_fingers/blob/master/fat_fingers.rb) and you'll see the unit tests starting around line 27.

Once you've cloned Fat Fingers to your system, just run `ruby fat_fingers.rb` and you'll see the output of the tests. They should all pass.

If there's a test case that we haven't written yet, just open up an "issue" here on the GitHub repo, and we'll get right on it. Or, if you want to write your own and send a pull request, that's cool, too.


### What failing e-mails does Fat Fingers catch? ###

It's a moderately-long list, mostly centered around the kinds of e-mail providers that have lots of users (and lots of users prone to typo their e-mail providers' names). Your 'Yaho's, your 'Hotmali's, your 'Gmial's. That sort of thing.

To see the full list of what Fat Fingers will catch, check out the tests (around line 27 of [the code](https://github.com/charliepark/fat_fingers/blob/master/fat_fingers.rb)).


### A quick note for users running this on Ruby < 1.9

Our multi-line chaining in this regex features the dots at the beginning of each line. Just move the periods to the end of the previous line if you're on Ruby 1.8.x.


### Code Climate!

[![Code Climate](https://codeclimate.com/badge.png)](https://codeclimate.com/github/charliepark/fat_fingers)

### Make it better!

I'd love to hear suggestions, critiques, and improvements. Feel free to fork it, ask me to pull in changes, and so on. I'd also love any test improvements.