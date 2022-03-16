# Set

## Can't store 2 identical element

```java
public class A {
    public static void main(String[]args){
        HashSet<String> a = new HashSet<>();
        boolean b1= a.add("China");
        boolean b2= a.add("China");
        boolean b3= a.add("China1");
        System.out.println(b1);
    }
}
```

### 如果new string是创立对象呢

```java
public class A {
    public static void main(String[]args){
        HashSet<String> a = new HashSet<>();
        String s1 = "China";
        String s2 = "China";
        System.out.println(s1==s2);//true 
        
        String s3= new String("A");
        String s4= new String("B");
        System.out.println(s3==s4);//false
        
       
        boolean b1= a.add(new String("China"));//true
        boolean b2= a.add(new String("China"));//False
       
    }

}


```

### 问题1： 既然是两个不同对象，为什么添加进去的时候还是会展示成为false呢，第二个对象为什么无法添加呢

```java
public class A {
    public static void main(String[]args){
        
    }
}
class String{
    boolean equals(object o){
        //这里的equals 方法是重新覆写过的
    }
}
```



## Hash Set

### hashcode

#### hashCode 方法返回的值不同，则一定不是同一个对象

#### hashCode 的方法返回值相同，则不一定是同一个对象



`equals()` 比较耗时，`hashcode` 节省时间，相同的话再调用`equals()` 方法

无论那个类都有hashcode这个方法

```java

public class A{
	public static void main (String[]args){
        HashSet<String> a =new HashSet<>();
        boolean b1 = a.add("China");
        boolean b2 =a.add("China");
        System.out.println(b1);
        System.out.println(b2);
        for (Person unit: a){
            
        }
    }
}
class Person{
    String name;
    Person(String name ){
        this.name =name;
    }
    public boolean equals(Object o){
        Person p =(Person) o;
        return this.name.euqal(p.name);
    }
    //强制让hashcode return same就可以吊euqlas方法
    public int hashCode(){
        return 0;
    }
    
        
}
```



## Tree Set 

### example 

```java

```

