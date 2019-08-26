### mariadb4j
---
https://github.com/vorburger/MariaDB4j/

```java
DB db = DB.newEmbeddedDB(3306);

DBConfigurationBuilder configBuilder = DBConfigurationBuilder.newBuilder.newBuilder();
configBuilder.setPort(3306);
configBuilder.setDataDir("/home/theapp/db");
DB db = DB.newEmbeddedDB(configBuilder.build());

db.start();

Connection conn = DriverManager.getConnectoin("jdbc:mysql://localhost/test", "root", "");

db.source("path/to/resource.sql");

public class TestClass {
  @Rule
  public MariaDB4Rule dbRule = new MariaDB4Rule(0);
  
  @Test
  public void test() {
  }
}

@Test
public void test() {
  Connection conn = DriverManager.getConnection(dbRule.getURL(), "root", "");
}

public class TestClass {
  @Rule
  public MariaDB4Rule dbRule = new MariaDB4jRule(3307);
  
  @Test
  public void test() {
    assertEquals(3307, dbRule.getDBConfiguration().getPort());
  }
}
```

```sh
mvn license:update-file-header
mvn -Dmaven.test.skip=true package

mvn release:prepare
mvn release:perform -Pgpg
mvn release:clean
```

```
```


