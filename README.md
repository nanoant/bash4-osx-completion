Bash 4 OSX commands completions
===============================

[bash4]: http://www.gnu.org/software/bash/
[debiancompletion]: http://bash-completion.alioth.debian.org

This completions are supposed to be used together with [Bash 4][bash4] and
[Debian's Bash Completions][debiancompletion]. Using it with shipped with OSX
old *Bash 3* will not work.

Installation
------------

#### 1. Install Bash 4

	cd /tmp
	git clone git://git.savannah.gnu.org/bash.git
	cd bash
	./configure
	make
	sudo make install

#### 2. Set Bash 4 as your default shell

Go to *System Preferences*, select *Users & Groups*. Unlock preferences with
clicking lock icon. Select your user and right click on it then select *Advanced
Options*.

Now you should be able to change `/bin/bash` into `/usr/local/bin/bash` which
will make *Bash 4* as your terminal shell. Select OK and close.

#### 3. Install Debian's Bash completion

	cd /tmp
	git clone git://git.debian.org/git/bash-completion/bash-completion.git
	./configure
	make
	sudo make install

#### 4. Enable Bash completion in your profile

Edit your `$HOME/.bash_profile` or create one if you do not have it already.
Then add following lines:

	if [ "${BASH_VERSINFO[0]}" -ge 4 ] && [ -f /usr/local/share/bash-completion/bash_completion ]; then
		. /usr/local/share/bash-completion/bash_completion
	fi

#### 5. Finally install OSX specific completions in your profile

	cd
	mkdir -p .local/share
	cd .local/share
	git clone git://github.com/nanoant/bash4-osx-completion.git bash-completion

License
-------

Copyright (c) 2015 Adam Strzelecki. All rights reserved.

This code is licensed under the MIT License:

> The MIT License
>
> License for the specific language governing rights and limitations under
> Permission is hereby granted, free of charge, to any person obtaining a
> copy of this software and associated documentation files (the "Software"),
> to deal in the Software without restriction, including without limitation
> the rights to use, copy, modify, merge, publish, distribute, sublicense,
> and/or sell copies of the Software, and to permit persons to whom the
> Software is furnished to do so, subject to the following conditions:
>
> The above copyright notice and this permission notice shall be included
> in all copies or substantial portions of the Software.
>
> THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS
> OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
> FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL
> THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
> LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
> FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER
> DEALINGS IN THE SOFTWARE.
