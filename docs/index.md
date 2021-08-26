less是css预处理语言。增加了变量,mixin,函数等特性。使css更易维护或扩展。

变量:
变量可以先使用后声明，意味预处理时会将变量解析提升。 使用@变量名;方式进行变量声明; 适用场景：动态类名。类动态属性名。类属性动态值。样式字符串模板。

动态类名:

````less

@my-layout: view-layout;

.@{my-layout} {
  height: 100%
}

````

类动态属性名:

````less

@property: color;

.view-layout {
  @{property}: red;
  background-@{property}: red;
}

````

类属性动态值:

````less

@color: red;

.main {
  color: @color;
  @green: green;

  .header {
    color: @@green;
  }
}

````

样式字符串模板:

````less
@url: "/static/test";

@import "@{url}/index.html";

.test {
  background: url("@{url}/white-sand.png");
}
````
