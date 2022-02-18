# shoppingmall-notes
购物商城笔记

# 2021-11-3 选集P1-P14

### coderwhy老师的Vue课程：

1、对真实数据进行复杂处理再展示到页面中

2、IT从业者要不断学习，自学，虽然多但很多东西是相通的

Vue是渐进式的框架：一点一点将应用放入Vue框架

### Vue高级功能：

- 解耦数据和视图

- 组件可复用
- 前端路由
- 状态管理
- 虚拟DOM

编程范式，HTML、CSS、JS、ES6（更好用）babel工具将ES6转为ES5，提供给浏览器使用，

x读叉，而不是欸克斯

### Vuejs安装（开发环境和生产环境）：

- 发布项目，需要CDN引入第三方库，选择更近的服务器
- 学习Vuejs，下载和引入
- NPM安装，使用，通过webpack和CLI的使用

webstorm（IDE：集成开发环境）和vscode（编辑器）

vscode有很多插件，免费，也有很多快捷键

### let(变量)/const(常量)

- 原生JS的做法：编程范式：命令式编程，分步骤，1，2，3告诉电脑怎么做

- Vuejs的做法：编程范式：声明式编程，声明需要显示的数据，内部逻辑不用管
- 声明式编程的好处：数据和样式分离，请求服务器数据界面不需要更改

- 响应式：数据发生改变时，界面会跟着改变

### 列表展示：

- 指令：v-for=“item in items" {{item}}
- data: {items: []}

### 计数器：

- 指令：v-on，语法糖@（语法糖：简写alias）
- methods: {increment(){},decrement(){}}

proxy：代理，this指向

### Vue中的MVVM（维基百科），Vue是标准的MVVM框架

- Model：JS Objects（服务器数据）
- View：DOM
- View Model：Vue实例做两件事：data bindings（数据绑定）（服务器端）和DOM Listeners（DOM监听）（用户端行为监听）

### 目前掌握的options：

- el:
- data:
- methods

方法（methods）和函数（function）

- 方法一般定义在类里面，与某个实例挂钩
- 而函数定义在全局变量中，两者其实差不多，叫法不一样

git上稳定的版本：tags的版本，已测试释放发布的release

### Vue的生命周期：（也叫做钩子函数hooks）

- 生命周期：事物从诞生到消亡的整个过程，例如一个人在整个生命周期的不同阶段会做不同事情
- Vue的生命周期：执行某个操作时进行回调
  - beforecreate() {}
  - created() {}
  - beforemounted() {}
  - mounted() {}
  - beforeUpdate() {}
  - updated() {}
  - beforeDestroy() {}
  - destroyed() {} 一般组件才会销毁
  - 根据项目需求来使用这些回调

代码规范：CLI：editconfig:2

### 插值操作：（绑定到文本）

- Mustache语法：插入变量或者简单的表达式
- 与插值有关系的指令：
  - v-once：渲染之后不会跟着之后改动的数据再次更改
  - v-html：返回的数据为标签时，在属性上指定标签变量渲染
  - v-text：一般不用，不够灵活
  - v-pre：很少用，和标签pre相似，原封不动显示标签中的东西
  - v-cloak：基本不会用，斗篷，vue代码解析前存在，解析后消失 [v-cloak] {display: none;} 

# 2021-11-4 选集P15-P23

### 属性根据数据动态改变：

​	展示服务器返回的JSON数据

### 绑定属性class：（绑定到属性）

 - 指令：v-bind:
 - 动态绑定后，Vue会将双引号内的内容解析为变量
 - 语法糖：简写方式：v-bind: => :
 - 对象语法：
   - 通过修改布尔值来判断是否添加属性
   - 对象过于复杂可以放在methods或computed里面
 - 数组语法：
   - 用的很少，因为类是写死的

### 绑定样式style：（组件化开发使用，可复用，插槽定制）

- 注意字符串和变量问题
- 对象语法：提取到methods中
- 数组语法：用的很少，定义类名添加为数组项

### 计算属性：computed

- 对数据进行处理再展示
- 定义函数但是不同于方法，名字起为属性名，不需要添加动词

- 本质是属性，添加到HTML中不需要加小括号
- 多次调用时，只执行一次，有缓存，性能高
- 高阶函数：filter/map/reduce

# 2021-11-5 选集P24-P44

### 计算属性：computed

- set()方法
- get()方法
- 计算属性一般没有set方法，只读属性
- 计算属性只有get方法，为了简便使用，省略get，直接将computed当作属性使用
- 使用set方法可以更改计算属性（但是99%的情况不使用）

### 计算属性和methods的对比

- 计算属性会被Vue缓存，若内部参数无变化，会直接返回结果不再计算，即多次使用，只会调用一次
- methods调用几次就会重新计算几次
- 因此在计算属性中定义函数方法，性能较高

### 补充ES6语法

- let/const/对象增强语法
- let：变量后续需要改变，存在块级作用域
- const：
  - 变量定义后不再改变
  - 定义时必须赋值
  - 指向的对象不能修改，但是可以改变对象内部的属性（const修饰的变量，不能改变指向内存的地址，所以定义的不能修改，但是指向对象时，对象里面属性并不是变量的地址，所以可以修改）
  - 存在块级作用域，开发中优先使用const
- 若无块级作用域，变量会被意外更改
- for循环事件监听内的函数是回调函数，访问的变量如果是var定义会被改变，因为for块级没有块级作用域，而let定义则有属于自己函数内的变量

- 对象字面量增强写法：去掉冗余代码
  - 属性的增强写法：键值对相同时可简写为只写一个
  - 函数的增强写法：函数名() {}

- TypeScript还有类型检测，感觉JS太多缺点了，没有类型检测编译时无法发现错误，要运行时才会发现，不过JS也在不断改善把，ES6改善了很多，加油吧！

### 监听事件：v-on指令

- 参数问题：
  - 调用方法不需要传参数时可以不用添加后面的()，假如方法需要传参但是没有添加()，Vue会默认将浏览器生成的event事件对象作为参数传入
  - 定义方法时既需要event对象，又需要其他参数，通过传入$event获取event对象
- v-on修饰符：（特殊情况下使用）
  - .stop修饰符：阻止事件冒泡，调用event.stopPropagation()
  - .prevent修饰符：阻止默认行为，调用event.preventDefault(）
  - .enter修饰符：监听按下回车键
  - .native修饰符：监听组件根元素的原生事件
  - .once修饰符：只触发一次回调

### 条件判断：v-if、v-else-if、v-else、v-show

- 非常复杂逻辑的判断，不建议v-else-if，而是使用计算属性computed，在里面定义属性做判断
- 输入框案例小问题：输入的内容切换类型后不会消失
  - 涉及到Vue底层的虚拟DOM原理
  - 先将即将显示的标签放到VDOM即在内存中创建的虚拟DOM中，是真实DOM的映射
  - Vue基于性能的考虑，在将虚拟DOM渲染到真实DOM时，会复用重复的内容
  - 如果不希望复用，可以添加key属性，作为标识，添加key之后，整个标签会被替换，之前未添加key时只替换了不同的内容
- v-show：决定一个元素是否要显示出来，依然会存在于DOM中
  - 即如果v-show=“false”，底层原理是给元素添加style="display: none"样式
  - 而如果v-if="false"，vue不会将其渲染到DOM中，改为true会重新渲染
- 需要在显示与隐藏之间切换频繁时，使用v-show，因为元素存在于DOM，切换成本低，性能好，效率高
- 当只有一次切换时，使用v-if
- 实际开发中，v-if用的更多，因为实际开发从服务器中获取数据来决定是否渲染DOM

### 循环遍历：v-for

- 数组：v-for="(item, index) in items"（v-for更多的是遍历数组）
- 对象：
  - v-for="item in items"，获取到的是键值对的值
  - v-for="(value, key) in items" ，能获取到键值对
  - v-for="(value, key, index) in items"

- 官方推荐使用v-for时，在元素或组件上添加key属性，目的是为了更好的复用
  - Array.splice()方法 在数组中插入剔除元素（传入两个参数，剔除；传入三个参数，第二参数为0，添加）
  - Vue创建虚拟DOM，再往真实DOMpatch
  - diff算法，对比真实DOM和虚拟DOM，若发现不同，则重新渲染
  - 添加key，可以提高性能，不需要一个一个替换，而是直接创建插入
  - key不要绑定index，因为index不是一一对应的，每次都会变，要绑定一一对应的，id值或者item本身字符串
  - 总结：key的作用主要是为了高效的更新虚拟DOM
- 并不是所有改变数组的方法都是响应式的
  - 以下方法可以做到响应式：push、pop、shift、unshift、splice（删除、插入、替换元素，第二个参数是否为0来决定）、sort、reverse、vue.set()
  - 通过索引值修改数组中的元素的方式不是响应式的
  - 可变参数：function sum(...num) 此写法调用函数sum()时可以随意传入多个参数
- 作业回顾：
  - 定义一个currentIndex属性
  - 定义一个方法将当前项的index传给currentIndex再进行比较，比较结果为布尔值，以此决定是否添加定义的类
- 书籍购物车案例
  - Vue中的过滤器：filters: {showPrice() {}}
  - 获取index，传入方法中改变当前项的数目
  - 按钮有disabled属性 不可点击，动态绑定，判断值是否小于1来获取布尔值
  - v-if和v-else

# 2021-11-5 选集P45-P54

### 编程范式：

- 命令式编程：按步骤一步一步来
- 声明式编程：拿到数据，自动遍历展示
- 面向对象编程：抽象成对象，封装继承多态，第一公民是对象
- 函数式编程：抽象成函数，第一公民是函数，链式编程

### 数组的高阶函数

filter

- filter中的回调函数有一个要求，必须返回一个布尔值
- 当返回true时，函数内部会自动将这次回调的n加入到新数组中
- 当返回false时，函数内部会过滤掉这次的n

map（映射操作）

- 回调函数中返回每个数组成员或计算处理后的数组成员

reduce

- 作用是对数组中所有的内容进行汇总
- 可以传入两个参数：第一个参数为回调函数，第二个参数为初始值
- 回调函数中有两个参数：第一个参数为初始值，第二个参数为数组成员
- 第一次遍历在回调函数中处理初始值和第一个数组成员，返回处理的结果
- 第二次遍历返回第一次遍历返回的结果和第二个数组成员处理的结果
- 有点递归函数那味儿了

函数式编程：三种高阶函数可以进行链式编程一起使用

### 表单绑定：v-model

实现双向绑定

原理：

- v-bind和v-on两个指令的结合
- 表单v-bind绑定实例中的message
- 表单v-on监听表单值的改变，将event.target.value传递给message
- 以这两个步骤实现v-model

v-model也可以用于textarea

单选框radio

- 为了互斥，给个一样的属性name="gender"
- 但是如果给了v-model，绑定同一个变量，那就不需要给name属性
- 给变量一个默认值，单选框即有默认选择

复选框checkbox

- v-model绑定单选框勾选情况的布尔值，定义布尔变量
- 通过布尔值判断是否勾选，是否进行下一步
- v-model绑定多选框勾选的value，定义数组变量

选择select

- 在select标签中添加v-model
- 定义字符串变量和数组变量

v-model的值绑定

- 动态遍历服务器获取的数据列表
- 动态绑定用户选择的数据
- 也就是说，真实开发，值不要写死，而是从服务器获取，其实就是v-bind

v-model修饰符

- 事件监听也有几个修饰符：.once/.stop/.prevent
- v-model主要有三个修饰符：.lazy/.number/.trim
- .lazy：实时绑定数据时用户只想敲回车或者失去焦点时才想绑定
- .number：默认情况下v-model返回的变量类型为String类型，但如果我们希望是number类型，可以添加.number修饰符
- .trim：剥除输入的字符串的两边空格

### 组件化开发

什么是组件化？

- 面对一个复杂问题时，可以拆分成很多个可以处理的小问题，放在整体中，复杂问题迎刃而解
- 组件化也是类似思想
- 如果页面所有处理逻辑放在一起，处理起来会很复杂，不利于后期管理维护扩展
- 如果页面拆分成一个个小功能块，每个功能块完成属于自己的独立功能，之后页面的管理和维护会变得非常容易
- Vue组件化思想：
  - 提供抽象，可以开发独立复用的小组件构造应用
  - 任何应用都会被抽象成一颗组件树（树结构）
- 组件化思想应用：
  - 将页面拆分成一个个小的、可复用的组件
  - 使代码更加方便组织和管理，扩展性也更强
- 组件的使用：
  - 创建组件构造器：const cpnC = Vue.extend({template：``})，ES6中的模板字符串语法，有语法糖
  - 注册组件（全局和局部）Vue.component('组件名'，cpnC)
  - 使用组件

全局组件和局部组件

- Vue.component() 全局组件可以在多个Vue的实例下使用
- const app = new Vue({components: {}}) 局部组件在Vue实例中注册，只能在这个实例中使用
- 开发中使用最多的是局部组件，因为开发中也只有一个Vue实例

# 2021-11-7选集P55-P68

### 父组件和子组件注册：

- talk is cheap,show me the code

- 父组件在Vue实例上注册，子组件在父组件上注册
- Vue实例实际上是根组件
- 子组件注册到父组件的components时，Vue会编译好父组件的模块（替换子组件的模板，交由实例之前已经确定）
- 渲染为render函数
- 该模块的内容已经决定了父组件将要渲染的HTML

### 注册组件的语法糖

- 省去调用Vue.extend()步骤，直接使用一个对象来代替

### 注册组件的模板抽离

- 第一种写法：script标签，text/x-template类型，给id，’#‘挂载
- 第二种写法：template标签（应用较多），给id，'#'挂载

### 组件数据

- 根据服务器获取的数据动态渲染
- 组件是一个单独功能模块的封装，有属于自己的HTML模板，也应该有属于自己的数据data
- 这个data属性必须是一个函数，这个函数返回一个对象，对象内部保存着数据

### 为什么组件数据的存放必须是个函数返回一个对象？

- 根据注册的组件模板，创建多个组件实例，而不共用同一个data，因为我们将data定义为一个函数，每个函数有自己的作用域
- 调用函数时每次在栈空间创建不同的变量，变量保存不同的内存地址，指向各自独一无二的数据
- 因此组件在操作改变自己的变量时，不会影响到其他组件实例，因此需要将data定义为一个函数
- 组件应该是独立可复用的，因此每个组件的内部数据不能互相影响

### 父子组件的通信

- 需求：向服务器发送请求，请求列表数据，渲染组件内的列表，在最外层组件发送网络请求，子组件展示数据，因此需要父子组件通信，数据或事件传递
- 父组件通过props（properties）向子组件传递数据
- 子组件通过自定义事件（$emit发出事件）向父组件发送消息
- 真实开发中，Vue实例和子组件的通信，父组件和子组件之间的通信，是一样的

### props（父传子常用）

- 子组件中定义props为数组，数组成员为字符串变量，很少用
- 实际开发中，定义props为对象，键值对中，键名为变量，键值为数据验证类型，比如Array，String，Number等；键值也可以是一个对象，提供一些默认值{type: '', default: '', required:true}

- 子组件标签中使用v-bind绑定父组件变量
- 子标签绑定变量不支持驼峰命名法，可以使用短横线分割法
- 定义子组件模板时，如果有多个标签，需要添加一个根标签div

### 自定义事件（子传父）

- 需求：用户点击子组件按钮，父组件根据点击事件传送相应数据
- 子组件标签中监听事件，传递自定义事件和参数
- 子组件方法中定义自定义事件并且使用this.$emit('')发射第二个自定义事件
- 发射后，父组件在模板标签中监听第二个自定义事件v-on，然后在实例中定义事件方法，当子组件发生事件后，父组件执行事件方法
- 自定义事件不是浏览器默认事件对象，因此传递默认参数不是event对象，而是子组件发射的参数

### 项目

- npm install
- npm run serve

### 组件化开发、前端模块化、webpack、Vue-CLI（选项的作用）

### prop父子组件通信

- 子组件v-model对input双向绑定，而实际上应该避免直接在子组件上对prop定义的的变量进行修改，Vue建议通过父组件来修改mutateprop，因此不要v-model到porps上。
- watch：监听数据的改变
- watch里面定义的也是方法，按照props里面的变量起名，传入参数newValue：给数据赋值，通过this.$emit发射事件

### 父子组件的访问方式：

- 父组件访问子组件：$children或者$refs
- 子组件访问父组件：$parent

#### $children(不太使用)

- 本身是个数组类型
- 子组件是其中一个数组成员
- 数组成员是一个对象，可以调用其中的数据和方法
- 实际开发中不会使用这个属性，而是使用另一个$refs

#### $refs(最常用)

- 默认是个空对象
- 必须在组件元素上添加ref属性，属性值为引用对象名字
- 返回一个对象类型
- this.$refs.aaa.fn()

#### $parent(不太使用)

- 组件应该是独立可复用的
- 但是使用这个属性后，独立可复用性不强，耦合度太高，引用数据容易报错
- $root：访问根组件，也很少使用，因为实际开发中实例中不会放数据

# 2021-11-8 选集P69-P79

### 插槽slot

- 组件插槽让封装的组件更加具有拓展性
- 让使用者可以决定组件内部的一些内容到底展示什么
- 真实开发中，很多组件需要预留插槽：共用一个组件，但是每个组件的具体细节不太一样，预留插槽，可以插入不同的文字标签内容，这样可以使组件具有很强的拓展性
- 如何封装呢？：抽取共性，保留不同

### 基本使用：

- 在模板中添加slot标签，在组件标签中添加插入内容
- 模板中slot标签内可添加默认内容
- 若有多个内容放入组件标签，则一起替换

### 具名插槽

- 某个位置需要使用某个内容
- 给插槽起名字：添加属性name，值为插槽名
- 打开组件标签添加内容，在内容标签上添加slot属性，属性值为插槽名
- 实际开放中，APP顶部的导航栏肯定是用具名插槽

### 编译作用域

- 在Vue实例中的模板，使用的变量的作用域都是Vue实例的
- 在组件模板template中，使用的变量的作用域都是组件中定义的
- 父组件模板的所有东西都会在父级作用域内编译；子组件模板的所有东西都会在子级作用域内编译

### 作用域插槽

- 父组件替换插槽的标签，但是内容由子组件来提供
- 在父组件组件模板中，获取子组件中的数据
- 1、在子组件模板插槽中定义一个属性绑定子组件中的数据：v-bind:data="message"
- 2、在父组件的组件标签中，定义template标签，标签中添加属性：slot-scope="slot"
- 3、之后打开template标签，添加展示方式，例如以星号分隔：{{slot.data.join('*')}}
- 总体来说，父组件通过slot.data能获取子组件中数据自主展示

### 项目：业务逻辑、数据处理、封装思想

### 模块化开发

三大框架阶段，实际开发中都是模块化开发

遵守规范，进行模块化开发

常见的模块化规范：CommonJS、AMD、CMD、ES6的Modules

模块化的两个核心：

- 导出：webpack-node环境-module.exports(CommonJS)
- 导入：require('./xxx.js')(CommonJS)

ES6的模块化

- export导出
- import导入

### webpack

认识、安装、起步、配置、loader使用、配置Vue、plugin、本地服务器

本质：

- 现代的JavaScript应用的静态模块打包工具
- 模块
- 打包

webpack将各种文件打包成一个文件夹，部署在服务器上，再发送给客户端，webpack本身也依赖于node环境，而node环境又包含各种依赖的包，为了管理这些依赖的包，又有一个包管理工具npm（node packages manager）

webpack指定3.6.0，因为vue cli2依赖该版本

- 安装webpack：npm install webpack3.6.0 -g
- 全局安装和局部安装
- package.json 

- dist-distribution 发布 打包到服务器

- webpack打包时自动处理模块之间的依赖：webpack ./src/main.js/ ./dist/bundle.js

- index.html引用bundle.js文件

配置文件，方便在终端输入webpack之后就快速打包处理，而不需要输入上面那么一长串代码路径，但实际开发中不会使用webpck命令，打包的话是使用npm run build（webpack和npm run映射）

- 输入webpack，系统就知道我要打包文件，为了做到这点，需要配置webpack文件，配置入口和出口，入口简单，出口要定义一个对象，包括path和filename，path要动态获取，需要用到node语法（node里的path包）
- npm init -> 生成 package.json 这个文件告诉你当前项目的信息
- npm install
- 绝对路径，node里上下文环境中的path.resolve(__dirname, 'dist') 得到当前文件的路径，再和dist拼接

实际开发中配置npm run build来打包文件

- 打开package.json文件
- 找到“scripts”选项
- 添加键值对："build": "webpack"

实际开发中，有本地的webpack包，全局用的很少，每个项目依赖的webpack不一样，版本不一样，因此需要配置本地的webpack包，避免出现意料之外的错误

- 开发时依赖  --save-dev  "devDependencies": {}
- 运行时依赖  "dependencies": {}
- 只要是在终端敲的命令，都是全局的
- 只有配置了脚本"scripts"，才会优先找本地的
- npm run build

### loader是webpack中一个非常核心的概念

- 需求：加载CSS、图片，将ES6、TypeScript转成ES5，将scss、less转成css，将jsx、vue转成js
- webpack不支持这些转化
- 因此给webpack扩展对应的loader

loader使用：

- 1、npm安装需要使用的loader
- 2、在webpack.config.js中的modules关键字下进行配置

入口的东西放在最外层，功能的东西放在文件夹

webpack只会打包产生依赖的文件，而要对css文件产生依赖，需要使用loader

- css-loader只负责加载，不负责解析
- style-loader负责添加样式到DOM上
- 使用多个loader时，是从右向左读取

# 2021-11-8 选集P80-P90

### less文件使用loader打包

- 创建less文件

- main.js依赖less文件
- npm install less-loader less
- 配置webpack.config.js: module{rules:[]}
- npm run build (搭建本地服务器，热更新)

### CSS中依赖的图片用loader打包

- css中依赖的图片也需要配置loader
- npm install --save-dev url-loader
- 配置webpack.config.js
- 加载的图片小于limit时，图片会编译成base64字符串渲染在页面上
- 加载的图片大于limit时，需要安装file-loader：npm install file-loader --save-dev，这时重新编译，图片会被打包到dist文件夹（哈希生成32位的哈希值），因此需要配置图片加载路径
- 在webpack.config.js里面的output添加键值对：publicPath: 'dist/'
- 对打包的图片名字有一定的规范 img/name.hash:8.ext
  - 首先放在同一个文件夹中img
  - 再加上原来的名字name
  - 防止名字冲突，依然使用hash8，保留8位
  - 最后使用图片原来的拓展名ext(extension的缩写)
  - 在webpack中options配置：name: 'img/[name].[hash:8].[ext]'

### ES6文件打包成ES5用loader打包

- npm install --save-dev babel-loader@7 babel-core babel-preset-es2015
- 配置webpack.config.js文件
  - exclude排除
- 查看bundle.js文件，其中内容变成ES5语法

### webpack配置Vue

- 在webpack环境中集成Vuejs（模块化思想）

- npm install vue --save
- main.js引入Vue：import Vue from 'vue';
- vue构建发布版本时有两类：
  - runtime-only：代码中不能有任何的template，因为没有编译template的代码，如果需要编译，需要在webpack.config.js文件中配置resolve: {alias: {'vue$': 'vue/dist/vue.esm.js'}}
  - runtime-compiler：代码中可以有template，因为compiler可以编译template

SPA：单页面富应用 simgle page web application

vue-router：前端路由

### 真实开发中，index.html中的内容一般不会更改，而一般在main.js中添加template

- el挂载的元素，Vue实例的template内容会将其全部替换
- 抽取template作为一个组件，形成一个对象，而在实例中只需要定义template和components
- 进一步将组件对象抽取到js文件中默认导出，在main.js中导入
- 再进一步，组件对象放入vue文件中，vue文件分为三大部分，template、script和style，在script标签中默认导出，在main.js中导入
- 配置vue的loader：npm install vue-loader vue-template-compiler --save-dev
- 修改webpack.config.js配置文件
- vue-loader缺少相对应的插件plugin，修改package.json里的vue-loader版本，改为13.0.0，然后在命令行重新安装npm install
- 再定义一个子组件，默认导出，在App.vue中导入，（导入时可在webpack.config.js文件的resolve中配置extensions，可省略文件拓展名），再注册组件，最后在template中使用组件（可用单标签），然后页面渲染

### Plugin是webpack中另一个核心

插件，通常对于现有架构进行拓展

- webpack的插件，就是对webpack现有功能的拓展，比如打包优化，文件压缩
- loader是转换某些类型模块，是转换器
- plugin是对webpack本身拓展，是拓展器
- 通过npm安装需要使用的plugins
- 在webpack.config.js中的plugins中配置插件

添加版权声明的plugin：

- const webpack = require('webpack')

- plugins: [

  new webpack.BannerPlugin('最终版权归aaa所有')

  ]

打包html的plugin：

- 将index.html打包到dist文件夹中
- 使用HtmlWebpackPlugin插件，自动生成指定模板的index.html文件，将打包的js文件，自动通过script标签插入body中
- npm install html-webpack-plugin --save-dev
- 安装好后导入和使用
- 修改webpack.config.js配置，取消公共路径，以原来的index为模板template: 'index.html'

js压缩的plugin：

- 项目发布前，对js等文件进行压缩处理
- 使用第三方插件uglifyjs-webpack-plugin，指定版本号和脚手架一致
- 安装好后导入和使用
- 修改webpack.config.js配置
- 丑化压缩会将注释都删掉，所以之前的版权声明是没有的

### 下载配置loader和plugin一定要指定版本号，否则会出现意料之外的错误



### 搭建本地服务器

每一次都要npm run build，太麻烦了，开发效率低，搭建本地node服务器，内部使用express框架，可以让浏览器自动更新（将编译的内容放在内存里而不是磁盘，可以做到快速响应），最后确定更新后再执行npm run build，才会将更新内容保存到磁盘里，然后发布到服务器上。

- 安装模块：npm install --save-dev webpack-dev-server@2.9.1
- 在webpack.config.js文件中配置：devServer: {contentBase: './dist', inline: true}

- 在局部调用命令：.\node_modules\.bin\webpack-dev-server
- 或者在package.json内配置"dev": "webpack-dev-server --open"
- 运行npm run dev，自动打开网页
- ctrl+c 终止批处理操作

#### 开发和打包时的配置不同，因此需要抽离部分配置

- 开发和生产抽离（ctrl+A全选，ctrl+C复制）
- 开发和生产时都依赖的东西都放入base.config.js中
- 开发依赖的放入dev.config.js
- 生产依赖的放入prod.config.jd
- 将分离的配置文件进行合并：npm install webpack-merge --save-dev
- package.json配置："build": "webpack --config ./build/prod.config.js", "dev": "webpack-dev-server --open --config ./build/dev.config.js"
- 出口路径需要修改为上一级：path: path.resolve(__dirname, '../dist')
- 注意使用webpackMerge()时，第一个参数是变量，不要添加引号，否则会出现Configuration file found but no entry configured.警告

### 总结

webpack其实就是提供了两个东西：

- loader
- plugin
- 这两个东西帮助前端开发人员节省大量的时间，集成在一个架构内，不需要到处去找好用的工具
- 而webpack里面的东西也有很多不需要我们自己配置，可以利用脚手架来搭建，接下来讲的就是Vue-CLI

# 2021-11-8 选集P91-P94

### Vue CLI（俗称脚手架）

开发大型项目，必然会使用到一个工具Vue CLI。我们必须考虑代码目录结构、项目结构和部署、热加载热更新、代码单元测试等。如果每个项目都要手动完成这些配置工作，效率会很低，所以通常我们会使用一些脚手架工具来完成这些事情。

CLI：Command-Line Interface，命令行界面

- Vue CLi是官方发布vue.js项目脚手架
- 使用vue-cli可以快速搭建Vue开发环境以及对应的webpack配置

Vue CLI使用前提 - Node、Webpack

- Node环境要求8.9及以上

安装Vue脚手架3（安装到全局就可以了）(记得管理员权限运行cmd)

- npm install -g @vue/cli@3.2.1
- 拉取脚手架2的模板
- npm install @vue/cli-init -g
- Vue CLI2初始化项目：vue init webpack my-project

先讲脚手架2，后讲脚手架3

- Vue CLI3初始化项目：vue create my-project

### 浏览器引擎

一般JS代码在运行时先在浏览器编译成字节码，然后浏览器中运行

而谷歌浏览器将JS代码直接编译成二进制代码，大大提高了代码运行效率，其核心就是V8引擎，是用C++写的

### 脚手架组织结构解析一览

相关配置和依赖、node包、开发源代码、静态文件、babelrc、editorconfig（正规公司都有）、gitignore、postcssrc、index.html、package.json、package-lock.json、README.md

# 2021-11-9 选集P95-P97

## 一、Vue CLI（二、Vue-Router 三、Vuex 四、网络请求封装（axios））

### ESlint

- vscode中，一修改代码，立即就会重新编译，原因是vscode设置了自动保存功能，取消即可：File ->Auto Save。

- JS规范加不加分号，争议很大。

- 配置了ESlint但是不想使用，可以再config的index.js文件中配置：useEslint：false

### runtime-compiler和runtime-only的区别：

- 代码区别主要是在main.js中：compiler中的组件先导入import，注册components，再在template中使用；而runtime-only中是有导入，但是没有注册，也没有在template中使用，只有一个render函数，传入了一个h参数，函数返回h(App)
- runtime-compiler
  - 1、模板template传给Vue实例的options，做个保存
  - 2、模板会被解析成抽象语法树ast（abstract syntax）
  - 3、ast再被compiler（编译）成Vue实例的render函数
  - 4、通过render函数将模板渲染成虚拟DOM树（virtual dom）
  - 5、虚拟DOM树再渲染成真实DOM（UI）
- runtime-only（1、性能更好；2、代码量更少（少6KB）；3、实际开发中选择runtime-only）
  - 1、render函数将组件渲染成虚拟DOM（template最终不存在）
  - 2、虚拟DOM渲染成真实DOM
- render函数
  - function(createElement) {}
  - 1、普通用法：createElement('标签', {标签属性},['标签内容'])
  - 2、传入组件对象：render: h => h(App)，这里的App在传入之前已经被解析编译为render函数了，是由vue-template-compiler（在安装vue-loader时一起安装的）解析编译了，没有template

### Vue CLI3

- 基于webpack4打造

- 设计原则是0配置，移除build和config目录
- 提供vue ui命令，提供可视化配置
- 移除static文件夹，新增public文件夹，index.html移动到public中

rc：run command

# 2021-11-9 选集P98-P114

### Vue CLI3查看配置：

- vue ui： GUI 查看配置

- 配置删除了，但并不是真的删除，而是转移到@vue中的cli-service中的lib
- 当前目录下创建vue.config.js：module.exports = {}

### 箭头函数

- 两个参数
- 一个参数：省略小括号
- 多行代码
- 一行代码：省略大括号和return关键字

### 箭头函数中的this

- 什么时候使用箭头函数：将函数作为参数，传到另一个函数中时（高阶函数）
- this的指向：箭头函数中的this，向外层作用域中一层层查找this，直到有this的定义

### vue-router

- 认识路由
- vue-router基本使用
- vue-router嵌套路由
- vue-router参数传递
- vue-router导航守卫
- keep-alive

脚手架2创建项目

### 路由

- 路由是网络工程里面的术语：通过互联的网络把信息从源地址传输到目的地址的活动
- 路由器：
  - 路由：决定数据包从来源到目的地的路径
    - 内网IP地址：192.168.1.110（局域网）
    - 公网IP地址：202.111.23.45（永远不会重复）
  - 转送：将输入端的数据转移到合适的输出端
- 路由表：
  - 路由表本质上是一个映射表，决定了数据包的指向
    - 内网IP和电脑mac地址（类似手机的唯一序列号）一一对应

### 前端渲染和后端渲染

#### 网页发展阶段

- 一开始都是后端渲染jsp(java server page)/php
- url（网址）发送给服务器，服务器解析，通过jsp将网页（html+css+java(作用是从数据库中读取数据，动态放在页面中))传给浏览器，服务器给过来的只有hmtl+css，已经渲染好的网页，这就是后端渲染
- 不同的url对应后端不同的渲染好的页面，用户输入不同的网页，获得不同的页面，这就是后端路由
- 优点：利于SEO的优化
- 缺点：页面模块由后端编写和维护；前端开发需要学习PHP和Java；代码逻辑混合在一起，不利于维护

#### 前后端分离阶段

- Ajax出现，有了前后端分离的开发模式

- 后端只负责提供数据（静态资源服务器，提供API接口服务器)，静态资源服务器提供html+css+js
- 前端Ajax请求数据，js代码渲染到页面
- 浏览器中显示的大部分内容，都是由前端写的js代码在浏览器中执行，最终渲染出来的网页，这就是前端渲染
- 优点：前后端责任清晰，后端专注于数据，前端专注于交互和可视化

#### 单页面富应用阶段SPA

- 在前后端分离的基础上，添加了一层前端路由
- 前端维护一套路由规则
- 整个网站只有一个HTML页面index.html+css+js
- 输入网址，静态资源服务器返回一个html+css+js包
- 前端路由配置映射关系：点击不同的按钮，页面渲染不同的页面内容（一个url对应一个组件）

#### 总结

- 前端渲染：从静态服务器返回的js代码，通过ajax请求数据，然后将数据渲染到页面，展示到浏览器
- 后端渲染：早期服务器中通过java动态获取数据渲染好页面，再直接展示到浏览器中

### 前端路由的核心

- 改变URL，但是页面不进行整体的刷新，也就是不再重新向服务器请求数据

- 1、改变URL的hash值
- 2、HTML5的history模式：pushState({}, '', 'home')（栈结构，先进后出）
  - history.back()
  - history.replaceState({}, '', 'home') 不能返回上一个页面
  - history.go() 传入正负整数，随意跳转某个页面
  - history.forward()

### vue-router基于路由和组件

- 创建router文件夹，index.js文件，导入VueRouter
- 安装插件，通过Vue.use(插件)安装
- 创建路由对象，定义routes，配置路由和组件之间的映射关系
- 导出router对象，挂载到Vue实例
- Vue实例导入，添加router对象

### 使用vue-router

- 创建路由组件

- 配置路由组件和路径映射关系

- 使用路由：

  - router-link（vue-router中注册的组件）标签中的to属性
  - router-view标签占位

- 路由默认路径{

  path: '',

  //路径为空是重定向为首页

  redirect: '/home'

  }

- 改变默认的哈希模式为history模式：mode: 'history'

- router-link补充其他属性：

  - to="/home"，指定跳转路径
  - tag="button"，指定渲染标签
  - replace，指定浏览器后退键不能返回
  - router-link-active，类名添加样式

- **通过原生标签和监听事件代替router-link进行组件跳转**

  - this.$router.push('./home')

- 动态路由：

  - router文件里的index.js里routes配置：{

    path: '/user/:userId',

    component: User

    }

  - App.vue文件配置：data() {

    return {

     userId: 'lisi'

    }

    }

  - <router-link :to="'/user/'+userId"

  - $route和$router

    - $route，哪个组件对象处于活跃状态就是谁
    - $router，路由对象
    - 通过this.$route.params.userId获取url中的用户信息

### 路由的懒加载

懒加载：用到时再加载。

打包构建应用时，JS包会非常大，影响页面加载，需要把不同路由对应的组件分割成不同的代码块，当路由被访问时才加载对应的组件，这样更高效

npm run build

- 业务代码会被打包到app.js中
- 第三方代码会被打包到vender.js中
  - vue/vue-router/axios/betterScroll
- 为打包代码作底层支撑的代码放到manifest.js中

懒加载做法：

- 将路由对应的组件打包成一个个的js代码块
- 只有在这个路由被访问到的时候，才加载对应的组件
- 写法：ES6中，组织Vue异步组件和Webpack的代码分割
  - const Home = () => import('../components/Home.vue')
- 以后的路由写法都需要用懒加载

### 路由的嵌套

嵌套路由是常见的功能，在路径下面嵌套子路径，能访问访问其他页面

实现的两个步骤：

- 创建对应的子组件，在路由映射中配置对应的子路由

  - {

    path: '/home',

    component: Home,

    children: [

     { path: 'news', component: HomeNews },

     { path: 'message', component: HomeMessage },

    ]

    },

- 在组件内部使用router-view标签

  - router-link to="/home/news"新闻/router-link
  - router-view

### 传递参数

Profile（我的档案）命名的问题

路由跳转时传递消息：

- params类型：
  - 配置路由格式：/router/:id
  - 传递方式：在path后面跟上对应的值
  - 传递后形成的路径：/router/abc
  - 页面中获取数据：$route.params.id
- query类型：
  - 配置路由格式：/router，普通配置
  - 传递方式：对象中使用query的key作为传递方式
  - 传递后形成的路径：/router?id=abc
  - 页面中获取数据：$route.query
- url的组成：协议scheme://主机host:端口port80/路径path?查询query

### $router和$route区别

在控制台打印之后可以分析：

- $router：是index.js导出的vue-router实例，里面有很多属性和方法，有push\replace等方法
- $route：是配置的当前活跃的路由对象，里面有很多属性，包括params和query

由来：所有的组件都是Vue的实例

# 2021-11-10 选集P115-P118

### 导航守卫

为了监听路由跳转的过程，在监听函数里面做一些事情，导航守卫就是监听这一跳转的过程。

使用全局导航守卫，动态修改页面标题：

- 前置钩子guard，跳转前回调：

- router.beforeEach((to, from, next) => {

  document.title = to.matched[0].meta.title

  next()

  })

meta，元数据，描述数据的数据；metaclass，元类

### 导航守卫补充（知道有这些东西）

- 后置钩子hook，跳转后回调，不需要主动调用next()函数：
- router.afterEach()
- 导航守卫，被称为全局守卫，除此之外，还有：
  - 路由独享守卫：在路由配置上直接定义beforeEnter守卫，与全局前置守卫的方法参数是一样的
  - 组件内的守卫：在路由组件内直接定义路由导航守卫：beforeRouteEnter、beforeRouteUpdate、beforeRouteLeave

### keep-alive

离开组件时，想要保留组件离开时的状态，就要使用keep-alive

- keep-alive是Vue内置的组件，使被包含的组件保留状态，避免重新渲染

- keep-alive包含router-view之后，跳转路由不会销毁组件，回到路由不会重新创建组件，而如果不包裹跳转就会导致销毁创建

- 组件路由内有子路由，想保存跳转子路由的状态：

  data() {

   return {

    message: 'hello',

    path: '/home/news'

   }

  }, 

  activated() {

    // console.log('activated');

    this.$router.push(this.path).catch(err => {})

   },

   beforeRouteLeave(to, from, next) {

    console.log(this.$route.path);

    this.path = this.$route.path;

    next()

   }

- 如果没有keep-alive组件包裹，那么activated()函数和deactivated()函数不会生效

- keep-alive有两个非常重要的属性来满足路由跳转的需求

  - include：字符串或正则，只有匹配的组件会被缓存
  - exclude：字符串或正则，任何匹配的组件都不会被缓存
  - 属性值不要加空格，仅输入组件路由名字即可

# 2021-11-10 选集P119-P124

### TabBar组件

一个大组件，包含多个小组件，小组件包含插槽动态获取数据

- 大组件Tabbar先定义好样式布局，导出到App.vue，给个插槽提供拓展

- 小组件TabBarItem再定义好样式布局，导出到App.vue，给个插槽提供拓展
- App.vue使用组件标签
- 如果要给插槽设置属性，不管是静态属性还是动态属性，最好都给插槽包裹一个div，在div中设置属性

### TabBar结合路由

点击TabBar组件，页面显示对应的路由组件，越往上层越抽象，越往下层越具体

- 配置vue-router
- 新建views文件夹，定义不同的组件
- 配置映射关系
- 组件item监听点击事件跳转路由
- 组件item样式利用已定义好的点击事件，用indexOf方法判断path是否相同返回布尔值，从而决定样式是否应用
- 字体颜色动态决定，通过props获取参数，定义计算属性返回参数值，动态赋值给元素

### 从App.vue抽取MainTabBar.vue

- 剪切粘贴
- import文件
- 修改引用的图片和import文件路径

# 2021-11-10 选集P125-P135

Promise、Vuex、网络请求封装axios、项目开发

### 给路径起别名：

- 在webpack.base.config.js文件中的resolve配置alias

- 脚手架2：

- alias: {

  '@': resolve('src'),

  'assets': resolve('src/assets'),

  'components': resolve('src/components'),

  'views': resolve('src/views')

  }

- DOM中使用路径的别名要加波浪号：src="~assets/img/tabbar//profile.svg"

### Promise

promise是异步编程的一种解决方案

- 执行网络请求
- 封装网络请求函数，传入另外一个参数，在数据请求成功时，将数据通过传入的函数回调出去
- 当网络请求非常复杂时，会出现回调地狱
  - 回调地狱代码难看而且不容易维护
  - 期望更加优雅的方式进行这种异步操作
- Promise可以用非常优雅的方式解决这个问题
- 代码结构：链式编程，将网络请求的代码和请求来的数据处理代码进行分离
  - 网络请求放在promise函数里面，同时放一个resolve函数
  - 处理操作放在promise函数之后的then方法里面
  - new Promise().then().then().then()
- 什么情况使用：有异步操作时，使用Promise对异步操作进行封装
- new => 构造函数（1、保存一些状态信息，2、执行传入的函数） => 执行回调函数时，会传入两个参数，resolve和reject，本身也是函数 => 在网络请求函数中放入resolve()，并放入数据 => 在promise函数之后链式调用then()方法，在then()方法中放入处理代码 => 调用成功使用resolve()，调用失败使用reject() => 调用失败链式调用catch()方法，放入错误箭头函数

### Promise三种状态

- 给异步操作包装一个Promise
- 异步操作之后会有三种状态：
  - pending：等待状态，正在进行网络请求
  - fulfill：满足状态，请求数据成功或主动回调resolve，会处于该状态，并回调.then()
  - reject：拒绝状态，请求数据失败或主动回调reject，会处于该状态，并回调.catch()

### Promise的第二种写法

- 除了链式调用then()和catch()之外，还可以只在then()方法中传入两个参数
- 两个参数都是函数，第一个函数处理resolve之后的数据，第二个函数处理reject之后的信息

### Promise的链式调用

- resolve函数对应.then()方法，reject函数对应.catch()方法
- 省略Promise.resolve简写

### Promise.all

需求本身依赖两个网络请求，如果只有一个网络请求成功，则无法满足需求。

如果确定网络请求成功或失败？

- 定义一个函数，在网络请求中调用这个函数，只要这个函数回调成功，说明这个网络请求成功

iterator可迭代的，可遍历的

用法：

- 将两个网络请求包装到Promise.all()方法中，网络请求作为数组项
- 在all()方法外调用then()方法，传入一个箭头函数，打印获取结果

### Vuex

官方解释：

- 专为Vue.js应用程序开发的状态管理模式
- 采用集中式存储管理应用的所有组件状态，以相应的规则保证状态以可预测的方式发生变化
- Vuex集成到Vue官方调试工具devtools extension，提供诸多高级调试功能

其实就是一个状态管理工具：

- 可以理解为需要多个组件共享的变量全部存储在一个对象里面
- 然后将这个对象放在顶层的Vue实例中，让其他组件可以使用
- Vuex也是响应式的，自己利用原型链封装的对象不能做到响应式

只有需要共享的变量才会由Vuex管理，并不是所有都需要管理

- 用户的登录状态token令牌、用户名称、头像、地理位置等
- 商品的收藏、购物车中的物品
- 这些状态信息，可以放在统一的地方，进行保存和管理，而且也是响应式的
- Talk is cheap，Show me the code （linus大神）

单页面状态管理：

- State：状态，即data函数里定义的变量counter
- View：模板，显示在页面上的counter
- Actions：行为，点击事件，影响counter

多界面状态管理：

- Vuex提供大管家，全局单例模式
- 将共享的状态抽取，交给大管家统一管理
- 每个视图按照规定好的规定，进行访问和修改

Vuex是一个插件，需要下载和安装使用

- npm install vuex --save
- Vue.use(Vuex)
- 新建文件夹store/index.js
- 导入 -> 安装 -> 创建对象（定义实例） -> 导出 -> mainjs导入

### Vuex状态管理图例

- State render到Vue Component，组件dispatch Actions，行为commit提交给Mutations，这种转变再去mutate改变State状态
- 而这种循环中的三个环节：State、Actions和Mutations被称为Vuex，而要记录跟踪这种循环，可使用Devtools插件
- 只要需要修改State状态，只能通过Mutations来改
- Mutations推荐使用同步操作
- Actions中使用异步操作（发送网络请求）-> Backend API
- Vuex对象中仅有常用的5个对象：
  - state
  - mutations
  - actions
  - getters
  - modules
- 使用步骤：
  - 1、提取公共的store对象，保存多个组件中共享的状态
  - 2、将store对象放置在new Vue对象中，保证所有组件都可以使用
  - 3、在其他组件中使用store对象中保存的状态即可
    - 通过this.$store.state属性的方式访问状态
    - 通过this.$store.commit('mutations中方法')来修改状态

State单一状态树，single source of truth，单一数据源

- 学习档案，社保记录，公积金，婚姻，户口，医疗，文凭，房产记录
- 信息分散在不同的地方，办理业务时需要去不同地点打印盖章
- 低效、不方便管理、很难维护
- 开发中类似
- Vue推荐只使用一个store对象进行管理，只挂载一个store到Vue实例中，用最直接的方式找到某个状态的变化，便于后期维护、调试和管理

### Vuex getters

有时需要从store中获取一些state变异后的状态，可以在getters中定义函数处理，类似于Vue实例中的computed

- 1、定义的方法中若需要store中的state，需要在方法中传入参数state
- 2、定义的方法中若需要getters中其他方法的协助，也可以在方法中传入参数getters
- 3、如果用户自己输入参数，可以在getters中定义一个方法，方法中返回一个函数，这个函数的形参对应用户输入的实参

### Vuex mutations

Vuex的store状态的更新唯一方式：提交Mutation

- Mutations包括两部分：字符串的事件类型和回调函数。回调函数的第一个参数是state

- 通过mutation更新：

  increment：function() {

  ​	this.$store.commit('increment')

  }

- 有点像子组件向父组件发射事件：this.$emit(' ')

- 如果在commit时需要传入参数：

  appAddCount(count) {

     this.$store.commit('addCount', count) 

    }

  store接收时：

  addCount(state, count) {

     state.counter += count

    }

- 通过mutations更新数据的时候，我们希望携带一些额外的参数

  - 参数被称为时mutation的载荷Payload
  - 参数也就是载荷通常是一个对象
  - commit中如果传入的是一个对象，mutation接收的第二个参数payload也是一个对象

# 2021-11-12 选集P136-P147

### Vuex响应式原理

mutations响应规则

- 提前在store初始化好所需的属性，这些属性都会被加入Vue响应性系统（Dep -> [Watcher] 监听属性变化 ，当属性变化时，会通知界面中用到该属性的地方刷新）
- Vue.set()方法可以添加新的属性到响应性系统
- Vue.delete()方法可以删除属性，做到响应式
- 查找资料最好不要用百度查询

mutations常量类型

- Mutations中的事件字符串统一到常量定义文件mutations-types.js

mutations同步函数

- mutation中的方法必须是同步方法
- 使用devtools时可以捕捉mutations快照
- 如果mutation中方法是异步的，尽管界面更新，但是devtools无法捕捉变化
- 如果希望进行异步操作，需要在actions中进行

### Vuex actions

actions类似mutations，主要用于替代mutations进行异步操作

- actions方法中传入的默认参数是context（上下文），可以理解为store

- 修改state的唯一途径是mutations，所以actions方法中不能直接修改state

- actions中的方法需要也是需要提交到mutation中来修改state

  - aUpdateInfo(context) {

    setTimeout(() => {

    ​    context.commit('updateInfo')

       }, 1000)

      }

- 而Vue组件中定义的异步操作方法，需要dispatch到actions中的异步方法

  appUpdateInfo() {

     // this.$store.commit('updateInfo')

     this.$store.dispatch('aUpdateInfo')

    }

- 这里控制台一直报错，devtools也没有跟踪变化，界面也未更新数据，百度、stackoverflow、官方文档都看过了，改了方法名也找不出问题，疯掉了

  TypeError: sub is not a function

- 最后听从了弹幕大神的建议，把devtools插件关掉，然后异步操作setTimeout成功了！！！我tm吐了！！！

- actions中return Promise函数，里面用组件传递过来的数据做异步操作，功能完成后，返回给组件，打印信息

### Vuex modules

当state变得臃肿时，可以将store分割成模块，在modules分模块对象之后，又可以定义state、mutations、actions和getters。

- 注意，分割的模块要放在store前面，不然会报错

- 定义和store里一样，例如在模块a中定义，用法：

  {{$store.state.a.name}}

  <button @click="updateName">修改名字

  {{$store.getters.fullname}}

- 模块中的actions commit的是自己模块中的mutations

- 一般模块中的mutations和store中的mutations都不会重名，所以组件中的commit和dispatch都可以直接调用传入方法名，无特殊改变

- 模块中的方法如果需要store中的方法和属性，可以调用context中的rootGetters和rootState

### ES6中对象解构

- const { name, age, height } = obj
- 就算解构属性调转顺序，也是对应的键名获得对应的键值

### Vuex store项目结构

三个层级：

- 1、store文件夹
- 2、index.js、actions.js、mutations.js、getters.js、modules文件夹
- 3、moduleA.js、moduleB.js

Vuex总结规则：

- 1、应用层级的状态（$store.state)应该集中到单个store对象中（index.js)
- 2、提交mutations是更改状态的唯一方法，并且这个过程是同步的
- 3、异步逻辑都应该封装到actions里面

### 网络模块封装

发送网络请求有非常多的方式：

一、传统的Ajax基于XMLHttpRequest（XHR）（编码蛋疼，真实开发很少使用）

二、jQuery-Ajax（要引入jQuery，不再使用）

三、官方Vue1.X推出的Vue-resource（Vue2.0即不再更新维护，不使用）

四、Vue作者推荐axios

### Jsonp

解决跨域访问问题

- 通过script标签帮助请求数据
- 项目部署在domain1.com服务器上，不能直接访问domain2.com服务器资料
- 通过script标签src属性帮助去服务器请求数据，把数据当作javascript函数来执行，执行过程中传入需要的json
- 封装jsonp的核心在于监听window上的jsonp进行回调时的名称

### axios（ajax i/o system)

简介：

- 在浏览器中发送XMLHttpRequests请求
- 在node.js中发送http请求
- 支持Promise API
- 拦截请求和响应
- 转换请求和响应数据
- ...

用法：

- 默认情况下，只传一个参数，是get请求
- 传入methods: post，可做post请求
- 并发请求：axios.all(axios(),axios())
- 全局配置：开发中很多参数都是固定的，可以进行抽取，利用axios的全局配置
  - axios.defaults.baseURL
  - axios.defaults.timeout
- 常见的配置选项：
  - url
  - method
  - baseURL
  - transformRequest
  - transformResponse
  - headers
  - params：{id: 12}和get请求对应： 查询对象
  - data: {key: 'aa'}和post请求对应 ： 请求体

### axios实例和模块封装

- 服务器并发量高时，即有很多网络请求时，公司会使用多个服务器

- 用户面向代理服务器，用nginx服务器部署

- 当数据不在同一个服务器，而是在多个服务器时，前端不能设置全局baseURL
- 只要是引用第三方工具，不要在每个组件都对其依赖（建立中间层）
  - 如果某天第三方工具不再使用，修改的时候就会很麻烦，要加班
  - 因此单独封装一个文件引用第三方工具，所有组件面向这个封装文件
  - 这样如果第三方工具修改，我们只需要修改一个文件就可以了

### axios拦截器

用于我们在上发送每次请求或者得到回应后，进行对应的处理

四种拦截：instance.interceptors

- 请求成功/失败：拦截后一定要把config返回回去，否则会请求失败

  instance.interceptors.request.use(config => {

    console.log(config);

    return config

   }, err => {

    console.log(err);

   })

- 响应成功/失败：

  instance.interceptors.response.use(res => {

    console.log(res);

    return res.data

   }, err => {

    console.log(err);

   })

请求拦截的作用：

- 1、如果config中的一些信息不符合服务器要求，可以拦截更改
- 2、每次发送网络请求时都希望在界面显示一个请求的图标（转圈圈动画）
- 3、某些网络请求（登录必须携带token），必须携带特殊信息，否则跳转到登录页面

响应拦截的作用：

- 1、拦截之后返回data出去

# 2021-11-12 选集P148-P152

### 项目开发

项目创建、github托管

- git clone url
- 复制项目
- git status
- git add .
- git commit -m "初始化项目" 提交到本地
- git push 提交到github

### 目录结构、CSS文件等

- 1、划分目录结构：assets:img/css，common，components:common/content，network，router，store，views

- 2、引用了两个CSS文件（统一风格，做基本设置）

- 3、脚手架3配置别名

  - 新建vue.config.js文件

  - 但其实没必要起别名，因为配置文件内部有配置

    - *node_modules -> @vue -> cli-service -> webpackconfig.js*

    - .alias

      ​    .set('@', api.resolve('src'))

  - ‘@’： ‘src'，这个就够了

  - 统一风格文件：.editorconfig

  - 脚手架或许没有，但是项目必须有，否则开发人员每个人不同风格导致项目乱七八糟

### 项目模块划分

- tabbar -> 路由映射关系

# 2021-11-13 选集P153-P158

### 小图标修改及路径问题

小图标修改

- html页面修改link标签的href属性，替换原来的图片
- <%= BASE_URL %> 动态获取当前文件所在路径，打包到dist文件夹后不会有这种语法

### 首页导航栏封装和使用

- 新建NavBar.vue
- 给个div，包裹三个slot，左中右
- 每个slot被div包裹并给定样式
- flex布局，给父元素display：flex，子元素左右给定宽度，中间给flex：1占领剩余宽度
- 定义好组件后引入Homt组件，使用NavBar标签，放入内容，设定样式

### 请求首页的多个数据

- 新建request.js文件，安装axios插件，导出封装的request函数
- 新建home.js文件，导入request，导出getHomeMultidata函数
- 层层封装，利于以后的管理维护，如果以后axios不再更新维护，更改第三方框架时只需要修改一个文件即可，耦合度低，不会加班
- 函数调用，压入函数栈，函数中的数据变量都是存在的，但是函数调用结束，会弹出函数栈，函数中所有数据变量都会被释放，所有函数执行完，内部所有变量都被回收，因此如果需要保存数据，在函数内部将数据保存到本地变量
- 垃圾回收机制：数据没有被引用，就会被垃圾回收
- 获取数据，定义组件变量，保存数据

### 轮播图展示

- 学习阶段，最好自己封装一个轮播图
- 轮播图作为一个小功能可以作为子组件HomeSwiper导入进Home组件中
- 在Home组件使用HomeSwiper组件时注意在元素上将变量绑定给子组件
- 子组件通过props获得数据，将数据展示到轮播图里
- 学会封装思想，不要将一坨一坨代码写到一块

### 推荐信息的展示

- 推荐信息模块也可以作为子组件HomeRecView导入进Home组件
- 在Home组件使用HomeRecView组件时在元素上绑定recommends变量
- 子组件通过props获得数据，定义recommends类型和数据
- 包裹一个div，给div样式，div包裹a连接，a链接包裹img和div文字

### 总结

- Promise，用Promise包装异步操作，resolve和reject对应then和catch
- Promise链式调用多种形式

- Promise.all()
- Vuex状态管理
- Vuex中的state由mutations修改
- Vuex核心概念：
  - state：单一状态树
  - getters：传参数
  - mutations：提交类型和方式commit，传参，响应式，常量
  - actions：异步操作dispatch
  - modules
- Vuex目录组织方式：抽离文件
- 网络请求选择
- axios基本使用和相关配置
- axios创建实例和封装
- 项目开发
  - 划分目录结构
  - 引入两个css文件
  - vue.config.js和.editorconfig
  - 项目的模块划分：tabbar->路由映射
  - 首页开发：
    - navbar封装
    - 网络请求，封装，中间层，管理维护
    - 轮播图
    - 推荐信息

# 2021-11-16 选集P159-P169

### 首页开发

若组件内只是文字不一样，就没必要使用插槽，可以定义数组变量，让父组件传递数据，根据数据来v-for循环渲染出元素。

注重代码写法，父组件导入文件时分类排列：

- 函数方法导入
- 公共组件导入
- 子组件导入

一个css属性实现tab-control吸顶功能：

- .tab-control {

​           position: sticky;

​           top: 44px;

​        }

- 在未达到44px时，position属性默认未sticky，当位置达到44px，浏览器会将position改变为fixed，但很多浏览器不支持这个属性，但是移动端基本支持这个属性

### 请求数据、页面展示

- 定义对象数据，分类，分页
- 定义项目公共组件：GoodList，GoodListItem
- 通过props对象传递数据
- GoodList负责v-for循环数据
- GoodListItem负责每个小块数据的样式展示

### 安装使用better-scroll

原生滚动在移动端非常卡顿，因此需要使用better-scroll

- 导入BScroll
- 给div添加wrapper类，给内容添加content类
- 在钩子函数mounted里面定义实例，传入参数'.wrapper'

### better-scroll基本使用

- 引用bscroll文件

- 创建bscroll对象，传入DOM对象且wrapper必须有固定高度
- 传入额外属性，在特殊情况下使用
  - probeType：3，实时监听滚动
  - click：true，监听点击事件，button元素默认有点击事件，其他元素需要添加此属性
  - pullUpLoad：true，上拉加载更多
- 监听事件：bscroll.on(' ', () => {})
- 上拉加载更多只能执行一次，因此需要添加finishPullUp()函数来执行更多次上拉加载更多

### 获取组件

不能在created()函数里面获取元素，需要在mounted()函数里，即组件挂载完后可以获取

### better-scroll在Vue中使用

better-scroll是第三方库，不建议直接在Home组件中使用，而应该封装到一个文件中，其他组件面向这个文件编程，形成低耦合。

这样做是为了如果以后框架或第三方库不再维护更新，只需要面对一个文件进行修改，而不用去对这个第三方库形成依赖的组件中一个个去修改。

在组件中直接使用第三方库，是一件非常危险的事情。

### better-scroll的封装和使用

- 导入scroll组件，使用scroll标签
- 自定义高度

封装：

- 获取DOM时不建议使用document.querySelector('.wrapper')，因为可能其他元素也会使用wrapper这个名词作为类，到时候获取元素时会获取错误
- 使用ref来获取（之前使用方法是可以在父组件中获取子组件：this.$refs.refname获取组件对象），普通元素也可以绑定ref，通过this.$refs.refname获取元素对象

vh：viewpor height 视口高度

使用：

- 设置content高度时，可以使用子绝父相定位

- \#home {

  padding-top: 44px;

  height: 100vh;

  position: relative;

  }

- .content {

  /* height: 300px; */

  overflow: hidden;

  

   position: absolute;

   top: 44px;

   bottom: 49px;

   left: 0;

   right: 0;

  }

### BackTop组件封装和使用

设置样式：

- position为fixed，给具体的right和bottom，给宽高设定大小

定义功能：

- BackTop组件发生点击事件
- Scroll组件发生滚动
- 可以直接在父组件里的子组件元素上监听事件，但是组件不能直接监听点击，如果需要在子组件元素上监听事件，必须添加修饰符.native
  - .native：监听组件根元素的原生事件
- 监听事件后，调用scroll组件里面的scrollTo方法
- 可以在scroll组件里封装好scrollTo方法，传入参数x，y，time=300，这样当父组件调用时可以直接调用子组件的方法而不是要到scroll里面再去拿

计算机中

- 计算机中没有黑魔法
- 如果有能复现的问题，肯定是代码的错误

# 2021-11-17 选集P170-P172

scroll实例中click属性必须设置为true，组件里的非button元素才有点击事件

### BackTop组件的显示和隐藏

某些组件需要实时监听，某些组件不需要实时监听，因此需要动态设置probeType的属性值，可以提高性能，避免不必要的实时滚动监听

- 通过props传递参数
- 定义probeType变量
- 这样封装的Scroll组件可以根据不同情况设置不同参数值

### 封装Scroll组件后遇到的问题

- 在其他组件使用Scroll封装组件的时候，一定要在style标签上设置scoped属性，否则不会滚动
- 动态设置了probeType属性，默认为0是不监听滚动位置，但是如果设置了pullUpLoad为true，这里相当于自带了probeType为3，那么也会对滚动位置进行实时监听

### 设置BackTop组件显示和隐藏

- Scroll组件监听滚动事件，通过

  this.scroll.on('scroll', (position) => {

     this.$emit('scroll', position)

    })发送自定义事件和位置参数

- Home父组件接收自定义事件和参数@scroll="contentScroll"，利用参数对子组件BackTop进行显示和隐藏

- 将position的Y值和设定的值进行对比，控制显示和隐藏

- 定义isShowBackTop，默认值为false，v-show为false是元素隐藏，将position里的Y值和设定值对比，当对比值为true时，v-show显示

### 上拉加载更多

- 并不是每个组件都需要监听上拉事件，因此也将上拉属性动态赋值

- 老规矩，Scroll组件监听事件，通过

  this.scroll.on('pullingUp', () => {

     this.$emit('pullingUp')

    })发送自定义事件

- Home父组件接受自定义事件，利用此事件请求数据

- 注意此事件只触发一次，因此需要添加this.scroll.finishPullUp()来执行下一次上拉加载更多

### BScroll组件BUG

- 一开始BScroll根据渲染到页面的内容规定死了可滚动区域
- 但是项目是动态获取网络数据，图片是异步加载，BScroll计算可滚动区域时未包含图片，可滚动区域不会实时改变
- 因此图片加载完毕后，需要刷新this.$refs.scroll.scroll.refresh()，可以重新计算可滚动区域

### git常用命令

- 添加当前目录的所有文件到暂存区git add . 

- 提交暂存区到仓库去git commit -m [message]

### 总结

- FeatureView 独立组件封装

- TabControl 独立组件封装 props传值 flex布局 选中tab变色和border-bottom 使用currentIndex
- 首页商品数据的请求：
  - 分三类保存数据，定义对象数据；
  - 发送数据请求，定义网络请求函数，传入参数；
  - 获取数据后push(...res)保存到本地；
- 商品数据的展示
  - 封装GoodsList.vue组件，通过props传值，传哪个值由点击index决定
  - 封装GoodsListItem.vue组件，通过props传值，取出数据，使用基础标签展示到页面
- 对滚动进行重构：better-scroll
  - 学会使用，注意结构：wrapper-content-内容，监听滚动probeType，bscroll.on('scroll', (position)=>{})；上拉加载pullUpLoad，bscroll.on('pullingUp',()=>{})；监听点击click，button默认点击监听，其他元素不可以
  - 在vue中使用better-scroll
    - 封装better-scroll文件scroll.vue
    - 动态传入参数，面向scroll.vue文件编程
    - 父组件在子组件元素上添加属性值传入参数，scroll.vue组件$emit发射自定义事件和参数给父组件
- 回到顶部BackTop
  - 对BackTop.vue组件进行封装
  - 监听组件的点击，添加修饰符@click.native
  - 回到顶部，scroll对象，this.$refs.scroll.scrollTo(0,0)
  - BackTop组件的显示和隐藏，isShowBackTop属性，默认false，监听滚动，拿到滚动位置，position.y与设定值比较

# 2021-11-17 选集P173-P177

### 滚动区域的BUG分析和解决

- better-scroll滚动的BUG：一会儿能拖动，一会儿不能拖动
- Scroll.vue区域滚动区域高度计算时，图片未加载；图片加载后，高度比之前的计算高出很多，但是滚动区域不会实时计算
- BScroll.scrollerHeight为计算出的滚动区域高度，根据content中的子组件内容高度决定，刚开始没有将图片计算在内，这个数值不正确
- 后来图片加载后有了新的高度，但是BScroll.scrollerHeight属性并没有进行更新，因此滚动出现了问题be

### 如何解决

- 监听每一张图片是否加载完成，只要有一张图片加载完成，执行一次refresh()

- 如何监听图片加载完成？

- vue中在img元素上添加@load="imageLoad"，再定义imageLoad()

- 监听之后调用this.scroll.refresh()方法

- 但是由于这是在Home组件中分别调用的两个子组件Scroll.vue和GoodsList.vue，而GoodsList.vue调用GoodsListItem.vue

- 在这种场景下，可以使用Vuex作为中间通信，但是在这里使用事件总线

- 涉及到非父子组件的通信，选择事件总线

  - 1、子组件发射事件this.$bus.$emit('aaa'，参数)
  - 2、父组件接收事件this.$bus.$on('aaa', () => {})

- $bus是空的，undefined，因此需要到Vue原型上去定义这个东西Vue.prototype.$bus = new Vue()

- 孙子组件监听图片加载完事件发射出去

  - @load="imageLoad"

  - methods: {

    imageLoad() {

     this.$bus.$emit('itemImageLoad')

    }

    }

- 父组件接收事件，获取其他组件对象执行refresh()方法

  - ref="scroll"

  - created() {

    this.$bus.$on('itemImageLoad', () => {

    this.$refs.scroll.refresh()

    })

    }

### refresh函数找不到的报错处理

- 在Scroll组件的methods里，对于scrollTo方法和refresh方法，添加一个前提判断，即需要this.scroll存在，具体代码为：

- methods: {

  // 返回顶部方法

  scrollTo(x, y ,time=300) {

   this.scroll && this.scroll.scrollTo(x, y, time)

  },

  refresh() {

   this.scroll && this.scroll.refresh()

  }

 }

- 如果仍然存在报错，Error in event handler for "itemImageLoad": "TypeError: Cannot read property 'refresh' of undefined"

  - 在Home.vue里，在调用refresh()方法前面，添加this.$refs.scroll判断

    this.$bus.$on('itemImageLoad', () => {

       this.$refs.scroll && this.$refs.scroll.refresh()

      })

  - 在App.vue里，给router-view组件添加keep-alive包裹(这种解决方法几乎不用)

- 最终修改：不要在created()函数里去获取DOM元素，也就是说监听item图片完成调用refresh函数不要在created()函数里使用，而是应该放在mounted函数里面监听调用函数；但是还有报错，还是要添加前置判断this.$refs.scroll &&

### 刷新频繁的防抖函数处理（经常使用）

例子：输入框输入关键字向服务器发送查询请求；

对于refresh非常频繁的问题，进行防抖操作

- 防抖debounce/节流throttle
- 防抖函数起作用的过程：
  - 如果直接执行refresh，那么refresh函数会被执行30次
  - 将refresh函数传入到debounce函数中，生成一个新的函数，也就是debounce包裹住了refresh函数
  - 当图片频繁加载时，refresh函数本来延迟500毫秒执行但是又被不断清除，直到最后一次延迟执行，图片没有加载了，refresh函数终于可以执行了
  - 防抖函数，抖动就是执行的意思，防止抖动就是防止持续多次的执行

### 哈哈哈哈哈

- 同步优先，异步靠边，回调垫底

### 上拉加载更多

- 子组件监听事件，发出事件
- 父组件监听自定义事件，实现自定义方法。调用封装函数，添加finishPullUp方法

### tab-control吸顶效果

- 获取tab-control的offsetTop：距离上方或父组件的位置
- 所有的组件都有一个属性$el，用于获取组件中的元素
  - this.$refs.tabControl.$el
- 但是这里获取的offsetTop不一定是准确的
  - 没有包含图片撑起来的高度
  - 有些图片加载快，有些图片加载慢，拿到的值可能很小
  - 要等图片加载完之后，拿到最终的offsetTop
- 判断滚动到多少时，开始有吸顶效果

# 2021-11-18 选集P178-P179

### tab-control吸顶效果

#### 获取tabControl的offsetTop

- 所有的组件都有一个属性$el：用于获取组件中的元素，这里this.$refs.TabControl.$el.offsetTop获取tabControl的offsetTop
- 但是这里获取的offsetTop值不一定准确，需要等待图片加载完毕之后拿到最终的offsetTop才是准确的
- 动态布局，图片会经常影响offsetTop，需要监听图片组件中监听load事件，发送事件给父组件，父组件再直到图片加载完毕后，去获取offsetTop值
  - 让子组件图片加载事件只发射一次，可以定义一个flag，flag为true，执行一个发射事件后，将flag改为false，这样就只执行一次发射
- 获取到offsetTop后，保存到本地设置的变量tabOffsetTop

#### 监听滚动，动态的改变tabControl的样式

- 定义布尔值变量，由position.y和tabOffsetTop对比得到布尔值
- 给tabControl组件动态添加class，是否添加由布尔值决定
- 定义class样式
- 但是这种方法行不通
  - 商品内容会突然间上移
  - tabControl虽然设置了fixed，但是也随着better-scroll一起滚出去了
- 而是用另外一种魔术的手法
- 复制一个tabControl组件放置在home-nav组件下面
- 考虑到内容是由better-scoll来包裹，而home-nav组件就没必要脱标了，取消home-nav组件的脱标，两个组件挨在一起
- 给新的tabControl一个相对定位，当页面滚动到特定位置时显示，没有到特定位置就隐藏，这里使用v-show

### Home离开时记录状态和位置

路由管理的组件离开时会销毁destroyed

1.让Home不要随意销毁

- keep-alive包裹router-view

2.让Home中的内容保持原来的位置

- 离开时，保存一个位置信息saveY

- 进来时，将位置设置为原来保存的位置saveY

- 这里要使用两个钩子函数activated和deactivated，data中定义saveY为0，Scroll组件中定义一个获取y位置的方法

- getScrollY() {

  return this.scroll ? this.scroll.y : 0

  }

- Home组件中定义两个钩子函数，在钩子函数里进行操作，记得要refresh，不然better-scroll会出现各种不可预测的bug问题

- activated() {

  this.$refs.scroll.refresh()

  this.$refs.scroll.scrollTo(0, this.saveY, 0)

  },

  deactivated() {

   this.saveY = this.$refs.scroll.getScrollY()

  },

# 2021-11-19 选集P180-P181

### 跳转到商品页并携带商品id

- 新建detail组件，路由配置，添加动态参数/detail/:id
- item组件监听点击事件，跳转路由到detail组件，传递参数
- detail组件定义id属性，在created钩子函数中获取id（其实觉得弹幕更有道理，在activated钩子函数中获取合理，在created中获取，如果设置了keep-alive，只能获取一次

### 详情页-导航栏封装

- 详情页导航栏有点复杂，因此在detail组件中定义子组件DetailNavBar，在子组件中导入封装好的NavBar
- 在子组件中使用插槽，在center插槽中循环遍历title数组，监听点击事件，动态添加颜色样式，flex布局
- 在left插槽中添加返回图标，监听点击事件，放回上一页

# 2021-11-22 选集P185-P188

### 详情页-加入滚动的效果Scroll

- 详情页完全盖上tab-bar组件：相对定位，z-index：9，背景颜色
- 详情页内容被scroll组件包裹，设置计算高度calc(100% - 44px)，和背景颜色，设置父元素100vh视图固定高度
- 详情页导航不随scroll滚动，设置相对定位，z-index：9，背景颜色

### 详情页-商品详情数据展示

- 简单的数据不用定义类封装，直接获取传值即可
- 所有图片都加载完后，进行一次回调，发射图片加载完毕事件，添加判断条件，每执行一次回调函数，counter+1，最终结果和图片长度比较，如果严格相等，那么就发射事件，如果不相等，说明图片未加载完毕，那么就不发射事件
- 用watch监听属性变化，一旦图片数量发生变化，就获取图片长度

### 详情页-商品参数信息、推荐的展示

- 网络请求中定义class GoodsParam
- 导入类，new，传入数据，展示

### 内容回顾

- 1.解决首页中可滚动区域的问题：计算滚动高度，监听图片加载，执行refresh()
- 2.非父子组件通信，选择事件总线：bus，Vue.prototype.$bus = new Vue()
- 3.refresh调用频繁，进行防抖操作，定义导入防抖函数debounce

- 4.上拉加载更多功能，在scroll中监听上拉事件，发射事件，首页监听，定义loadMore函数，根据当前页数请求更多页数据
- 5.tabControl吸顶效果：滚动到指定位置，获取位置offsetTop

- 6.复制一份tabControl组件，在合适时间显示，其他时间隐藏

- 7.首页跳转时记录位置saveY，deactivated，回到首页时跳转到记录的位置，activated
- keep-alive，exclude=“detail”

# 2021-11-22 选集P189-P198

相同的内容，不同班级，速过一遍

- 点击商品进入详情页
- 首页保持位置状态
- 详情页的导航栏实现
- 请求详情的数据
- 轮播图的实现
- 滚动处理，隐藏tabBar
- 定义类传递子组件数据

### 项目难点：

- 代码如何组织
- 业务逻辑（不要立即动手，先理清逻辑）
- 自己留的bug

### 商品评论信息的展示

- 服务器不会返回标准的时间格式：2019-3-10 11:22:33而是返回一串数字：1535694719
- 不同用户端展示的时间样式不一样，因此需要处理
- 以Unix时间元年为起点，返回对应的时间戳

### 如何将时间戳转化成时间格式化字符串（常用功能）

- 1、将时间戳转成Date对象 const data = new Date(1535694719*1000)
- 2、将date进行格式化，转成对应的字符串
  - date.getYear() + date.getMonth() + 1
- 开发中这个功能太常见：date => FormatString
- fmt.format(date, 'yyyy-MM-dd hh:mm:ss')
  - y: year 年
  - M:Month 月
  - d:day 日
  - h:hours 时
  - m:minutes 分
  - s:seconds 秒
- 正则表达式：字符串匹配 利器（难，规则太多）
  - y+表示1个或多个y
  - y*表示0个或多个y
  - y？表示0个或1个y
- 时间格式化很常用

# 2021-11-25 选集P199-P203

### 商品推荐数据的展示

- 复用子组件GoodsListItem，如果从不同的地方获取数据，添加一个计算属性，return 某某属性 || 某某属性

### 首页和详情页监听全局事件和Mixin的使用

- 离开首页时，取消全局事件总线的监听

- ```js
  itemImgListener: {}
  mounted() {
      this.itemImgListener = () => {
          newRefresh()
      },
      this.$bus.$on('itemImgLoad', this.itemImgListener)
  }
  deactivated() {
      this.$bus.$off('itemImgLoad', this.itemImgListener)
  }
  ```

- 而在详情页中，因为详情页没有keep-alive，因此没有deactivated钩子函数，而应该使用destroyed生命周期函数

- Home组件和Detail组件里面有一些相同的代码，可以抽取，对象里面重复代码，需要使用混入，mixin，减少组件之间代码重复问题

- ```
  import { debounce } from "./utils";
  
  export const itemListenerMixin = {
    date() {
      return {
        itemListenerMixin: {}
      }
    }
    mounted() {
      let newRefresh = debounce(this.$refs.scroll.refresh, 100)
      this.itemImgLister = () => {
        newRefresh()
      }
      this.$bus.$on('itemImgLoad', this.itemImgLister)
    }
  }
  
  import { itemListenerMixin } from '@/common/mixin.js'
  
  mixin: [itemListenerMixin]
  ```

- 组件之间使用重复的代码，可以使用混入mixin，可以提取data，methods，mounted等

  - 1.创建混入对象：const mixin = {}
  - 2.导入到组件对象中：mixins：[mixin]

# 2021-11-26 选集P204-P225

ReactNative -> Flutter 做原生的东西

### 两个tabContrl状态保持一致

- currentIndex保持一致
- 给ref属性获取组件
- 在点击事件中将两个组件的currentIndex = index
- 添加一个if判断是否有值或者将代码定义到mounted里面

### 详情页不能滚动的BUG处理

- 偶然会出现图片加载完后不能滚动的BUG
- 原因是better-scroll中有一个属性scrollerHeight计算高度不太准确
- 监听图片加载完毕后刷新refresh
  - 子组件监听，发射自定义事件
  - 父组件监听自定义事件，调用刷新refresh，用防抖函数包裹

### 点击标题滚到对应内容

标签中使用属性时最好不用驼峰法，而是使用短横线分割法，标签中不区分大小写

- 子组件tabBar发射事件，将光标值index作为参数
- 父组件Detail监听事件，根据光标值滚动到对应内容位置scrollTo
- 等组件data值渲染完毕后获取offset值，可以使用this.$nextTick()方法，往里面传入箭头函数，定义空数组，在数组里推入对应组件内容的offsetTop值
- 获取对应内容的offsetTop：this.$refs.param.$el.offsetTop
- 根据最新的数据，对应的DOM已经被渲染，但是图片依然未加载完，目前获取到的offsetTop未包含图片
- offsetTop值不正确的问题，一般都是图片未加载完毕的问题
  - 哪里能获取到正确的offsetTop
  - created()不行，不能获取到元素
  - mounted()不行，不能获取到数据
  - 获取到数据的回调中也不行，DOM未渲染完
  - $nextTick也不行，图片的高度没有被计算在内
  - 图片加载完成后，获取的高度才是正确的✔

### 滚动内容显示对应标题

理清判断条件，获取i值

### 对复杂判断条件分析和优化

空间换时间

### 底部工具栏

封装子组件，给定布局和样式

微调可以使用相对定位

### 详情页的回到顶部

- home.vue和detail.vue回到顶部：mixin

### 点击加入购物车

- 监听点击事件，发射自定义事件
- 监听自定义事件，获取需要展示的信息
- 使用Vuex管理需要在购物车展示的信息

### Vuex中代码的重构

- mutations唯一的目的就是修改state中的状态
- mutations的设计原则是：每一个方法尽可能只完成一件事情
- 在actions中写逻辑代码，commit到mutations中
- 在mutations中写单一的方法，有利于调试跟踪
- 常量抽离，文件结构组织

### 购物车-导航栏实现

- 复用组件NavBar

- 封装一个getter获取添加到购物车的数量

- mapGetters辅助函数

- import { mapGetters } from 'vuex'

- computed: {

  ...mapGetters({

  ​    length: 'cartLength',

    })

  }

### 购物车-商品列表展示

- 定义子组件CartList

- for循环展示商品数据

- 导入better-scroll组件滚动

- 定义子组件CartListItem

- 遍历这个子组件，传递商品数据

- 布局，样式，展示

- 如果不能滚动，可能是better-scroll在购物车添加新数据时scrollerHegith计算高度没有刷新，要刷新一下

  - activated() {

    ​	this.$refs.scroll.refresh()

    }

### 购物车-列表的item展示

- 样式，布局
- 新建CheckButton组件，放在content中，因为可能在其他页面也会用到

### 购物车-item选中和不选中的切换

- 选中或不选中是在对象模型中保存状态，默认是选中的
- payload.checked = true
- 监听点击事件，将状态取反

### 购物车-底部工具的封装和应用

- 新建子组件CarBottomBar
- 导入CheckButton组件
- 调整样式，flex布局
- 合计商品价格，定义计算属性totalPrice，返回购物车数据计算后的价格，首先过滤选中的商品filter，然后累加选中商品的价格reduce

### 内容回顾

- 商品信息由Vuex管理，将mutations中的代码抽取到actions中，定义两个mutations
- 购物车商品展示，better-scroll滚动问题，需要刷新
- 商品选中和不选中切换，需要修改模型对象，payload.checked=true

### 购物车-全选按钮的状态显示

- 判断是否有一个不选中，如果有那么全选按钮就是不选中
- 使用数组的高阶函数：filter，find，some，every

### 购物车-全选按钮的点击效果

- 监听点击事件
- 原来是全选中，点击一次，取消全选中
- 原来是不全选中，点击一次，全部选中
- 使用forEach函数

### Vuex-actions返回Promise

- Toast（吐司）：弹窗
- 在Vue.x做了操作，如果想让外界直到，就需要使用Promise

- Promise.then()

### mapActions的映射关系

- 导入import { mapActions } from 'actions.js'

- ```
  methods: {
  	...mapActions(['addCart'])
  }
  ```

### Toast封装-普通方式

- 在common中新建Toast组件
- 设置布局和样式
- 监听按钮点击，传入数据和显示隐藏Toast组件，定义setTimeout函数
- 以上普通的封装太麻烦，如果在多个地方使用，会有很多重复代码，因此需要封装起来使用
- 理想封装后只需要一行代码即可使用
  - this.$toast.show(res, 2000)

### Toast封装-插件方式

### 补充一些细节

- 移动端使用一个轻量库FastClick，减小移动端300ms延迟
  - 安装
  - 导入
  - 调用attach函数
- polyfill，补丁，填充材料

# 2021-11-27 选集P226-P232

### 图片懒加载vue-lazyload库

- npm安装 --save
- Vue.use(VueLazyLoad，{ 构造器选项loading：require('图片路径') })导入import from使用
- 修改img：为v-lazy

### nginx-项目在windows下的部署

- 项目打包npm run build
- nginx服务器部署
- 服务器问题：一台电脑，没有显示器，只是主机，24小时开机，为用户提供服务
- 大部分公司没有自己的服务器主机，成本高，只好租借（阿里云，华为云，腾讯云）
- 主机 -》操作系统 -》windows(.net)/Linux -》 tomcat/nginx（软件/反向代理）
- 打包后的dist文件夹部署在主机中
- 1、将自己的电脑作为服务器-》window-》nginx（服务器）
- 2、远程部署（Mac）
- nginx：
  - mainline 主力开发版本
  - stable 稳定版本
  - Legacy 遗留版本
  - 双击exe启动（解压文件路径不要有中文）
  - localhost查看端口是否被占用
  - Welcome to nginx
  - 将dist文件夹复制到解压文件中，index替换默认html文件，访问localhost就会访问项目（或者修改配置，conf文件夹中nginx.conf中location中的root 改为dist，然后关闭nginx -s stop,重启nginx：nginx -s reload）（报错的话看看pid值或者是否启动了多个）
  - nginx.conf中的server修改来解决跨域问题

### nginx-项目在远程Linux下的部署

