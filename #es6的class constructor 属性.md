# es6的class constructor 属性

```js
  <script>
    // 基本上，ES6 的class可以看作只是一个语法糖，它的绝大部分功能，ES5 都可以做到，
    // 新的class写法只是让对象原型的写法更加清晰、更像面向对象编程的语法而已。

    //基本使用
    class Animal{
            // name = "jerry"
            // age = 55
            
            // 静态属性，必须使用类名去访问，该类公共的那些属性，可以定义成static
            static address = "地球"
            // 实例属性
            name = ""
            age = 0

            constructor(name,age){
                // 使用this.属性名来赋值
                this.name = name
                this.age = age
            }
            //动态方法 取值的话也是this   上下不要加逗号 否则会报错
            eat(food){
                console.log(`${this.name} 吃 ${food}`)
            }
            //静态方法
            static huxi(){
                console.log('深呼吸...')
            }
        }
        //静态属性和静态方法都需要直接点出
        Animal.address = '火星'
        Animal.huxi()

        //实例化的动态方法都需要这样
        const a1 = new Animal('旺财',3)
        //或者这样
        // 实例属性/对象属性
        // a1.name = '旺财'
        // a1.age = 3
        console.log(a1.name);  //旺财
        console.log(a1.age);   //3
        a1.eat('鱼子酱');      //旺财 吃 鱼子酱
        
    </script>
```

## 使用的注意点

+ 我们在使用的时候一些公共的属性 和公共的方法放在这里面 

+ 然后一些变化的单独处理

+ ```js
   constructor(name,age){//constructor是一个构造方法，用来接收参数
          this.name = name;//this代表的是实例对象
          this.age=age;
     }
   eat(food){     //这是一个类的方法，注意千万不要加上function
  ```

```
1.在类中声明方法的时候，千万不要给该方法加上function关键字
2.方法之间不要用逗号分隔，否则会报错
```