# 模版方法模式

模板方法主要是为了解决一些方法通用性问题，将通用方法放在父类，需要单独实现的方法放在其他类中，将通用方法和变化的方法分开，各自实现分开到不同的地方，并且可以单独实现，往往是将将变化部分方法/处理器的实现延迟到子类或者其他可注入的类型中。


go 的结构对象和接口的分离做的更彻底，不需要像其他语言一样显式声明继承或者实现关系，所以在实现模板方法时候更灵活。

模板方法的特点在于，定义一好一套接口，定义基本类型结构作为父类，同时在父类中组合好调用方式，并实现好通用的方法，变化部分的接口的具体实现可以在子类或者其他地方实现。

现实生活中工作中，文件打印就是一个很好的模板方法的例子，我们打印操作一般式：

文件--->设置--->打印.

但是对于不同的打印方式对于同一个文件的打印实现可能略有不同。

比如虚拟打印到 pdf或者xps与打印打纸质文件需要的设置和打印肯定式不同的，虚拟打印你肯定需要指明输出路径，纸质打印需要可能需要设置打印质量，质量越高，越费墨。

