maven:

maven中项目的继承依赖包可以怎么管理

 1.通过parent项目中的pom.xml文件进行统一管理,在pom.xml中<dependenices></dependenices>内的所有jar包子项目都可以使 用

 2.parent项目中pom.xml文件中的 <dependsManagerment>来统一管理jar的版本,子项目在使用jar包时,不需要显示版本号,maven会一级级网上找dependManagerment,在使用该标签下的版本,避免了多个子项目之间的jar版本冲突问题

 ps: 默认情况下<dependsManagerment>中jar包不会被子项目继承,若子项目需要使用,可以手动添加即可,版本不用写
