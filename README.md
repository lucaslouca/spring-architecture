# spring-architecture
Java maven project to illustrate a good practice spring service-dao architecture.

**How to Import into Eclipse**
* **File** -> **Import...** -> **Existing Maven Projects**
* Click **Next**
* Click **Browse...** for the **Root Directory**
* Select and open **spring-app**
* Click **Finish**
* Right click on **spring-app** in the Eclipse Project Explorer -> **Maven** -> **Update Project...**

**Architecture**
The idea is to keep the API separate from the implementation. For example, the DAO are kept separate from the their implementations (dummy, jdbc, hibernate, etc). Similarly, the Services are being kept in separate projects from the actual Bean implementations. 

This architecture illustrates how easy it is to switch between a dummy DAO implementation and a DAO implementation that uses Hibernate, simply by changing:

```java
@ContextConfiguration(classes = { DaoDummyConfig.class })
```
to this:

```java
@ContextConfiguration(classes = { DaoHibernateConfig.class })
```
