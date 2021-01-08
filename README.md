### Opplates

> OpeningO templates



##### SpringBoot

> SpringBoot多种环境下的配置

- 多数据库
- 多MySQL

- logback

##### MyBatisPlusGenerator依赖

> 建议在test中生成即可。

- properties

  ```xml
  <properties>
        <java.version>1.8</java.version>
        <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
        <project.reporting.outputEncoding>UTF-8</project.reporting.outputEncoding>
        <maven.compiler.source>${java.version}</maven.compiler.source>
        <maven.compiler.target>${java.version}</maven.compiler.target>
        <lombok.version>1.18.8</lombok.version>
        <springboot.version>2.1.8.RELEASE</springboot.version>
        <druid.version>1.1.21</druid.version>
        <ojdbc.version>11.2.0.4.0-atlassian-hosted</ojdbc.version>
        <mysql.sersion>8.0.17</mysql.sersion>
        <springboot.mybatis.version>2.1.0</springboot.mybatis.version>
        <mybatis-plus.version>3.3.2</mybatis-plus.version>
        <mybatis-x.version>1.0</mybatis-x.version>
        <jdkits.version>1.0.1</jdkits.version>
        <postgresql.version>42.2.14</postgresql.version>
        <velocity.version>2.2</velocity.version>
    </properties>
  ```

- 必须依赖

  ```xml
  <!-- 开启lombok时 -->
  <dependency>
      <groupId>org.projectlombok</groupId>
      <artifactId>lombok</artifactId>
      <version>${lombok.version}</version>
  </dependency>
  
  <dependency>
      <groupId>org.mybatis.spring.boot</groupId>
      <artifactId>mybatis-spring-boot-starter</artifactId>
      <version>${springboot.mybatis.version}</version>
  </dependency>
  
  <!-- mybatis plus -->
  <dependency>
      <groupId>com.baomidou</groupId>
      <artifactId>mybatis-plus-boot-starter</artifactId>
      <version>${mybatis-plus.version}</version>
  </dependency>
  
  <!-- mybatis plus generator with test envoriment -->
  <dependency>
      <groupId>com.baomidou</groupId>
      <artifactId>mybatis-plus-generator</artifactId>
      <version>${mybatis-plus.version}</version>
      <scope>test</scope>
  </dependency>
  <dependency>
      <groupId>org.apache.velocity</groupId>
      <artifactId>velocity-engine-core</artifactId>
      <version>${velocity.version}</version>
      <scope>test</scope>
  </dependency>
  
  <!-- test -->
  <dependency>
      <groupId>org.springframework.boot</groupId>
      <artifactId>spring-boot-starter-test</artifactId>
      <scope>test</scope>
  </dependency>
  ```

- MySQL

  ```xml
  <dependency>
      <groupId>mysql</groupId>
      <artifactId>mysql-connector-java</artifactId>
      <version>${mysql.sersion}</version>
  </dependency>
  <dependency>
      <groupId>org.openingo.kits</groupId>
      <artifactId>mybatis-x</artifactId>
      <version>${mybatis-x.version}</version>
  </dependency>
  ```

- Oracle

  ```xml
  <dependency>
      <groupId>com.oracle</groupId>
      <artifactId>ojdbc6</artifactId>
      <version>${ojdbc.version}</version>
  </dependency>
  ```

- PostgreSQL

  ```xml
  <dependency>
      <groupId>org.postgresql</groupId>
      <artifactId>postgresql</artifactId>
      <version>${postgresql.version}</version>
  </dependency>
  ```

> 问题：

- Oracle

> 表名及字段都需要用大写，mp gererator出来的 date字段为LocalDateTime，但按照此类型写入数据时，类型错误，需要调整为java.util.Date，调整`com.baomidou.mybatisplus.generator.config.GlobalConfig#dateType`进行配置。

- PostgreSQL

> 表名及字段必须用小写，不然会出现字段找不到的情况。
>
> 在生成的entity中没有@TableField注解



##### Copyright

> 拷贝对应的文件到 `.idea/copyright/`下即可。

