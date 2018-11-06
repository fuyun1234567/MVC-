个人总结：

# MVC #
MVC的重要目的是在人的心智模型和计算机的模型之间建立桥梁，为用户提供直接看到的信息和操作信息的功能
![.NET MVC](https://i.imgur.com/qocVmmQ.jpg)

##理解##
1. Controller负责管理View和Model
2. View负责展示Model的数据

#Spring MVC#
SpringMVC相对于MVC多了用户分发请求、管理视图的DispatchServlet
![Spring MVC](https://i.imgur.com/QPudt3V.jpg)
## 分析 ##

1. 通过DispatchServlet将Controller和View层完全解耦
2. View层和Model层没有直接关系，存在间接关系，Contrlloer对Model进行查询、返回给DispatchServlet后传递给View层

# 其他的MVC #
1. IOS MVC
2. Rails MVC
3. WIKI的MVC

# 标准的MVC #
- View：管理屏幕的图形和文字输出
- Controller：翻译用户输入，依照用户输入操作模型和视图
- Model：管理应用的行为和数据，相应数据请求和更新状态
## 依赖关系 ##
Model可以单独工作，而View和Controller都依赖Model中的数据

#MVVM#

##PM##
PM模式（Presentation Model）是MVVM的前身，
PM模式与分离展示层Separated Presentation有一定的关系。
PM 模式将**视图中的全部状态和行为放到一个单独的展示模型中，协调领域对象（模型）并且为视图层提供一个接口。**
![PM](https://i.imgur.com/IBNTA1a.jpg)
在监督控制器中，View层与Model层中的一些简单属性进行绑定，在Model属性变化时直接更新View，而 PM 通过引入展示模型将Model层中的数据与复杂的业务逻辑封装成属性与简单的数据同时暴露给Vew，让View和展示模型中的属性进行同步。

View中包含所有的View渲染需要的动态信息，包括View的内容（text、color）、Component是否启用（enable），除此之外还会将一些方法暴露给View用于某些事件的响应。

##MVVM##

MVVM基本遵循PM模式的实现
![MVVM](https://i.imgur.com/1KTnLWC.jpg)

从上面可以看到Model-ViewModel-Model之间的关系，在MVVM中的ViewModel就是PM中的展示模型，在MVVM中称为视图模型。

除了以上三个部分，还有一个隐式的一个Binder层，而声明式的数据和命令的绑定在 MVVM 模式中就是通过它完成的。
![Blinder](https://i.imgur.com/zDjzfto.jpg)
无论是 MVVM 还是 Presentation Model中最重要的不是如何同步视图和展示模型/视图模型之间的状态，是使用观察者模式、双向绑定还是其它的机制都不是整个模式中最重要的部分，最为关键的是**展示模型/视图模型创建了一个视图的抽象，将视图中的状态和行为抽离出一个新的抽象，这才是 MVVM 和 PM 中需要注意的**。


##本文档内容非原创##