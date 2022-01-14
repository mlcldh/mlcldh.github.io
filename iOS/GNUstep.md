## GNUstep

简单来说，GNUstep 是实现 OpenStep 接口的开放软件 (Open Source) 计划，目标为提供跨平台的面向对象程序开发环境。

C 语音有Dennis Ritchie于20世纪70年代早期首创，20世纪70年代晚期才获得广泛支持并流行开来。UNIX 操作系统的普及也促进C 语音的普及，UNIX 完全有C 语音编写。

Objective-C 主要由 [Stepstone](https://zh.wikipedia.org/w/index.php?title=Stepstone&action=edit&redlink=1) 公司的[布莱德·考克斯](https://zh.wikipedia.org/wiki/布萊德·考克斯)（Brad Cox）和 [汤姆·洛夫](https://zh.wikipedia.org/w/index.php?title=汤姆·洛夫&action=edit&redlink=1)（Tom Love） 在 1980 年代发明。

1981年 Brad Cox 和 Tom Love 还在 [ITT 公司](https://zh.wikipedia.org/wiki/ITT公司)技术中心任职时，接触到了 [SmallTalk语言](https://zh.wikipedia.org/wiki/Smalltalk)。Cox 当时对软件设计和开发问题非常感兴趣，他很快地意识到 [SmallTalk语言](https://zh.wikipedia.org/wiki/Smalltalk) 在系统工程构建中具有无法估量的价值，但同时他和 Tom Love 也明白，目前 [ITT 公司](https://zh.wikipedia.org/wiki/ITT公司)的电子通信工程相关技术中，C 语言被放在很重要的位置。

于是 Cox 撰写了一个 C 语言的预处理器，打算使 C 语言具备些许 Smalltalk 的本领。Cox 很快地实现了一个可用的 C 语言扩展，此即为 Objective-C语言的前身。到了 1983 年，Cox 与 Love 合伙成立了 Productivity Products International（PPI）公司，将 Objective-C 及其相关库商品化贩售，并在之后将公司改名为StepStone。1986年，Cox 出版了一本关于 Objective-C 的重要著作《Object-Oriented Programming, An Evolutionary Approach》，书内详述了 Objective-C 的种种设计理念。

在1985 年，Steve Jobs 离开苹果公司后成立了 [NeXT Computer](https://zh.wikipedia.org/wiki/NeXT_Computer) 公司。 NeXT 公司于 1988 年获得Objective-C 的授权，并发展了Objective-C的语言库和开发环境，即NEXTSTEP，推出了 NeXT 电脑，使用 NeXTStep 为操作系统。在当时，NeXTStep 是相当先进的系统。以 Unix (BSD) 为基础，使用 PostScript 提供高品质的使用者图形接口，并以 Objective-C 语言提供完整的面向对象环境。

1992年[自由软件基金会](https://zh.wikipedia.org/wiki/自由软件基金会)的 GNU 开发环境增加了对 Objective-C 的支持，所有Free Software foundation(FSF)产品版权归属于FSF，它以GUN通过公关许可来发布产品。

尽管 NeXT 在软件上的优异，其硬体销售成绩不佳，不久之后，NeXT 便转型为软件公司。NeXT也开发了一套[网络程序](https://zh.wikipedia.org/w/index.php?title=網路程式&action=edit&redlink=1)[架框](https://zh.wikipedia.org/w/index.php?title=架框&action=edit&redlink=1)－[WebObjects](https://zh.wikipedia.org/w/index.php?title=WebObjects&action=edit&redlink=1)，用于产生[动态网页](https://zh.wikipedia.org/wiki/動態網頁)。可能因为售价过高之故（超过50,000美元），它并没有流行起来。尽管如此，WebObjects仍为动态网页程序创建了一个良好的示例。

1994 年，NeXT 与太阳 (Sun Microsystem) 合作推出 OpenStep ，目标为跨平台的面向对象程序开发环境。OpenStep分离了NEXTSTEP的Mach基础或NeXT特定硬件的部分。NeXT 接着推出实现 OpenStep 接口的 OPENSTEP 系统，可在 Mach，Microsoft Windows NT，Sun Solaris 及 HP/UX 上执行。1996年12月20日，[苹果公司](https://zh.wikipedia.org/wiki/蘋果公司)宣布收购 NeXT Software 公司，NEXTSTEP/OPENSTEP环境成为苹果操作系统[Mac OS X](https://zh.wikipedia.org/wiki/Mac_OS_X)的基础，WebObjects则集成到[Mac OS X Server](https://zh.wikipedia.org/wiki/Mac_OS_X_Server)和[Xcode](https://zh.wikipedia.org/wiki/Xcode)中。这个开发环境的版本被苹果公司称为[Cocoa](https://zh.wikipedia.org/wiki/Cocoa)。

在 1995 年，自由软件基金会 (Free Software Fundation) 开始了 GNUstep 计划，目的在实现 OpenStep 接口，以提供 Linux/BSD 系统一个完整的程序发展环境。但由于 OpenStep 接口过于庞大，开发人力不足，及许多技术在当时尚未成熟 (如 Display PostScript)，所以直到目前为止，GNUstep 才算是一个完整的程序开发环境。
尽管 OpenStep 早在 1994 年便提出，其接口及架构在现今仍相当先进及实用，使得开发 GNUstep 程序相当容易。

GNUstep 使用 Objective-C 语言，是 C 语言加上 SmallTalk 的面向对象的功能。结合两者的优点，又不至于像 C++ 如此复杂。

GNUstep 提供两个主要的程序库，Foundation 及 AppKit。Foundation 处理非图形接口的部份，如字串，档桉，网路，基本资料结构，多行绪等，又称之为 GNUstep Base。AppKit 则处理图形接口的部份，包含视窗，使用者接口等，又称之为 GNUstep GUI。

由于 GNUstep 具有跨平台的特性，有关绘图及字型的部份，则交由 GNUstep Back 来处理。使用者可依所使用的操作系统，选择适当的后端处理 (Backend)。GNUstep GUI 会自行处理与 Back 相关的功能，程序开发者只要使用 GUI 程序库，便可适用于各种后端上，完全不用考虑平台问题。

目前 GNU GCC 3.x 支援 Objective-C 语言，GNUstep 则提供 GNUstep Make 来简化编译 Objective-C 程序。 GNUstep Make 提供类似 Makefile 的功能，称为 GNUmakefile。与 Makefile 相比较之下 GNUmakefile 简单许多。

综合上述，GNUstep 实现 OpenStep 接口，该接口已在商业市场上使用多年，目前并演进成 MacOS X 的 Cocoa 环境。GNUstep 包含四个主要部份，统称为核心 (Core)：

1. GNUstep Make: 提供类似 Makefile 的功能，称为 GNUmakefile，较 Makefile 好用许多。
2. GNUstep Base: 提供 OpenStep 的 Foundation 程序库，处理非图形接口的功能。
3. GNUstep GUI: 提供 OpenStep 的 AppKit 程序库，处理图形接口的功能。
4. GNUstep Back: 提供与操作系统相关的后端处理，提供 GNUstep GUI 有关绘图及字型的功能。

简单的说 GNUstep 其实也是要打造类似 KDE 或 GNOME 的整合式环境，只是说它用的程序语言是Objective-C，而本身也有一套 GUI Toolkits 来开发，当然先进的面向对象设计是最让人印象深刻的。

### 参考文章

[https://www.oschina.net/p/gnustep-org](https://www.oschina.net/p/gnustep-org)

[https://my.oschina.net/wolx/blog/304204](https://my.oschina.net/wolx/blog/304204)

[https://zh.wikipedia.org/wiki/Objective-C](https://zh.wikipedia.org/wiki/Objective-C)

[https://zh.wikipedia.org/wiki/NeXT](https://zh.wikipedia.org/wiki/NeXT)

[https://zh.wikipedia.org/wiki/OpenStep](https://zh.wikipedia.org/wiki/OpenStep)

[http://www.gnustep.org/resources/OpenStepSpec/OpenStepSpec.html](http://www.gnustep.org/resources/OpenStepSpec/OpenStepSpec.html)

