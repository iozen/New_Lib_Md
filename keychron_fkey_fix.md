#keychron #fix #fkeys


## Getting the Function keys of a Keychron working on Linux

published on 2021-04-30 · tagged with [#debian](https://venthur.de/tags/debian.html), [#keychron](https://venthur.de/tags/keychron.html) and [#linux](https://venthur.de/tags/linux.html)

Having destroyed the third Cherry Stream keyboard in 4 years, I wanted to try a more substantial keyboard for a change. After some research I decided that I want a mechanical, wired, tenkeyless keyboard without any fancy LEDs.

At the end I settled for a [Keychron C1](https://www.keychron.com/products/keychron-c1-wired-mechanical-keyboard) with red switches. It meets all requirements, looks very nice and the price is reasonable.

## Surprise!

After the keyboard was delivered, I connected it to my Debian machine and was unpleasantly surprised to notice that the Function-keys did _not work at all_. The keyboard shares the Multimedia keys with the F-keys and you have an `fn` key that supposedly switches between the two modes, like you’re used to on a laptop. On Linux, however you cannot access the F-keys at all: pressing `fn + F1` or `F1` makes no difference, you’ll always get the Multimedia key. Switching the keyboard between “Windows” and “Mac” mode makes no difference either, in both modes the F-keys are not accessible.

Apparently Keychron is aware of the problem, because the quick start manual tells you:

> “We have a Linux user group on facebook. Please search “Keychron Linux Group” on facebook. So you can better experience with our keyboard.”

Customer support at its finest!

So at this point you should probably just send the keyboard back, get the refund and buy a proper one with functioning F-keys.

## The fix

Test if this command fixes the issue and enables the `Fn +` F-key-combos:

`# as root: echo 2 > /sys/module/hid_apple/parameters/fnmode`

Depending on the mode the keyboard is in, you should now be able to use the F-keys by simply pressing them, and the Multimedia keys by pressing `fn +` F-key (or the other way round). To switch the default mode of the F-keys to Function- or Multimedia-mode, press and hold `fn + X + L` for 4 seconds.

If everything works as expected, you can make the change permanent by creating the file `/etc/modprobe.d/hid_apple.conf` and adding the line:

`options hid_apple fnmode=2`

and running

`# as root update-initramfs -u -k all`

This works regardless if the keyboard is in Windows- or Mac-mode, and that might hint at the problem: in both cases the Linux thinks you’re connecting a Mac keyboard.