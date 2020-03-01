# Sublime

Edit the text in multi point, we can use the **Command Key** to select the word needs to be modified

**Command + p** : switch to the file quickly

**Shift + Command + p** : show the operation list, which also shows the shortcut keys of the operation

**Command + ,** : show the preferences of sublime

Open the **vim pattern** : open the preferences, comment the following part:

```
"ignored_packages": [
		//"Vintage"
]
```

Make a soft link of sublime :

```shell
sudo /bin/ln -s /Applications/Sublime\ Text.app/Contents/SharedSupport/bin/subl /usr/local/bin/
```

Sublime's config location:

```shell
~/Library/Application Support/Sublime Text 3/Packages/User
```

We can remove the User dir, and pull the config from GitHub to control our config :

```shell
rm -rf ~/Library/Application Support/Sublime Text 3/Packages/User
cd ~/Library/Application Support/Sublime Text 3/Packages
git clone git@github.com:happypeter/sublime-config.git
mv sublime-config User
```

**Command + K,B** : show the side bar of the file.

**Command +/-** : Resize the font

**Shift + Command + p ==then== input key bindings** : we can see all the keymap of sublime

**Command + n** : open a new tag

**Control + tab** :  switch to next tag

**Command + j** : join lines to one line

**Command + ]** : tab forward

**Command + [** : tab backward

**Command + l** : select the line

**Command + x** : delete the current line

**Command + enter** : open a new line below

**Command + shift + enter** : open a new line last row

**option + mouse select** : select the block and edit

**Command + shift + p** : select java, we can use the java syntax highlighting

Package Config:

```shell
/Users/mac/Library/Application Support/Sublime Text 3/Packages/User/Preferences.sublime-settings
```

Keymap Config:

```shell
/Users/mac/Library/Application Support/Sublime Text 3/Packages/User/Default(OSX).sublime-keymap
```

Install the advanced new file plugin:

**Shift + Command + p**, then input the advanced new file, install the plugin

We can create a new file in sublime terminal use following keymap : **Option + Command + n**

Git is also supported in sublime, so open the install package Shift + Command + p, input : install package.

Search git plugin, after installation, Shift + Command + p , we can use git add, git commit, git push etc.

Firstly, git add

Then, git commit, add the comments, then **Command + w** to commit

Last, git push to the remote repo

Install SyncedSideBar plugin, the side bar cursor will move to the current file's position.

Install Terminal to open terminal at current file's path, use **Command + Shift + t** to use it.



Search File's content:

**Command + p** : number : move to the file's specific number line

**Command + p @function name** : move to the function or tag of the file

**Command + p # string** : search the string from the file

**Command + option + f** : search and replace

**Command + d** : select word one by one and enter the multi part edit mode

**Find in folder** : Find all the matched content in the folder, can use F4 to enter the file

**Control + -** ： Return the former operation's position

**Control + Shift + -** : Return the next operation's position

**Control + `** : enter the python terminal 



Self define the build system : 

Run java app in sublime:

```json
{
    "encoding": "utf-8",
    "file_regex": "^ *\\[javac\\] (.+):([0-9]+):() (.*)$",
    "selector": "source.java",
    "shell_cmd": "javac -encoding utf-8 $file_name && java $file_base_name"
}
```

If note the selector, the build system will choose how to build the file[ when tap the Command + b ].

For html file, the selector should be defined as **text.html**, when build the html file, will open the chrome:

```json
{
	"cmd": ["/Applications/Google Chrome.app/Contents/MacOS/Google Chrome","$file"],
    "selector":"text.html"
}
```

