# Mediator Pattern
<p>中介者模式将一个网状的系统结构变成一个以中介者对象为中心的星形结构，在这个星型结构中，
使用中介者对象与其他对象的一对多关系来取代原有对象之间的多对多关系。中介者模式在事件驱动类
软件中应用较为广泛，特别是基于GUI（Graphical User Interface，图形用户界面）的应用软
件，此外，在类与类之间存在错综复杂的关联关系的系统中，中介者模式都能得到较好的应用。</p>

## 案例需求-客户信息管理窗口的初始设计
<p>Sunny软件公司欲开发一套CRM系统，其中包含一个客户信息管理模块，所设计的“客户信息管理窗口”
Sunny公司开发人员通过分析发现，界面组件之间存在较为复杂的交互关系：如果删除一个客户，要在客户
列表(List)中删掉对应的项，客户选择组合框(ComboBox)中客户名称也将减少一个；如果增加一个客户
信息，客户列表中需增加一个客户，且组合框中也将增加一项。如何实现界面组件之间的交互是Sunny公司
开发人员必须面对的一个问题</p>

## UML 结构图
![Mediator uml](https://github.com/SunnyMarkLiu/Awesome-Design-Patterns/blob/master/BehavioralPattern/Mediator/mediator.jpg)

## 主要优点
   
中介者模式的主要优点如下：
   
1. 中介者模式简化了对象之间的交互，它用中介者和同事的一对多交互代替了原来同事之间的多对多交互，一对多关系更容易理解、维护和扩展，将原本难以理解的网状结构转换成相对简单的星型结构。
2. 中介者模式可将各同事对象解耦。中介者有利于各同事之间的松耦合，我们可以独立的改变和复用每一个同事和中介者，增加新的中介者和新的同事类都比较方便，更好地符合“开闭原则”。
3. 可以减少子类生成，中介者将原本分布于多个对象间的行为集中在一起，改变这些行为只需生成新的中介者子类即可，这使各个同事类可被重用，无须对同事类进行扩展。

## 主要缺点
   
中介者模式的主要缺点如下：
   
1. 在具体中介者类中包含了大量同事之间的交互细节，可能会导致具体中介者类非常复杂，使得系统难以维护。

## 适用场景
   
在以下情况下可以考虑使用中介者模式：
   
1. 系统中对象之间存在复杂的引用关系，系统结构混乱且难以理解。
2. 一个对象由于引用了其他很多对象并且直接和这些对象通信，导致难以复用该对象。
3. 想通过一个中间类来封装多个类中的行为，而又不想生成太多的子类。可以通过引入中介者类来实现，在中介者中定义对象交互的公共行为，如果需要改变行为则可以增加新的具体中介者类。