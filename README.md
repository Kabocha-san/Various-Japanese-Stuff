# Various-Japanese-Stuff
Stuff concerning Japanese and learning Japanese

First: This is not a how on how to learn Japanese, there are already many others out there that have done an excellect job with this.
There also would definitely never be that much information here as I myself have already achieved reading fluency and simply no longer am confronted with problems one might often have in the beginning.

This is mostly a place where I collect information myself as I come across it, such as old instructions to make things work that are broken or unaddressed issues I come accross myself.

I will not provide step by step instructions for most things and only the relevant parts, if you have no idea how to do something try using use a search engine!

I will also place here scripts (concerning Japanese or Japanese learning) I write myself should I have to in the future.

As always I collect these solutions by my own volition and my own time for my own use cases and cannot gurantee that they will work for your use cases and am not liable if something goes wrong.
Reading instructions clearly and use a search engine if something remains unclear and make sure you understand what you are doing!
I am putting this together for future me and anyone else, who might find this useful.

# Studying

Again this is not general advice on how to learn the language, these are things that I have come accross myself I happen to find useful.
If general advice on advice on how to learn Japanese is something you need, you will likely not find it here but this post from [r/LearnJapanese](https://www.reddit.com/r/LearnJapanese/wiki/index/startersguide/) is often good point to start.

## Fast word look ups for non PC-games or printed media (and fast anki card creation)
I still own a lot of printed manga or books (or VNs I have as switch games), this is what I do to make look ups easier here.
Using Google lense to get the actucal text is a no-brainer, but unfortunately because of a disability I have very high repetive strain injury risks, so I need things to be as effortless and fast as possible and except for the fact I am often busy with other things and code, I still read a lot and the pain thus normally adds up quickly when looking up words. 

And using my laptop for this cases has brought me personally much relief in that regard.
Using the Dolphin android browser (because it supports chrome add-ons) instead because of lack of functioning clipboard monitor is already too much and does not work for me.

The best solution I have for this is to use [KDE connect](https://kdeconnect.kde.org/) to automatically get the phone's clipboard and send in to the PC, where yomichan will detect the clipboard change and open the pop-up as usually. You will need to have your PC on (obviously) and on on the same wifi network as your phone and connection between devices on the network has to be allowed.

From Android 10+ root is required for this to work and something like this riru/xposed module: [Riru-ClipboardWhitelist](https://github.com/Kr328/Riru-ClipboardWhitelist) 

Though from my own experience this breaks again for many android 13 ROMs (even with root).

# Encoding woes

I am sure most non English speakers with a language that uses some or some many "fancy characters" know how much problems one can get with text encodings.
I am not an English speaker myself, but still prefer US English on all my devices for OS and and software for the most part for troubleshooting reasons.

For most operating systems the first step to solve any of the following problems is to install Japanese support on OS level, should one not have done so yet.

## Mojibake

As in the encoding is either not recognized automatically (text editor or browsers, try changing it to Unicode then Shift JIS).

For non-unicode encodings this becomes much more cumbersome.

### Windows
Turn on support for Non-Unicode software and or switch it to Japanese otherwise use locale emulator.

### Wine, Proton, Lutris
First install fake Japanese (maybe also corefonts when you already busy installing fonts in your prefix) via winetricks or protontricks.
Please not that if you have not installed fake Japanese and or do not start the installation without setting the environmental variable as bellow the installer will often produce broken installations (like mojibake folder and filenames) or fail to complete altogether. In that case delete your prefix and start again.

Start software like so via the terminal: 
```
LANG=ja_JP.UTF-8 wine example.exe
```
Note that even though Lutris does support setting environmental variables per prefix this often still does not work in my personal experience and you may have to start Lutris via terminal after setting it yourself (obviously in the same terminal window).

## Make Japanese character variants appear instead of Chinese variants
And for Japanese, especially when not setting the whole system of a device to Japanese this very often results in characters getting displayed wrong meaning simplified Chinese characters have the same unicode mapping as Japanese characters and if not the whole system is set to Japanese one has to content often with seeing simplified Chinese characters instead. 

On Windows this mostly works correctly, but even then some software still doesn't do this correctly sometimes. 
For software where one can specify the font to display stuff that does this using Japanese only fonts like [Google's Noto Sans Japanese](https://fonts.google.com/noto/specimen/Noto+Sans+JP) (explicitly not one of the CJK fonts as they have Chinese and Korean variants and it will again not work) or the Takao fonts.

If one can tell the software what language is use (as in Anki note templates) one should do that instead, otherwise I will write up what solutions I happen to come across when encountering problems.

For example as I was going through Japanese books about Blender (on Ubuntu) I set the UI interface to Japanese, but the characters where displayed wrong so I went to 編集>プリファレンス>テキストレンダリング to instead use Noto Sans Japanese fonts. (If you happen to need this specific instructions: Do not forget to save your configuration changes you have to click the Hamburger menu in the left corner.)
