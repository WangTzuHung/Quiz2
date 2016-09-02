#A1
```ruby
a = 1 #將變數的a的值指定為1

@a = 2  #將實例變數(instance variable)a的值指定為2

@@a = 5 #將類別變數(class variable)a指定為5

user = User.new  #用User的類別創造一個user的物件

user.name #name是user這個物件的實例變數 或name是user這個物件的實例方法(沒有更多線索，不能確定)

user.name = "Joe" #將user這個物件的實例變數name指定為字串"Joe"
```

***

#A2
```
  module就是不能產生實例（也就是不能new)以及不能被繼承的class(因為class是繼承自module)

  如果在不同的類別裡面都需要有同樣的功能，則可以將同樣的功能做成module，讓各個class直接include這個module  

```
```ruby
module CanSwim
  def Swim
    puts "I can CanSwim!"
  end
end

class Fish
  include CanSwim
end

littlefish = Fish.new
littlefish.CanSwim
```

***

#A3
```
當多個instance從某個class或是該class的子類別new出來後，每個instance都會各自擁有各自的instance variable
，每個instance之間的instance variable並不會互相干擾。而class variable
則是所有instance共用，當任意instance存取到class variable
則其他instance都會受到影響。

```

***

#A4
```
class method:只有class自己能用，所有該class new出來的物件都無法使用。感覺類似Java/C#裡類別的靜態方法

instance method:當某class裡面定義了instance method，則所有該class new出來的物件都可以使用。但是class自己無法使用。
```

```ruby
class SomeClass
  def self.A
    puts 'class method'
  end
  
  def B
    puts 'instance method'
  end
end

SomeClass.A # => "class method"
SomeClass.B # => NoMethodError

SomeClass.new.A # => NoMethodError
SomeClass.new.B # => instance method
```

***

#A5
```ruby
class User
  def initialize(name, gender, job)
      @name = name
      @gender = gender
      @job = job
  end
end
```

***

#A6
```
在class裡面，instance method外面，self是指class自己
在class裡面，instance method裡面，self是指被new出的某instance 
```

***

#A7
```
當一個class裡面有宣告變數時，必須有能對這個變數做寫入或讀取的方法(geter method / seter method)該變數才能被使用。
而attr_accessor、attr_reader、attr_writer就是自動產生這些method的方法

如果一個變數只能被讀取時，要使用attr_reader
如果一個變數只能被寫入時要使用attr_writer
如果一個變數可以被讀取也可以被寫入時要使用attr_accessor

```

***

#A8
```
private method只有該類別所產生的物件內部能使用
public method可以被外部呼叫
public method可以被繼承
private method不能繼承
```

***

#A9
```
  如果在不同的類別裡面都需要有同樣的功能，則可以將同樣的功能做成module，讓各個class直接include這個module 
```
```ruby
module CanSwim
  def Swim
    puts "I can CanSwim!"
  end
end

class Fish
  include CanSwim #=>I can CanSwim!
end

littlefish = Fish.new
littlefish.CanSwim

class Human
  include CanSwim
end

kid = Human.new
kid.CanSwim #=>I can CanSwim!
```

***

#A10
```
 class 有 include 一個 module，那他的sub class可以使用該class include 的module，
 因為如果object呼叫了一個它的class裡面沒有的Method
他就會依序找他所有的祖先，若找到了有這個 method 的祖先，就使用這個祖先類別的。
因此parent class無法使用 sub class 的module

```

#A11
```
Relational Database:泛指所有關聯式資料庫，像是sql server、my sql、sqlite等
SQL:Structural Query Language，是關聯式資料庫用的查詢語言
```