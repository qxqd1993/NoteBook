
1. 将要添加的依赖包（比如 ${filename}.jar）拷贝到项目根目录的 ` ./lib ` 下面
2. 执行以下单行语句：
```
  mvn deploy:deploy-file 
    -Dfile=./lib/${filename}.jar 
    -DrepositoryId=my-local-repo 
    -DgroupId=idv.titangin -DartifactId=${filename} 
    -Dversion=0.1.0-SNAPSHOT 
    -Dpackaging=jar 
    -Durl=file:./lib/ 
```
3. 将"${filename}"替换为你所拷贝.jar包不含后缀名的名称，
在 `./pom.xml` 中的 `dependencies` 标签下添加如下数行：
```
    <dependency>
      <groupId>idv.titangin</groupId>
      <artifactId>${filename}</artifactId>
      <version>0.1.0-SNAPSHOT</version>
    </dependency>
```
