

# Microdot Linux

The Microdot Linux project will guide you through the process of
creating a miniature but fully functional Linux system from the
ground up, with special emphasis on toolchain creation and kernel
configuration. The root file system (kernel + busybox + musl-libc) takes
up only 1.5MB of space inside a compressed tarball, and it is bootable
using Quick Emulator. You can tune the kernel to support more hardware
and extend the functionality of the base system.

More software can be added to Microdot by compiling them from source. An
experimental package manager named `Tiny Package Manager` is currently being
developed. For more information, visit the 
[tpkg](https://github.com/unturned3/tpkg)
github repo.


# Tutorial Overview

- Section 1: prerequisites, background information, and build environment setup
- Section 2: constructs a musl-based cross compilation toolchain
- Section 3: builds a minimum Linux system composed of a tiny kernel and an
	initramfs archive.
- Section 4: tutorials for more specific topics, such as kernel fine tuning,
	porting Microdot to other architectures, installing other programs, etc.
	This section will probably contain a lot of work contributed by other users.
	For more details, see the `readme.md` file inside `wiki/4_beyond`.


# Getting Started

The Microdot [wiki](/wiki) is where all the tutorials and documentation are
stored. Check out the Wiki to start building your own Microdot Linux!
You can also visit the FAQ section to learn more about the Microdot project.


# FAQ


### Why did you build the Microdot project?

I started building Microdot purely out of curiosity (and building a Linux
system from scratch does seem like a popular pastime for people). However, 
along the way, I encountered many problems, such as:

* How do I properly make a cross compilation toolchain?
* How can I replace glibc with the smaller musl-libc?
* How do I properly configure the Linux kernel and make it tiny?
* How can I make the a Linux system as small as possible?

There is suprisingly little documentation or tutorials on the internet
about these topics. For any information that I did manage to find, they
hardly agreed with each other and were either incorrect or inconsistent.
And some of them just expect you to blindly follow insturctions
and type commands without explaining why.

"cross toolchain building" and "kernel configuration" were the nastiest
out of all the problems I faced. There are literally thousands of
switches and options that you can use to configure the packages, and
misusing one could cause the toolchain to fail or render the kernel
unbootable. I partially used trail-and-error to figure things out (believe
me, applying trail-and-error that on a process that takes hours to finish
every time is not a fun task to do), but luckily I got some help from
[other people](/thanks.md), which spared me from wasting more time.

I learned a lot in the end, and I thought it would be good for me to
share my experience, so other people wouldn't have to go through the same
process and waste an awful lot of time.

### What's the difference between the Microdot and other projects?

Here are some projects that has some similar aspects to Microdot:

* Tiny Core Linux

	Does an exellent job making a complete & tiny Linux distro,
	but isn't primarily focused on teaching people _how_ to make one.

* Linux From Scratch

	Teaches people how to manually assemble a working Linux system, but
	uses _a lot_ of packages, employs a complicated process, and makes a
	big system(200+ MB). Doesn't offer any details about how to configure
	a kernel. 

* Minimal Linux Live

	Has a concise and fully automated build process, explains a lot
	about the boot process and system internals, and the resulting system
	is quite small (around 8MB). However, it doesn't use a customized
	toolchain (makes the end system unnecessarily big), and it doesn't
	explain how to configure a kernel. This makes it somewhat difficult for
	the system to be extended and molded for other purposes.

### What's wrong with articles/tutorials on the internet?

Most of them are outdated, inconsistent, and perplexing. Having that said,
there are still some good ones out there, and I will put links to these
in the documentation whenever appropriate.

### What does "Microdot" mean?

Microdots are a steganographic technique that involves
photographically shrinking a large chunk of text to the
size of a typographical dot, such as a period. This term
is used here to figuratively show the fact that Microdot
Linux compresses a lot of functionality into a tiny
amount of space.


### Who is the intended audience of the Microdot Project?

The Microdot Project is primarily intended for people who
is interested in constructing a custom Linux system (it seems
like that this is quite a popular activity for Linux users).
However, besides that, the Microdot Project also provides
useful information on cross compilation, which could be useful
outside the scope of Linux system building.


### What can Microdot Linux be used for?

Microdot Linux is made to be modular and extendable,
meaning that you can tailor it to your needs. Because 
it comes with no bloat and has a small size, it can
also be used as an embedded Linux system, where resources
are constrained. For example, you can replace Rasbian with
Microdot on a Raspberry Pi in order to save more memory
and processing power for your applications. 



