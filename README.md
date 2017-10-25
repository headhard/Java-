<h1>Java内部类（详细整理）</h1>
<br>
<br>
<br>

<h2>JAVA中方法的调用主要有以下几种：</h2>
<h3>1.非静态方法</h3>
非静态方法就是没有 static 修饰的方法，对于非静态方法的调用，是通过对 象来调用的，表现形式如下。

对象名.方法（）
eg：

<pre>public class InvokeMethod{
    public static void main(String[] args){
        InvokeMethod in = new InvokeMethod();
        in.t1();
    }
    public void t1(){
        System.out.printfln("t1");
    }
}</pre>
<h3>2.调用静态方法</h3>
静态方法就是用 static 修饰的方法，静态方法的调用是通过类名来调用的， 表现形式如下：

类名.方法()
eg:

<pre>public class InvokeMethod{
    public static void main (String[] args){
        InvokeMethod.t2();
    }
    public static void t2(){
        System.out.println("static t2....");
    }
}</pre>
<h3>3.方法与方法之间的调用</h3>
方法与方法之间的调用，主要是在一个方法内部如何调用其他方法。
（1）静态方法内部调用其他方法
如果在本类当中，静态方法可以直接调用静态方法，
除了在 main 方法中，还可以在自定义的静态方法中直接调用。
如果在本类当中是非静态方法，就必须通过对象来调用。

<pre>public class InvokeMethod{
    public static void main (String[] args){
        t2();
    }
    public static void t2(){
        System.out.println("static t2...");
    }
    public static void t1(){
        //静态方法调用非静态方法需通过对象来调用
        //InvokeMethod in =new InvokeMethod();
        //in.t2();
        t2();
        System.out.println("static t1");
    }
}</pre>
如果不在一个类当中，静态方法调用其他类中的静态方法，必须通过

类名.静态方法（）；
如果在不同类当中，静态方法调用其他类的非静态方法，需要导入该类中的包，以及通过创建对象调用。

（2）非静态方法内部调用
如果在本类中，非静态方法可以直接调用静态方法与非静态方法。
在不同类中，非静态方法调用其他类的静态方法，需要通过导入该类中的包，并且需要通过类名来调用
在不用类中，非静态方法调用其他类的非静态方法时，需要导入该类中的包，还需要通过创建对象来调用。


原文地址 <a href="http://www.imooc.com/article/13423">Java方法调用</a>
