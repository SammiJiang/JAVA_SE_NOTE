# Collection - List

## 集合继承关系图

> -Collection
>
>  - list: array List, linked List
>    - List 可以放重复对象
>  - Set: hash Set, Three Set 
>    - set不可以放重复对象

## Array List and Linked List

### array 的弊端

``` java
public class Entrance{
    public static void main (String[]args){
        int[] array = new int[2];
        array[0]=0;
        array[1]=1;
        //这样的话需要新建array 不能延长
        array=new int [3];
        array[0]=0;
        array[1]=1;
        array[1]=2;
        
    }
}

```

``` java
// 在jdk中每个基本类型都有一个类被写出来
int a =3; 
integer asd = new(3);

double --->Double;
```

```java
public class Entrance{
    public static void main (String[]args){
        ArrayList<String> list = new ArrayList<>();
   
    }
}

//String a= "a";
//String b= "a";
a 和 b指定的是相同的对象
//String c= New String("a");
//String d= New String("a");
c 和 d指向的对象并不相同
```

### Example 

`.remove()`

### 原理是使用`.euqals()` 方法进行比较

```java
public class Entrance{
    public static void main (String[]args){
        ArrayList<String> list = new ArrayList<>();
        Person p1 = new Person();
        Person p2 = new Person();
        list.add(p1);
        list.add(p1); 
        list.add(p2);
        list.remove(p1);//remove 第一个元素
        list.remove(p2);//remove 第2个元素
        /**	
        remove  的原理是
        p2.equals(第一个元素)
        p2.equals(第二个元素)
        依次类推，只有是同一个对象才会返回true
        
		**/
        
    }
}
class Person{
    int age =19l;
    void equals(Object ob){
        return(this==obj);
        
    }
  	
    
}

```

###  覆写equals 方法 : equals 本质是让两个对象相等，因此可以用自己的定义方法来定义两个对象是否相等

#### 下面的例子：如果age相等那就是同样的对象

```java

public class Entrance{
    public static void main (String[]args){
        ArrayList<String> list = new ArrayList<>();
        Person p1 = new Person(18);
        Person p2 = new Person(18);
        list.add(p1);
        list.add(p1); 
        list.add(p1);
        list.remove(p2);
        // this will return true 
        
    }
}
class Person{
    int age =19l;
    Person(int age){
        this.age=age
    }
    void equals(Object ob){
        return(this==obj);
        
    }
    Boolean equals (Object obj){
        Person p = (Person)obj;
        return this.age==p.age
    }
  	
    
}

    
```

###  一些常用的方法

`.addAll()` 改变被add的list的长度

```java
public class Entrance{
    public static void main (String[]args){
        ArrayList<String> list1 = new ArrayList<>();
        ArrayList<String> list2 = new ArrayList<>();
        Person p1 = new Person(18);
        Person p2 = new Person(18);
        list1.add(p1);
        list1.add(p1); 
        list1.add(p1);
        
        list2.add(p2);
        list2.add(p2);
        list2.add(p2);
        
        list1.add(p2);
        
        
        
    }
}
```



### 集合的遍历

```java
public class Entrance{
    public static void main (String[]args){	
        ArrayList coll = new ArrayList();
        coll.add(new Student("张三",23));		
        coll.add(new Student("李四",24));
        coll.add(new Student("王五",25));
        coll.add(new Student("赵六",26));
        //1
        Object[] arr = coll.toArray();				
        for (int i = 0; i < arr.length; i++) {
            Student s = (Student)arr[i];			
            System.out.println(s.getName() + "," + s.getAge());
        }
        
        //itertor 
        Iterator <Person> it = coll.iterator();
        while (it.hasNext()){
            Person p =it.next();
            System.out.println(p.getName());
            list.remove(p);
           //这样会报错 cocurent comodifictaion
            如果使用it.remove(); 就没有问题，如果需要改变list结构，最好使用list本身的方法
        }
        //3: for each
        
    }
}
class Person{
    int age =19l;
    Person(int age){
        this.age=age
    }
    void equals(Object ob){
        return(this==obj);
        
    }
    Boolean equals (Object obj){
        Person p = (Person)obj;
        return this.age==p.age
    }
  	
    
}

```



