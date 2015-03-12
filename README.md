# spring-architecture
Java maven project to illustrate a good practice spring service-dao architecture.

**How to Import into Eclipse**
* **File** -> **Import...** -> **Existing Maven Projects**
* Click **Next**
* Click **Browse...** for the **Root Directory**
* Select and open **spring-app**
* Click **Finish**
* Right click on **spring-app** in the Eclipse Project Explorer -> **Maven** -> **Update Project...**

**Running a Test**

To test the ``LibraryService`` run the ``com.mydomain.app.impl.AppTest`` in the **spring-app-service** module.

Note: You need a running MySQL database to test the JDBC and Hibernate DAO (see src/main/resources/jdbc.properties under **spring-app-dao**).

**Architecture**

The idea is to keep the API separate from the implementation. For example, the DAO are kept separate from the their implementations (dummy, jdbc, hibernate, etc). Similarly, the Services are being kept in separate projects from the actual Bean implementations. Best practices like **programming against interfaces** is also illustrated in this project.

This architecture illustrates how easy it is to switch between a dummy DAO implementation and a DAO implementation that uses Hibernate, simply by changing:

```java
@ContextConfiguration(classes = { DaoDummyConfig.class })
```
to this:

```java
@ContextConfiguration(classes = { DaoHibernateConfig.class })
```
