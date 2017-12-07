# mandeler translating A CEO's Guide to Emacs
CEO 的 Emacs 指南
============================================================
几年，哦不对，是十几年前，Emacs 是我唯一的编辑器。写代码、写文档、管理邮件和日历，这些我全部在 Emacs 下面完成，而且用的很爽。时光飞逝，我渐渐转投到一些新的，更炫酷的工具。这导致我离开了鼠标就连一些基本的文本导航操作都忘了。大概三个多月前，我终于意识到，我在应用之间/电脑设备之间切换浪费了大量的时间，这时我决定再切换回 Emacs。这个决定真的很明智，其原因我接下来会一一列出。本文中，我还会谈到 `.emacs`  和 Dropbox 的一些技巧，这样读者可以更好地配置可以随心切换的使用环境。

对于还没使用过 Emacs 的人，可能比较厌恶 Emacs，但是我觉得，你们会爱上它的（如果尝试一下）。 Emacs 有点鲁布·戈德堡机械的味道，就好比你在一座房子里放了很多设备，相互关联工作，但是乍一看实现的只不过是烤面包片机的功能。但我可不是真的这个意思，注意我前面说的是“乍一看”。一旦你掌握了 Emacs 的使用技巧，你将意识到，我的天，这是一台热核能的烤面包机！它几乎可以作为任何文本处理的引擎。仔细想想，在你们使用电脑花费的时间中，有太多时间是和文本打交道。所以我这个说法虽然有点大胆了，但是，这却是事实。

也许对我而言，最重要的一点是， Emacs 是我使用过的应用中，最让我感觉我能掌控的。而不是让我感觉我是那种被坐落在 [Soma][30] 或者 Redmond 某个地方的豪华办公室里的产品营销部门洗脑的“钱多，人傻”的匿名用户。现代的生产力和创作应用（比如 Pages，IDE）就像碳纤维竞赛自行车，出厂时就组装得很好很完整。而 Emacs 就像一箱经典的 [Campagnolo][31] 零件加漂亮的刚质车架，但是没给配曲柄和刹车握把。缺的东西你要自己去网上淘。前者用起来体验很完整，也很快。而后者则是无穷的欢乐或烦恼--取决于你的性格，而且这种感受会一直伴着你。我属于那种找到收藏的 Campy 老配件和用 eLisp 调试 Emacs 时一样开心的那种人。YMMV （译者：YMMV不懂啥意思）

![1933 年的刚质自行车](https://blog.fugue.co/assets/images/bicycle.jpg)
我至今还骑着的 1933 年制刚质自行车。看看关于车架的对比视频
Youtube: [https://www.youtube.com/watch?v=khJQgRLKMU0][6].

Emacs 可能会给人映像有点落伍有点过时。但实际上并不是这样，Emacs 很强大，而且不会过时，但是它需要你花时间去了解它的用法。 Emacs 的用法和一般的使用习惯区别很大，看起来有点古怪，但是逻辑性很好，这使得你没法抗拒，为之着迷。我觉得， Emacs 代表着未来，而不是过去。就像刚质车架，经年累月，还是一样舒适好用。而神奇的碳纤维自行车到时候却支离破碎，只能填埋到垃圾场。 Emacs 也像这样，将会一直是个好用的工具，而最新的流行应用，将被人们遗忘脑后。

如果你觉得改 Lisp 代码，搭建个人工作环境，同时让这个量身打造的环境在任意电脑都能随手可用这个主意还不错，你很可能会喜欢上 Emacs 的。而如果你喜欢新的炫酷的应用，不想多花时间和精力调试，想要直接上手使用，那 Emacs 就不是你的菜了。我个人已经不写代码了（除了 Ludwig 和 Emacs Lisp），但是 Fugue 工作的很多工程师用 Emacs 用的挺好的。我必须得说，我们的工程师编辑器使用占比大概是 Emacs 30%， IDE 40%， Vim 30%。但是，咱这文章不是写给 CEO 和 [秀顶光的老板们][32] (PHB) 看的嘛（哦，对了，还有感兴趣的亲们），那我就专门写写为啥我爱用 Emacs 以及我是怎么使用它的。我也希望能给各位读者提供足够多的细节，让你们能够有个成功的体验，而不需要花上几个小时去谷歌。

### 长期的优势

使用 Emacs 的长期优势是让你活得轻松些，这一收获会让你前期的投入变得物有所值。想想下面这些：

### 不用再换来换去

单一个 Org 模式，就值得你花不少时间去研究了，但你要是和我一样，经常要处理成堆的文档--博客啊、会议备忘啊、员工评价啊这些。通常意味着要用好几种应用才能处理，这些应用的界面不一样，存储、筛选、搜索方式也不一样。导致的问题就是，你得频繁地切换思维环境，还要记住一些细枝末节的的东西。我很讨厌切换环境，因为这是由于用户界面 [2][8] 不一致，从而强加给我的问题，而且我很讨厌记住一些理论上本该电脑设备去记住的东西。在提供单一一致的环境方面， Emacs 对 PHB 们比对程序员们更有用，因为程序员通常一天下来只会用一种应用。切换思维环境导致的成本增加其实比我们显而易见的多得多。操作系统和应用提供商试图通过改变界面以使我们难以意识到这个事实。如果你是个技术，通过快捷键 (`M-:`) 来调出强大的 [语言解释器][33] 是非常有用的。[3][9]

许多应用可以整天全屏开着用来编辑文本。 Emac 是其中独一无二的，因为它即是文本编辑器，又是 Lisp 翻译器。当你处理文件的时候，基本上手边会有这么一台电脑。如果你稍微懂一点编程，你就会意识到这意味着你可以用 Emacs 做 _任何事情_ 。只要你记得命令是怎么用的，就能发挥电脑的全部性能。你不会想要在 eLisp 里面再去创建 Excel 表格，但是你在 Excel 中做的大部分工作都将通过一两行的代码轻松解决。当我需要处理数据的时候，我更喜欢跳转到缓存区写个几行命令，而不是新建一个 sheet 。甚至当我在写邮件的时候，哪怕不是一两行内容，我都会先在 Emacs 里面写好，然后粘贴到邮件客户端里面去。能接在一个环境处理的，为啥要切过来切过去呢？一开始的时候，可能只是简单地处理一些计算，时间长了，你需要处理的任何东西都可以轻松的交给 Emacs 去做。能提供丰富的功能给其他人创建文件，这在应用软件里面有可能是独一无二的。还记得 Issac Asimov 在书里面写到的神奇的终端吗？ Emacs 是我接触到的最接近那些终端的了。用了 Emacs ，我再也不纠结在什么情况下使用哪个应用程序了，只需要专注工作就行。工具顺手，效率也会高很多。

### 平心静气地写点东西

我用了 Emacs 之后，效果怎么样呢？仅仅是社区里面的人做了很多插件吗？又或者仅仅是因为一键之隔就能发挥 Lisp 的强大功能？实际上，除了编辑音频和图片，我所有的创造性工作都用 Emacs 做。
我桌子上放了双显示器，一块屏幕整天全屏开着 Emacs ，打开到portrait模式。另一块开着浏览器，用来搜索和阅读，通常也会开着一个终端。日历，邮箱这类应用，都在另一台桌子的苹果电脑上，当我用 Emacs 做事情的时候，所有那些应用都放到后台，提醒功能也都关掉了。这样子，我才能专注于手头的事情。因为我发现，现代界面的应用程序，设计初衷就是试着变得简单易用，导致的结果是你几乎没办法排除它们带来的干扰。我不需要人提醒那些我已經做了成千上万次的操作，我只需要一张干净清爽的白纸，让我能有思考的空间。有可能是上了年纪经历风霜之后，我已经适应不了嘈杂的环境了。但是我依然建议每个人都值得试一下我这种方式。体验一下在计算机处理环境中获得真正的安宁是什么感觉。诚然，好多应用程序有隐藏界面的模式，而且微软和苹果现在的全屏模式也不再那么鸡肋了。但是除了 Emacs 你还真找不到其他的应用，能让你沉浸式地处理大部分工作。除非你整天敲代码，或者在处理很长的文本，比如写书，不然你还是得面对其他应用程序带来的“噪音”。再一个，好多现代应用看上去牛逼哄哄，用起来糟糕透顶 [5][11] 。我唯一一个比办公软件还讨厌的，就属在线版本的办公软件了。

![我的电脑桌面](https://blog.fugue.co/assets/images/desktop.jpg)
我的电脑桌面，左侧是 Emacs

那么，通讯工具怎么办？创造和通讯的区别还是很大的。当把创作和通讯分开处理的时候，效率还是蛮高的。我们用的是 Fugue 上的 Slack，这玩意儿又好用又讨厌。我把和日历邮箱放在一个桌面，这样当我在处理工作的时候，看不到那些叨叨我乐得自在。因为哪怕一个消息弹窗、或者一封投资人或董事的邮件，就能打断我的工作。其实很多事情都能等个一两个小时再去处理。

### 随时随地，永久使用

Emacs 比其他环境优越的第三个原在于，你可以轻松地把手头工作带着。用不着各种各样的同步软件，你只要用 Dropbox 或者类似的工具同步一两个目录，就可以在任何你自己定制化的环境中继续工作了。我在 OS X，Windows，Linux 这几个平台中都做过这个事。真的超级简便，超级可靠！这个功能太好用了，所以我很讨厌用 Pages，GDocs，Office 这类软件或者其他类型的文件管理软件，因为那些软件还得让我到本地硬盘或者云端去找我的东西。

限制文件在电脑里面永久存储的因素是文件格式。假设人类现在已经解决了存储的问题 [6][12]，过一段时间我们面临的问题是，我还能访问我创建的文件吗？文本格式是计算处理领域历史最悠久的格式了。你可以用 Emacs 轻松地打开一份 1970 年的文本文件，但是用 Office 软件就不一定了。文本文件通常也很小，比 Office 文件小多了。作为一名数字收集者，脑袋里一旦有灵感就会记笔记，能够保证数据简单、轻量、永久存储、随时可用，这对我太重要了。

如果准备好试一下 Emacs 了，接着往下读！下面的章节虽然不能和完整的教程比，但是读完之后，你就能上手试一试了。

### 学会驾驭 Emacs - 技术配置

要想拥有这份强大的功能、内心的安宁，需要付出的代价就是 Emacs 的学习路线非常艰难，而且和你之前接触到的都不相同。一开始你会觉得这是把时间浪费在了过时的古怪的应用上，现代社会已经把它 pass 掉了。这个过程有点好比你只会开车，却要去学习骑自行车 [7][13]。

### 用哪个版本

我在 OS X 和 Windows 上面用的是 GNU vanilla Emacs 。 OS X 版本可以在 [][34][http://emacsformacosx.com/][35] 上面下载，Windows 版本可以在 [][36][http://www.gnu.org/software/emacs/][37] 上面下载。还有很多其他的版本，尤其是 Mac 上面，但是在这个版本上学习做些功能强悍的处理（包括了 Lisp 和 许多模型），学习曲线要比其他版本缓和的多。那么，下载下来，我们就可以开始啦！ [8][14]

### 第一步，文本导航

写这篇文档的时候，我使用 Emacs 的按键和按键组合用法。 'C' 指代 'contorl'，'M' 指代 'meta' （通常映射到了微软的 Alt 键或者苹果的 Option 键），连字符指代按键组合， `C-h t` 表示按住 control 键，然后按下 h 键，再松开 control 键，接着按下 t 键。这条命令用来引出下面的教程，接着往下读。

不要使用方向键和鼠标，它们可以用，但是你应该先花一周时间使用 Emacs 自带的导航命令。一旦形成肌肉记忆，你将喜欢用导航命令，到哪也离不开了。 Emacs 使用说明在这块写的已经很好了，我这里做些归纳，这样你就不用再去读整篇的教程了。无聊的地方在于，不再是用方向键来表示上下左右，而是分别用 `C-b` 表示后退， `C-f` 表示前进， `C-p` 表示上一个 ( up )， `C-n` 表示下一个 ( down )。你可能会想“我为什么要这么麻烦呢？用方向键不是很好吗？”这是有原因的。首先，使用快捷键，在打字的时候，手不需要离开输入位置。其次，前进后退键和 Alt 同时按下时，可以以单词为单位进行跳格(Emacspeak 里面 Alt 对应的是 Meta )。实际上，这四个导航键用起来会更顺手。第三个好处是，如果你需要重复某个命令，可以在前面加上数量。这个功能我经常使用，编辑文档的时候，估计一下需要跳几行或者跳几个单词，比如 `C-9 C-p` 可以上跳9行，`M-5 M-b`可以向前跳5个单词。其他一些重要的导航命令都是以 `a` 开头，以 `e` 结尾的。 `C-a|e` 用在行间，`M-a|e` 用在句中。为了保证句命令正常执行，句号后面需要加双空格，这样即提供了有用的特性，又可以消除一些 [思维上的误差][38] 。如果想要把文档导出到某个 [单空格的发布环境][39] ，写个宏简单运行一下就好了。 Emacs 自带的说明真的值得过一遍。有些读者没耐心看官方自带的手册，我这里覆盖几个重要的命令，但是官方说明真的很不错。
It genuinely is worth going through the tutorial that ships with Emacs. I'll cover a few important commands for the truly impatient, but the tutorial is gold. Reminder: `C-h t` for the tutorial.

### Learn To Copy and Paste

You can put Emacs into `CUA` mode, which will work in familiar ways, but the native Emacs way is pretty great and plenty easy once you learn it. You mark regions (like selecting) by using Shift with the navigation commands. So `C-F` selects one character forward from the cursor, etc. You copy with `M-w`, you cut with `C-w`, and you paste with `C-y`. These are actually called killing and yanking, but it's very similar to cut and paste. There is magic under the hood here in the kill ring, but for now, just worry about cut, copy, and paste. If you start fumbling around at this point, `C-x u` is undo...

### Next, Learn Ido Mode

Trust me. Ido makes working with files much easier. You don't generally use a separate Finder|Explorer window to work with files in Emacs. Instead you use the editor's commands to create, open, and save files. This is a bit of a pain without Ido, so I recommend installing it before learning the other way. Ido comes with Emacs beginning with version 22, but you'll want to make some tweaks to your `.emacs` file so that it is always used. This is a good excuse to get your environment set up.

Most features in Emacs come in modes. To install any given mode, you'll need to do two things. Well, at first you'll need to do a few extra things, but these only need to be done once, and thereafter only two things. So the extra things are that you'll need a single place to put all your eLisp files and you'll need to tell Emacs where that place is. I suggest you make a single directory in, say, Dropbox that is your Emacs home. Inside this, you'll want to create an `.emacs` file and an `.emacs.d` directory. Inside the `.emacs.d`, make a directory called `lisp`. So you should have:

```
home
|
+.emacs
|
-.emacs.d
  |
  -lisp
```

You'll put the `.el` files for things like modes into the `home/.emacs.d/lisp`directory, and you'll point to that in your `.emacs` like so:

`(add-to-list 'load-path "~/.emacs.d/lisp/")`

Ido Mode comes with Emacs, so you won't need to put an `.el` file into your Lisp directory for this, but you'll be adding other stuff soon that will go in there.

### Symlinks are Your Friend

But wait, that says that `.emacs` and `.emacs.d` are in your home directory, and we put them in some dumb folder in Dropbox! Correct. This is how you make it easy to have your environment anywhere you go. Keep everything in Dropbox and make symbolic links to `.emacs`, `.emacs.d`, and your main document directories in `~`. On OS X, this is super easy with the `ln -s` command, but on Windows this is a pain. Fortunately, Emacs provides an easy alternative to symlinking on Windows, the HOME environment variable. Go into Environment Variables in Windows (as of Windows 10, you can just hit the Windows key and type "Environment Variables" to find this with search, which is the best part of Windows 10), and make a HOME environment variable in your account that points to the Dropbox folder you made for Emacs. If you want to make it easy to navigate to local files that aren't in Dropbox, you may instead want to make a symbolic link to the Dropbox Emacs home in your actual home directory.

So now you've done all the jiggery-pokery needed to get any machine pointed to your Emacs setup and files. If you get a new computer or use someone else's for an hour or a day, you get your entire work environment. This seems a little difficult the first time you do it, but it's about a ten minute (at most) operation once you know what you're doing.

But we were configuring Ido...

`C-x` `C-f` and type `~/.emacs RET RET` to create your `.emacs` file. Add these lines to it:

```
;; set up ido mode
(require `ido)
(setq ido-enable-flex-matching t)
(setq ido-everywhere t)
(ido-mode 1)
```

With the `.emacs` buffer open, do an `M-x evaluate-buffer` command, and you'll either get an error if you munged something or you'll get Ido. Ido changes how the minibuffer works when doing file operations. There is great documentation on it, but I'll point out a few tips. Use the `~/` effectively; you can just type `~/` at any point in the minibuffer and it'll jump back to home. Implicit in this is that you should have most of your stuff a short hop off your home. I use `~/org` for all my non-code stuff and `~/code` for code. Once you’re in the right directory, you'll often have a collection of files with different extensions, especially if you use Org Mode and publish from it. You can type period and the extension you want no matter where you are in the file name and Ido will limit the choices to files with that extension. For example, I'm writing this blog post in Org Mode, so the main file is:

`~/org/blog/emacs.org`

I also occasionally push it out to HTML using Org Mode publishing, so I've got an `emacs.html` file in the same directory. When I want to open the Org file, I will type:

`C-x C-f ~/o[RET]/bl[RET].or[RET]`

The [RET]s are me hitting return for auto completion for Ido Mode. So, that’s 12 characters typed and, if you're used to it, a  _lot_  less time than opening Finder|Explorer and clicking around. Ido Mode is plenty useful, but really is a utility mode for operating Emacs. Let's explore some modes that are useful for getting work done.

### Fonts and Styles

I recommend getting the excellent input family of typefaces for use in Emacs. They are customizable with different braces, zeroes, and other characters. You can build in extra line spacing into the font files themselves. I recommend a 1.5X line spacing and using their excellent proportional fonts for code and data. I use Input Serif for my writing, which has a funky but modern feel. You can find them on [http://input.fontbureau.com/][40] where you can customize to your preferences. You can manually set the fonts using menus in Emacs, but this puts code into your `.emacs`file and, if you use multiple devices, you may find you want some different settings. I've set up my `.emacs` to look for the machine I'm using by name and configure the screen appropriately. The code for this is:

```
;; set up fonts for different OSes. OSX toggles to full screen.
(setq myfont "InputSerif")
(cond
((string-equal system-name "Sampo.local")
 (set-face-attribute 'default nil :font myfont :height 144)
 (toggle-frame-fullscreen))
((string-equal system-name "Morpheus.local")
 (set-face-attribute 'default nil :font myfont :height 144))
((string-equal system-name "ILMARINEN")
 (set-face-attribute 'default nil :font myfont :height 106))
((string-equal system-name "UKKO")
 (set-face-attribute 'default nil :font myfont :height 104)))
```

You should replace the `system-name` values with what you get when you evaluate `(system-name)` in your copy of Emacs. Note that on Sampo (my MacBook), I also set Emacs to full screen. I'd like to do this on Windows as well, but Windows and Emacs don't really love each other and it always ends up in some wonky state when I try this. Instead, I just fullscreen it manually after launch.

I also recommend getting rid of the awful toolbar that Emacs got sometime in the 90s when the cool thing to do was to have toolbars in your application. I also got rid of some other "chrome" so that I have a simple, productive interface. Add these to your `.emacs` file to get rid of the toolbar and scroll bars, but to keep your menu available (on OS X, it'll be hidden unless you mouse to the top of the screen anyway):

```
(if (fboundp 'scroll-bar-mode) (scroll-bar-mode -1))
(if (fboundp 'tool-bar-mode) (tool-bar-mode -1))
(if (fboundp 'menu-bar-mode) (menu-bar-mode 1))
```

### Org Mode

I pretty much live in Org Mode. It is my go-to environment for authoring documents, keeping notes, making to-do lists and 90% of everything else I do. Org was originally conceived as a combination note-taking and to-do list utility by a fellow who is a laptop-in-meetings sort. I am against use of laptops in meetings and don't do it myself, so my use cases are a little different than his. For me, Org is primarily a way to handle all manner of content within a structure. There are heads and subheads, etc., in Org Mode, and they function like an outline. Org allows you to expand or hide the contents of the tree and also to rearrange the tree. This fits how I think very nicely and I find it to be just a pleasure to use in this way.

Org Mode also has a lot of little things that make life pleasant. For example, the footnote handling is excellent and the LaTeX/PDF output is great. Org has the ability to generate agendas based on the to-do's in all your documents and a nice way to relate them to dates/times. I don't use this for any sort of external commitments, which are handled on a shared calendar, but for creating things and keeping track of what I need to create in the future, it's invaluable. Installing it is as easy as adding the `org-mode.el` to your Lisp directory and adding these lines to your `.emacs`, if you want it to indent based on tree location and to open documents fully expanded:

```
;; set up org mode
(setq org-startup-indented t)
(setq org-startup-folded "showall")
(setq org-directory "~/org")
```

The last line is there so that Org knows where to look for files to include in agendas and some other things. I keep Org right in my home directory, i.e., a symlink to the directory that lives in Dropbox, as described earlier.

I have a `stuff.org` file that is always open in a buffer. I use it like a notepad. Org makes it easy to extract things like TODOs and stuff with deadlines. It's especially useful when you can inline Lisp code and evaluate it whenever you need. Having code with content is super handy. Again, you have access to the actual computer with Emacs, and this is a liberation.

#### Publishing with Org Mode

I care about the appearance and formatting of my documents. I started my career as a designer, and I think information can and should be presented clearly and beautifully. Org has great support for generating PDFs via LaTeX, which has a bit of its own learning curve, but doing simple things is pretty easy.

If you want to use fonts and styles other than the typical LaTeX ones, you've got a few things to do. First, you'll want XeLaTeX so you can use normal system fonts rather than LaTeX specific fonts. Next, you'll want to add this to `.emacs`:

```
(setq org-latex-pdf-process
 '("xelatex -interaction nonstopmode %f"
  "xelatex -interaction nonstopmode %f"))
```

I put this right at the end of my Org section of `.emacs` to keep things tidy. This will allow you to use more formatting options when publishing from Org. For example, I often use:

```
#+LaTeX_HEADER: \usepackage{fontspec}
#+LATEX_HEADER: \setmonofont[Scale=0.9]{Input Mono}
#+LATEX_HEADER: \setromanfont{Maison Neue}
#+LATEX_HEADER: \linespread{1.5}
#+LATEX_HEADER: \usepackage[margin=1.25in]{geometry}

#+TITLE: Document Title Here
```

These simply go somewhere in your `.org` file. Our corporate font for body copy is Maison Neue, but you can put whatever is appropriate here. I strongly discourage the use of Maison Neue. It’s a terrible font and no one should ever use it.

This file is an example of PDF output using these settings. This is what out-of-the-box LaTeX always looks like. It's fine I suppose, but the fonts are boring and a little odd. Also, if you use the standard format, people will assume they are reading something that is or pretends to be an academic paper. You've been warned.

### Ace Jump Mode

This is more of a gem than a major feature, but you want it. It works a bit like Jef Raskin's Leap feature from days gone by.[9][15] The way it works is you type `C-c` `C-SPC`and then type the first letter of the word you want to jump to. It highlights all occurrences of words with that initial character, replacing it with a letter of the alphabet. You simply type the letter of the alphabet for the location you want and your cursor jumps to it. I find myself using this as often as the more typical nav keys or search. Download the `.el` to your Lisp directory and put this in your `.emacs`:

```
;; set up ace-jump-mode
(add-to-list 'load-path "which-folder-ace-jump-mode-file-in/")
(require 'ace-jump-mode)
(define-key global-map (kbd "C-c C-SPC" ) 'ace-jump-mode)
```

### More Later

That's enough for one post—this may get you somewhere you'd like to be. I'd love to hear about your uses for Emacs aside from programming (or for programming!) and whether this was useful at all. There are likely some boneheaded PHBisms in how I use Emacs, and if you want to point them out, I'd appreciate it. I'll probably write some updates over time to introduce additional features or modes. I'll certainly show you how to use Fugue with Emacs and Ludwig-mode as we evolve it into something more useful than code highlighting. Send your thoughts to [@fugueHQ][41] on Twitter.

* * *

#### Footnotes

1.  [^][16] If you are now a PHB of some sort, but were never technical, Emacs likely isn’t for you. There may be a handful of folks for whom Emacs will form a path into the more technical aspects of computing, but this is probably a small population. It’s helpful to know how to use a Unix or Windows terminal, to have edited a dotfile or two, and to have written some code at some point in your life for Emacs to make much sense.

2.  [^][17] [][18][http://archive.wired.com/wired/archive/2.08/tufte.html][19]

3.  [^][20] I mainly use this to perform calculations while writing. For example, I was writing an offer letter to a new employee and wanted to calculate how many options to include in the offer. Since I have a variable defined in my `.emacs` for outstanding-shares, I can simply type `M-: (* .001 outstanding-shares)`and get a tenth of a point without opening a calculator or spreadsheet. I keep  _lots_ of numbers in variables like this so I can avoid context switching.

4.  [^][21] The missing piece of this is the web. There is an Emacs web browser called eww that will allow you to browse in Emacs. I actually use this, as it is both a great ad-blocker and removes most of the poor choices in readability from the web designer's hands. It's a bit like Reading Mode in Safari. Unfortunately, most websites have lots of annoying cruft and navigation that translates poorly into text.

5.  [^][22] Usability is often confused with learnability. Learnability is how difficult it is to learn a tool. Usability is how useful the tool is. Often, these are at odds, such as with the mouse and menus. Menus are highly learnable, but have poor usability, so there have been keyboard shortcuts from the earliest days. Raskin was right on many points where he was ignored about GUIs in general. Now, OSes are putting things like decent search onto a keyboard shortcut. On OS X and Windows, my default method of navigation is search. Ubuntu's search is badly broken, as is the rest of its GUI.

6.  [^][23] AWS S3 has effectively solved file storage for as long as we have the Internet. Trillions of objects are stored in S3 and they've never lost one of them. Most every service out there that offers cloud storage is built on S3 or imitates it. No one has the scale of S3, so I keep important stuff there, via Dropbox.

7.  [^][24] By now, you might be thinking "what is it with this guy and bicycles?" ... I love them on every level. They are the most mechanically efficient form of transportation ever invented. They can be objects of real beauty. And, with some care, they can last a lifetime. I had Rivendell Bicycle Works build a frame for me back in 2001 and it still makes me happy every time I look at it. Bicycles and UNIX are the two best inventions I've interacted with. Well, they and Emacs.

8.  [^][25] This is not a tutorial for Emacs. It comes with one and it's excellent. I do walk through some of the things that I find most important to getting a useful Emacs setup, but this is not a replacement in any way.

9.  [^][26] Jef Raskin designed the Canon Cat computer in the 1980s after falling out with Steve Jobs on the Macintosh project, which he originally led. The Cat had a document-centric interface (as all computers should) and used the keyboard in innovative ways that you can now imitate with Emacs. If I could have a modern, powerful Cat with a giant high-res screen and Unix underneath, I'd trade my Mac for it right away. [][27][https://youtu.be/o_TlE_U_X3c?t=19s][28]

--------------------------------------------------------------------------------

via: https://blog.fugue.co/2015-11-11-guide-to-emacs.html

作者：[Josh Stella ][a]
译者：[译者ID](https://github.com/译者ID)
校对：[校对者ID](https://github.com/校对者ID)

本文由 [LCTT](https://github.com/LCTT/TranslateProject) 原创编译，[Linux中国](https://linux.cn/) 荣誉推出

[a]:https://blog.fugue.co/authors/josh.html
[1]:https://blog.fugue.co/2013-10-16-vpc-on-aws-part3.html
[2]:https://blog.fugue.co/2013-10-02-vpc-on-aws-part2.html
[3]:http://ww2.fugue.co/2017-05-25_OS_AR_GartnerCoolVendor2017_01-LP-Registration.html
[4]:https://blog.fugue.co/authors/josh.html
[5]:https://twitter.com/joshstella
[6]:https://www.youtube.com/watch?v=khJQgRLKMU0
[7]:https://blog.fugue.co/2015-11-11-guide-to-emacs.html?utm_source=wanqu.co&utm_campaign=Wanqu+Daily&utm_medium=website#phb
[8]:https://blog.fugue.co/2015-11-11-guide-to-emacs.html?utm_source=wanqu.co&utm_campaign=Wanqu+Daily&utm_medium=website#tufte
[9]:https://blog.fugue.co/2015-11-11-guide-to-emacs.html?utm_source=wanqu.co&utm_campaign=Wanqu+Daily&utm_medium=website#interpreter
[10]:https://blog.fugue.co/2015-11-11-guide-to-emacs.html?utm_source=wanqu.co&utm_campaign=Wanqu+Daily&utm_medium=website#eww
[11]:https://blog.fugue.co/2015-11-11-guide-to-emacs.html?utm_source=wanqu.co&utm_campaign=Wanqu+Daily&utm_medium=website#usability
[12]:https://blog.fugue.co/2015-11-11-guide-to-emacs.html?utm_source=wanqu.co&utm_campaign=Wanqu+Daily&utm_medium=website#s3
[13]:https://blog.fugue.co/2015-11-11-guide-to-emacs.html?utm_source=wanqu.co&utm_campaign=Wanqu+Daily&utm_medium=website#bicycles
[14]:https://blog.fugue.co/2015-11-11-guide-to-emacs.html?utm_source=wanqu.co&utm_campaign=Wanqu+Daily&utm_medium=website#nottutorial
[15]:https://blog.fugue.co/2015-11-11-guide-to-emacs.html?utm_source=wanqu.co&utm_campaign=Wanqu+Daily&utm_medium=website#canoncat
[16]:https://blog.fugue.co/2015-11-11-guide-to-emacs.html?utm_source=wanqu.co&utm_campaign=Wanqu+Daily&utm_medium=website#phbOrigin
[17]:https://blog.fugue.co/2015-11-11-guide-to-emacs.html?utm_source=wanqu.co&utm_campaign=Wanqu+Daily&utm_medium=website#tufteOrigin
[18]:http://archive.wired.com/wired/archive/2.08/tufte.html
[19]:http://archive.wired.com/wired/archive/2.08/tufte.html
[20]:https://blog.fugue.co/2015-11-11-guide-to-emacs.html?utm_source=wanqu.co&utm_campaign=Wanqu+Daily&utm_medium=website#interpreterOrigin
[21]:https://blog.fugue.co/2015-11-11-guide-to-emacs.html?utm_source=wanqu.co&utm_campaign=Wanqu+Daily&utm_medium=website#ewwOrigin
[22]:https://blog.fugue.co/2015-11-11-guide-to-emacs.html?utm_source=wanqu.co&utm_campaign=Wanqu+Daily&utm_medium=website#usabilityOrigin
[23]:https://blog.fugue.co/2015-11-11-guide-to-emacs.html?utm_source=wanqu.co&utm_campaign=Wanqu+Daily&utm_medium=website#s3Origin
[24]:https://blog.fugue.co/2015-11-11-guide-to-emacs.html?utm_source=wanqu.co&utm_campaign=Wanqu+Daily&utm_medium=website#bicyclesOrigin
[25]:https://blog.fugue.co/2015-11-11-guide-to-emacs.html?utm_source=wanqu.co&utm_campaign=Wanqu+Daily&utm_medium=website#nottutorialOrigin
[26]:https://blog.fugue.co/2015-11-11-guide-to-emacs.html?utm_source=wanqu.co&utm_campaign=Wanqu+Daily&utm_medium=website#canoncatOrigin
[27]:https://youtu.be/o_TlE_U_X3c?t=19s
[28]:https://youtu.be/o_TlE_U_X3c?t=19s
[29]:https://blog.fugue.co/authors/josh.html
[30]:http://www.huffingtonpost.com/zachary-ehren/soma-isnt-a-drug-san-fran_b_987841.html
[31]:http://www.campagnolo.com/US/en
[32]:http://www.businessinsider.com/best-pointy-haired-boss-moments-from-dilbert-2013-10
[33]:http://www.webopedia.com/TERM/I/interpreter.html
[34]:http://emacsformacosx.com/
[35]:http://emacsformacosx.com/
[36]:http://www.gnu.org/software/emacs/
[37]:http://www.gnu.org/software/emacs/
[38]:http://www.huffingtonpost.com/2015/05/29/two-spaces-after-period-debate_n_7455660.html
[39]:http://practicaltypography.com/one-space-between-sentences.html
[40]:http://input.fontbureau.com/
[41]:https://twitter.com/fugueHQ
