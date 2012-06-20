---
layout: post
title: "Hello world"
description: ""
category: 
tags: []
---


### Hello world
{% highlight java linenos %}
public class Test {
	public static void main(String[] args) {
		System.out.println("Hello world!");
	}
}
{% endhighlight %}  

{% highlight ruby %}
def foo
  puts 'foo'
end
{% endhighlight %}
{% highlight java %}
session.beginTransaction(); 
String hql = "select userName from User"; 
Query query = session.createQuery(hql); 
List nameList = query.list(); 
for(Object obj:nameList){ 
  System.out.println(obj); 
} 
session.getTransaction().commit();

// 多个属性的话，需要用object[]接收

session.beginTransaction(); 
String hql = "select userName,userPwd from User"; 
Query query = session.createQuery(hql); 
List nameList = query.list(); 

for(Object obj:nameList){ 
	Object[] array = (Object[]) obj; // 转成object[]
	System.out.println("name:" + array[0]); 
	System.out.println("pwd:" + array[1]); 
} 
session.getTransaction().commit();
{% endhighlight %} 
{% highlight java %} 
session.beginTransaction(); 
String hql = "select count(*),max(id) from User"; 
Query query = session.createQuery(hql); 
List nameList = query.list(); 
for(Object obj:nameList){ 
	Object[] array = (Object[]) obj; 
	System.out.println("count:" + array[0]); 
	System.out.println("max:" + array[1]); 
} 
session.getTransaction().commit();

/*  
	该条sql语句返回的是单条数据，所以还可以这样写
	单列数据用Object，多列数据用Object[]
*/

Object[] object = (Object[]) query.uniqueResult();
System.out.println("count:" + object[0]); 
System.out.println("max:" + object[1]);
{% endhighlight %}