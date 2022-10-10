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



## Keychron Linux Function Keys

mshade | May 12, 2022, 3:59 a.m.

On Linux, the [Keychron K2](https://www.keychron.com/products/keychron-k2-wireless-mechanical-keyboard) doesn't register any of the F1-F12 function keys as actual F keys, instead, treating them as multimedia keys by default. Here's how to fix it!

They keyboard has 2 modes: Windows/Android and MacOS, but neither mode worked properly out of the box.

To fix this:

-   Set the keyboard to Windows mode via the side switch
-   Use `Fn + X + L` (hold for 4 seconds) to set the function key row to "Function" mode. (usually all that's necessary on Windows)
-   `echo 0 | sudo tee /sys/module/hid_apple/parameters/fnmode`

Once complete, my F1-F12 keys work properly, and holding `Fn` turns them into multimedia keys. You can use the `evtest` utility to check how keyboard keys are registering until you get the above combination of settings configured properly.

To persist this change, add a module option for `hid_apple`:

```
echo "options hid_apple fnmode=0" | sudo tee -a /etc/modprobe.d/hid_apple.conf
```

You may need to rebuild your `initramfs` if `hid_apple` is included. - ubuntu: `sudo update-initramfs -u` - arch: `mkinitcpio -P`

See also: - [/u/fratdaddyZC's comment on reddit for the `fnmode` tip](https://www.reddit.com/r/MechanicalKeyboards/comments/d5io49/keychron_k2_f_keys_dont_work_w_linux_help/f0m2u14/) - [Kurgol's keychron repo of tips](https://github.com/Kurgol/keychron/blob/master/k2.md) - [K2 manual](https://drive.google.com/file/d/1PsAKfM4lJVGuHL4oAFW7r10ACMfwFRpG/view)