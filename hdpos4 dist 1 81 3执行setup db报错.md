
## hdpos4-dist:1.81.3执行setup_db报错


```
"[INFO] commit执行结果：0 rows effect.", "[INFO] [SQLDOC:META-INF/latin-sys-core/setup/script/oracle/data/goodsHintConfig]: goodsHintConfig.mysql.sql Running ...", "[ERROR] 执行SQL语句insert into GoodsHintConfig(length, operate) values (0, '%=')：发生错误：ORA-00001: 违反唯一约束条件 (HDPOSCS.IDX_GOODSHINTCONFIG_X1)", "", "[INFO] ============================================================", "[INFO] [PERFORM]", "[INFO]   com.hd123.hdpos4.rdb.setup.SetupUpgrader:", "[INFO]     [FAILURE]     47,011ms", "[INFO] ", "[INFO]   Total:          47,245ms", "[INFO] ============================================================", "[ERROR] ", "java.sql.SQLIntegrityConstraintViolationException: ORA-00001: 违反唯一约束条件 (HDPOSCS.IDX_GOODSHINTCONFIG_X1)", "", "\tat oracle.jdbc.driver.T4CTTIoer.processError(T4CTTIoer.java:447)", "\tat oracle.jdbc.driver.T4CTTIoer.processError(T4CTTIoer.java:396)", "\tat oracle.jdbc.driver.T4C8Oall.processError(T4C8Oall.java:951)", "\tat oracle.jdbc.driver.T4CTTIfun.receive(T4CTTIfun.java:513)", "\tat oracle.jdbc.driver.T4CTTIfun.doRPC(T4CTTIfun.java:227)", "\tat oracle.jdbc.driver.T4C8Oall.doOALL(T4C8Oall.java:531)", "\tat oracle.jdbc.driver.T4CStatement.doOall8(T4CStatement.java:195)", "\tat oracle.jdbc.driver.T4CStatement.executeForRows(T4CStatement.java:1036)", "\tat oracle.jdbc.driver.OracleStatement.doExecuteWithTimeout(OracleStatement.java:1336)", "\tat oracle.jdbc.driver.OracleStatement.executeUpdateInternal(OracleStatement.java:1845)", "\tat oracle.jdbc.driver.OracleStatement.executeUpdate(OracleStatement.java:1810)", "\tat oracle.jdbc.driver.OracleStatementWrapper.executeUpdate(OracleStatementWrapper.java:294)", "\tat org.apache.commons.dbcp.DelegatingStatement.executeUpdate(DelegatingStatement.java:228)", "\tat org.apache.commons.dbcp.DelegatingStatement.executeUpdate(DelegatingStatement.java:228)", "\tat com.hd123.latin.upgrade.sql.SqlExecuter.executeSQL(SqlExecuter.java:194)", "\tat com.hd123.latin.upgrade.sql.SqlExecuter$$FastClassBySpringCGLIB$$91af106a.invoke(<generated>)", "\tat org.springframework.cglib.proxy.MethodProxy.invoke(MethodProxy.java:204)", "\tat org.springframework.aop.framework.CglibAopProxy$CglibMethodInvocation.invokeJoinpoint(CglibAopProxy.java:700)", "\tat org.springframework.aop.framework.ReflectiveMethodInvocation.proceed(ReflectiveMethodInvocation.java:150)", "\tat org.springframework.transaction.interceptor.TransactionInterceptor$1.proceedWithInvocation(TransactionInterceptor.java:96)", "\tat org.springframework.transaction.interceptor.TransactionAspectSupport.invokeWithinTransaction(TransactionAspectSupport.java:260)", "\tat org.springframework.transaction.interceptor.TransactionInterceptor.invoke(TransactionInterceptor.java:94)", "\tat org.springframework.aop.framework.ReflectiveMethodInvocation.proceed(ReflectiveMethodInvocation.java:172)", "\tat org.springframework.aop.framework.CglibAopProxy$DynamicAdvisedInterceptor.intercept(CglibAopProxy.java:633)", "\tat com.hd123.latin.upgrade.sql.SqlExecuter$$EnhancerBySpringCGLIB$$26e59c1d.executeSQL(<generated>)", "\tat com.hd123.latin.upgrade.sql.SqlExecuter.executeSQLScript(SqlExecuter.java:110)", "\tat com.hd123.latin.upgrade.sql.SqlExecuter.executeSqlFile(SqlExecuter.java:58)", "\tat com.hd123.latin.upgrade.sql.SqlExecuter.executeSqlFile(SqlExecuter.java:63)", "\tat com.hd123.latin.upgrade.sql.SqlExecuter$$FastClassBySpringCGLIB$$91af106a.invoke(<generated>)", "\tat org.springframework.cglib.proxy.MethodProxy.invoke(MethodProxy.java:204)", "\tat org.springframework.aop.framework.CglibAopProxy$CglibMethodInvocation.invokeJoinpoint(CglibAopProxy.java:700)", "\tat org.springframework.aop.framework.ReflectiveMethodInvocation.proceed(ReflectiveMethodInvocation.java:150)", "\tat org.springframework.transaction.interceptor.TransactionInterceptor$1.proceedWithInvocation(TransactionInterceptor.java:96)", "\tat org.springframework.transaction.interceptor.TransactionAspectSupport.invokeWithinTransaction(TransactionAspectSupport.java:260)", "\tat org.springframework.transaction.interceptor.TransactionInterceptor.invoke(TransactionInterceptor.java:94)", "\tat org.springframework.aop.framework.ReflectiveMethodInvocation.proceed(ReflectiveMethodInvocation.java:172)", "\tat org.springframework.aop.framework.CglibAopProxy$DynamicAdvisedInterceptor.intercept(CglibAopProxy.java:633)", "\tat com.hd123.latin.upgrade.sql.SqlExecuter$$EnhancerBySpringCGLIB$$26e59c1d.executeSqlFile(<generated>)", "\tat com.hd123.latin.rdbver.upgrade.BaseScriptUpgrader.upgradeFile(BaseScriptUpgrader.java:233)", "\tat com.hd123.latin.rdbver.upgrade.BaseScriptUpgrader.runByPath(BaseScriptUpgrader.java:160)", "\tat com.hd123.latin.rdbver.upgrade.BaseScriptUpgrader.execute(BaseScriptUpgrader.java:106)", "\tat com.hd123.rumba.rdbver.upgrader.UpgraderManager.callUpgrader(UpgraderManager.java:953)", "\tat com.hd123.rumba.rdbver.upgrader.UpgraderManager.callUpgraders(UpgraderManager.java:820)", "\tat com.hd123.rumba.rdbver.upgrader.UpgraderManager.doPerform(UpgraderManager.java:561)", "\tat com.hd123.rumba.rdbver.upgrader.UpgraderManager.all(UpgraderManager.java:225)", "\tat com.hd123.rumba.rdbver.cli.CommandDispatcher.dispatch(CommandDispatcher.java:161)", "\tat com.hd123.latin.rdbver.upgrade.UpgradeEntry.run2(UpgradeEntry.java:57)", "\tat com.hd123.hdpos4.rdb.setup.Main.main(Main.java:67)"]}
```

## h6-openapi2-service:1.14执行setup报错

```
"[ERROR] ", "com.hd123.rumba.rdbver.upgrader.UpgraderManagerException: java.sql.SQLSyntaxErrorException: ORA-00942: 表或视图不存在", "", "\tat com.hd123.rumba.rdbver.upgrader.UpgraderManager.callUpgrader(UpgraderManager.java:737)", "\tat com.hd123.rumba.rdbver.upgrader.UpgraderManager.callUpgraders(UpgraderManager.java:720)", "\tat com.hd123.rumba.rdbver.upgrader.UpgraderManager.doPerform(UpgraderManager.java:399)", "\tat com.hd123.rumba.rdbver.upgrader.UpgraderManager.all(UpgraderManager.java:296)", "\tat com.hd123.rumba.rdbver.cli.CommandDispatcher.dispatch(CommandDispatcher.java:160)", "\tat com.hd123.rumba.rdbver.cli.CommandLineMain.run(CommandLineMain.java:77)", "\tat com.hd123.h6.openapi2.rdb.setup.Main.main(Main.java:55)", "Caused by: java.sql.SQLSyntaxErrorException: ORA-00942: 表或视图不存在", "", "\tat oracle.jdbc.driver.T4CTTIoer.processError(T4CTTIoer.java:447)", "\tat oracle.jdbc.driver.T4CTTIoer.processError(T4CTTIoer.java:396)", "\tat oracle.jdbc.driver.T4C8Oall.processError(T4C8Oall.java:951)", "\tat oracle.jdbc.driver.T4CTTIfun.receive(T4CTTIfun.java:513)", "\tat oracle.jdbc.driver.T4CTTIfun.doRPC(T4CTTIfun.java:227)", "\tat oracle.jdbc.driver.T4C8Oall.doOALL(T4C8Oall.java:531)", "\tat oracle.jdbc.driver.T4CStatement.doOall8(T4CStatement.java:195)", "\tat oracle.jdbc.driver.T4CStatement.executeForRows(T4CStatement.java:1036)", "\tat oracle.jdbc.driver.OracleStatement.doExecuteWithTimeout(OracleStatement.java:1336)", "\tat oracle.jdbc.driver.OracleStatement.executeUpdateInternal(OracleStatement.java:1845)", "\tat oracle.jdbc.driver.OracleStatement.executeUpdate(OracleStatement.java:1810)", "\tat oracle.jdbc.driver.OracleStatementWrapper.executeUpdate(OracleStatementWrapper.java:294)", "\tat com.alibaba.druid.pool.DruidPooledStatement.executeUpdate(DruidPooledStatement.java:324)", "\tat com.hd123.swallows.dao.executor.DefaultSqlExecutor.executeSQL(DefaultSqlExecutor.java:74)", "\tat com.hd123.swallows.dao.executor.DefaultSqlExecutor.executeSQLScript(DefaultSqlExecutor.java:204)", "\tat com.hd123.swallows.dao.executor.DefaultSqlExecutor.executeFile(DefaultSqlExecutor.java:50)", "\tat com.hd123.swallows.dao.executor.DefaultSqlExecutor.executeFile(DefaultSqlExecutor.java:55)", "\tat com.hd123.swallows.upgrader.BaseScriptUpgrader.upgradeFile(BaseScriptUpgrader.java:131)", "\tat com.hd123.swallows.upgrader.BaseScriptUpgrader.runByPath(BaseScriptUpgrader.java:105)", "\tat com.hd123.swallows.upgrader.BaseScriptUpgrader.execute(BaseScriptUpgrader.java:74)", "\tat com.hd123.rumba.rdbver.upgrader.ConfigurableUpgraderWrapper.execute(ConfigurableUpgraderWrapper.java:50)", "\tat com.hd123.rumba.rdbver.upgrader.UpgraderManager.callUpgrader(UpgraderManager.java:733)", "\t... 6 more"]}
```


## hdpos4-dist启动报错

```
2023-05-05 14:02:12,322 [localhost-startStop-1] [456f2ee5c5c7446eb06a4c631cab5fce] ERROR org.springframework.web.context.ContextLoader - Context initialization failed
org.springframework.beans.factory.parsing.BeanDefinitionParsingException: Configuration problem: Failed to import bean definitions from URL location [classpath:latin-core.xml]
Offending resource: class path resource [main.xml]; nested exception is org.springframework.beans.factory.parsing.BeanDefinitionParsingException: Configuration problem: Failed to import bean definitions from URL location [classpath:META-INF/latin-commons-core/*.xml]
Offending resource: class path resource [latin-core.xml]; nested exception is org.springframework.beans.factory.BeanDefinitionStoreException: Unexpected exception parsing XML document from file [/opt/heading/tomcat7/webapps/hdpos4-web/WEB-INF/classes/META-INF/latin-commons-core/config.xml]; nested exception is java.lang.IllegalArgumentException: Could not resolve placeholder 'cache.config' in string value "classpath:META-INF/cache/${cache.config}"
	at org.springframework.beans.factory.parsing.FailFastProblemReporter.error(FailFastProblemReporter.java:68)
	at org.springframework.beans.factory.parsing.ReaderContext.error(ReaderContext.java:85)
	at org.springframework.beans.factory.parsing.ReaderContext.error(ReaderContext.java:76)
	at org.springframework.beans.factory.xml.DefaultBeanDefinitionDocumentReader.importBeanDefinitionResource(DefaultBeanDefinitionDocumentReader.java:256)
	at org.springframework.beans.factory.xml.DefaultBeanDefinitionDocumentReader.parseDefaultElement(DefaultBeanDefinitionDocumentReader.java:207)
	at org.springframework.beans.factory.xml.DefaultBeanDefinitionDocumentReader.parseBeanDefinitions(DefaultBeanDefinitionDocumentReader.java:192)
	at org.springframework.beans.factory.xml.DefaultBeanDefinitionDocumentReader.doRegisterBeanDefinitions(DefaultBeanDefinitionDocumentReader.java:139)
	at org.springframework.beans.factory.xml.DefaultBeanDefinitionDocumentReader.registerBeanDefinitions(DefaultBeanDefinitionDocumentReader.java:108)
	at org.springframework.beans.factory.xml.XmlBeanDefinitionReader.registerBeanDefinitions(XmlBeanDefinitionReader.java:493)
	at org.springframework.beans.factory.xml.XmlBeanDefinitionReader.doLoadBeanDefinitions(XmlBeanDefinitionReader.java:390)
	at org.springframework.beans.factory.xml.XmlBeanDefinitionReader.loadBeanDefinitions(XmlBeanDefinitionReader.java:334)
	at org.springframework.beans.factory.xml.XmlBeanDefinitionReader.loadBeanDefinitions(XmlBeanDefinitionReader.java:302)
	at org.springframework.beans.factory.support.AbstractBeanDefinitionReader.loadBeanDefinitions(AbstractBeanDefinitionReader.java:174)
	at org.springframework.beans.factory.support.AbstractBeanDefinitionReader.loadBeanDefinitions(AbstractBeanDefinitionReader.java:209)
	at org.springframework.beans.factory.support.AbstractBeanDefinitionReader.loadBeanDefinitions(AbstractBeanDefinitionReader.java:180)
	at org.springframework.web.context.support.XmlWebApplicationContext.loadBeanDefinitions(XmlWebApplicationContext.java:125)
	at org.springframework.web.context.support.XmlWebApplicationContext.loadBeanDefinitions(XmlWebApplicationContext.java:94)
	at org.springframework.context.support.AbstractRefreshableApplicationContext.refreshBeanFactory(AbstractRefreshableApplicationContext.java:130)
	at org.springframework.context.support.AbstractApplicationContext.obtainFreshBeanFactory(AbstractApplicationContext.java:537)
	at org.springframework.context.support.AbstractApplicationContext.refresh(AbstractApplicationContext.java:451)
	at org.springframework.web.context.ContextLoader.configureAndRefreshWebApplicationContext(ContextLoader.java:410)
	at org.springframework.web.context.ContextLoader.initWebApplicationContext(ContextLoader.java:306)
	at org.springframework.web.context.ContextLoaderListener.contextInitialized(ContextLoaderListener.java:112)
	at org.apache.catalina.core.StandardContext.listenerStart(StandardContext.java:5077)
	at org.apache.catalina.core.StandardContext.startInternal(StandardContext.java:5591)
	at org.apache.catalina.util.LifecycleBase.start(LifecycleBase.java:150)
	at org.apache.catalina.core.ContainerBase.addChildInternal(ContainerBase.java:901)
	at org.apache.catalina.core.ContainerBase.addChild(ContainerBase.java:877)
	at org.apache.catalina.core.StandardHost.addChild(StandardHost.java:652)
	at org.apache.catalina.startup.HostConfig.deployDirectory(HostConfig.java:1263)
	at org.apache.catalina.startup.HostConfig$DeployDirectory.run(HostConfig.java:1975)
	at java.util.concurrent.Executors$RunnableAdapter.call(Executors.java:511)
	at java.util.concurrent.FutureTask.run(FutureTask.java:266)
	at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1149)
	at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624)
	at java.lang.Thread.run(Thread.java:748)
Caused by: org.springframework.beans.factory.parsing.BeanDefinitionParsingException: Configuration problem: Failed to import bean definitions from URL location [classpath:META-INF/latin-commons-core/*.xml]
Offending resource: class path resource [latin-core.xml]; nested exception is org.springframework.beans.factory.BeanDefinitionStoreException: Unexpected exception parsing XML document from file [/opt/heading/tomcat7/webapps/hdpos4-web/WEB-INF/classes/META-INF/latin-commons-core/config.xml]; nested exception is java.lang.IllegalArgumentException: Could not resolve placeholder 'cache.config' in string value "classpath:META-INF/cache/${cache.config}"
	at org.springframework.beans.factory.parsing.FailFastProblemReporter.error(FailFastProblemReporter.java:68)
	at org.springframework.beans.factory.parsing.ReaderContext.error(ReaderContext.java:85)
	at org.springframework.beans.factory.parsing.ReaderContext.error(ReaderContext.java:76)
	at org.springframework.beans.factory.xml.DefaultBeanDefinitionDocumentReader.importBeanDefinitionResource(DefaultBeanDefinitionDocumentReader.java:256)
	at org.springframework.beans.factory.xml.DefaultBeanDefinitionDocumentReader.parseDefaultElement(DefaultBeanDefinitionDocumentReader.java:207)
	at org.springframework.beans.factory.xml.DefaultBeanDefinitionDocumentReader.parseBeanDefinitions(DefaultBeanDefinitionDocumentReader.java:192)
	at org.springframework.beans.factory.xml.DefaultBeanDefinitionDocumentReader.doRegisterBeanDefinitions(DefaultBeanDefinitionDocumentReader.java:139)
	at org.springframework.beans.factory.xml.DefaultBeanDefinitionDocumentReader.registerBeanDefinitions(DefaultBeanDefinitionDocumentReader.java:108)
	at org.springframework.beans.factory.xml.XmlBeanDefinitionReader.registerBeanDefinitions(XmlBeanDefinitionReader.java:493)
	at org.springframework.beans.factory.xml.XmlBeanDefinitionReader.doLoadBeanDefinitions(XmlBeanDefinitionReader.java:390)
	at org.springframework.beans.factory.xml.XmlBeanDefinitionReader.loadBeanDefinitions(XmlBeanDefinitionReader.java:334)
	at org.springframework.beans.factory.xml.XmlBeanDefinitionReader.loadBeanDefinitions(XmlBeanDefinitionReader.java:302)
	at org.springframework.beans.factory.support.AbstractBeanDefinitionReader.loadBeanDefinitions(AbstractBeanDefinitionReader.java:174)
	at org.springframework.beans.factory.support.AbstractBeanDefinitionReader.loadBeanDefinitions(AbstractBeanDefinitionReader.java:209)
	at org.springframework.beans.factory.xml.DefaultBeanDefinitionDocumentReader.importBeanDefinitionResource(DefaultBeanDefinitionDocumentReader.java:250)
	... 32 more
Caused by: org.springframework.beans.factory.BeanDefinitionStoreException: Unexpected exception parsing XML document from file [/opt/heading/tomcat7/webapps/hdpos4-web/WEB-INF/classes/META-INF/latin-commons-core/config.xml]; nested exception is java.lang.IllegalArgumentException: Could not resolve placeholder 'cache.config' in string value "classpath:META-INF/cache/${cache.config}"
	at org.springframework.beans.factory.xml.XmlBeanDefinitionReader.doLoadBeanDefinitions(XmlBeanDefinitionReader.java:412)
	at org.springframework.beans.factory.xml.XmlBeanDefinitionReader.loadBeanDefinitions(XmlBeanDefinitionReader.java:334)
	at org.springframework.beans.factory.xml.XmlBeanDefinitionReader.loadBeanDefinitions(XmlBeanDefinitionReader.java:302)
	at org.springframework.beans.factory.support.AbstractBeanDefinitionReader.loadBeanDefinitions(AbstractBeanDefinitionReader.java:174)
	at org.springframework.beans.factory.support.AbstractBeanDefinitionReader.loadBeanDefinitions(AbstractBeanDefinitionReader.java:209)
	at org.springframework.beans.factory.xml.DefaultBeanDefinitionDocumentReader.importBeanDefinitionResource(DefaultBeanDefinitionDocumentReader.java:250)
	... 43 more
Caused by: java.lang.IllegalArgumentException: Could not resolve placeholder 'cache.config' in string value "classpath:META-INF/cache/${cache.config}"
	at org.springframework.util.PropertyPlaceholderHelper.parseStringValue(PropertyPlaceholderHelper.java:173)
	at org.springframework.util.PropertyPlaceholderHelper.replacePlaceholders(PropertyPlaceholderHelper.java:125)
	at org.springframework.core.env.AbstractPropertyResolver.doResolvePlaceholders(AbstractPropertyResolver.java:180)
	at org.springframework.core.env.AbstractPropertyResolver.resolveRequiredPlaceholders(AbstractPropertyResolver.java:145)
	at org.springframework.core.env.AbstractEnvironment.resolveRequiredPlaceholders(AbstractEnvironment.java:493)
	at org.springframework.beans.factory.xml.DefaultBeanDefinitionDocumentReader.importBeanDefinitionResource(DefaultBeanDefinitionDocumentReader.java:233)
	at org.springframework.beans.factory.xml.DefaultBeanDefinitionDocumentReader.parseDefaultElement(DefaultBeanDefinitionDocumentReader.java:207)
	at org.springframework.beans.factory.xml.DefaultBeanDefinitionDocumentReader.parseBeanDefinitions(DefaultBeanDefinitionDocumentReader.java:192)
	at org.springframework.beans.factory.xml.DefaultBeanDefinitionDocumentReader.doRegisterBeanDefinitions(DefaultBeanDefinitionDocumentReader.java:139)
	at org.springframework.beans.factory.xml.DefaultBeanDefinitionDocumentReader.registerBeanDefinitions(DefaultBeanDefinitionDocumentReader.java:108)
	at org.springframework.beans.factory.xml.XmlBeanDefinitionReader.registerBeanDefinitions(XmlBeanDefinitionReader.java:493)
	at org.springframework.beans.factory.xml.XmlBeanDefinitionReader.doLoadBeanDefinitions(XmlBeanDefinitionReader.java:390)
	... 48 more
```


## panther-dts-server启动报错

```
15:30:01,182 [rumba-quartz-core.scheduler_Worker-3] WARN org.hibernate.util.JDBCExceptionReporter - SQL Error: 942, SQLState: 42000
15:30:01,190 [rumba-quartz-core.scheduler_Worker-3] ERROR org.hibernate.util.JDBCExceptionReporter - ORA-00942: 表或视图不存在

15:30:01,215 [rumba-quartz-core.scheduler_Worker-3] ERROR com.hd123.rumba.quartz.job.AbstractJob - Job Aborted.
javax.persistence.PersistenceException: org.hibernate.exception.SQLGrammarException: could not execute query
	at org.hibernate.ejb.AbstractEntityManagerImpl.convert(AbstractEntityManagerImpl.java:1387)
	at org.hibernate.ejb.AbstractEntityManagerImpl.convert(AbstractEntityManagerImpl.java:1315)
	at org.hibernate.ejb.QueryImpl.getResultList(QueryImpl.java:255)
	at sun.reflect.GeneratedMethodAccessor57.invoke(Unknown Source)
	at sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
	at java.lang.reflect.Method.invoke(Method.java:498)
	at org.springframework.orm.jpa.SharedEntityManagerCreator$DeferredQueryInvocationHandler.invoke(SharedEntityManagerCreator.java:311)
	at com.sun.proxy.$Proxy78.getResultList(Unknown Source)
	at com.hd123.rumba.commons.jpa.query.executor.JpaSimpleQueryExecutor.query(JpaSimpleQueryExecutor.java:142)
	at com.hd123.rumba.commons.jpa.query.executor.JpaSimpleQueryExecutor.query(JpaSimpleQueryExecutor.java:120)
	at com.hd123.rumba.commons.jpa.query.executor.PrecisePagingSelector.queryCount(PrecisePagingSelector.java:91)
	at com.hd123.rumba.commons.jpa.query.executor.PrecisePagingSelector.queryPage(PrecisePagingSelector.java:127)
	at com.hd123.rumba.commons.jpa.query.executor.PrecisePagingSelector.query(PrecisePagingSelector.java:79)
	at com.hd123.rumba.commons.jpa.query.executor.JpaQueryExecutor.query(JpaQueryExecutor.java:295)
	at com.hd123.h4.panther.dts.dao.datageneration.PDataGenerationTaskDao.queryPk(PDataGenerationTaskDao.java:232)
	at com.hd123.h4.panther.dts.dao.datageneration.PDataGenerationTaskDao$$FastClassBySpringCGLIB$$dad30e13.invoke(<generated>)
	at org.springframework.cglib.proxy.MethodProxy.invoke(MethodProxy.java:204)
	at org.springframework.aop.framework.CglibAopProxy$DynamicAdvisedInterceptor.intercept(CglibAopProxy.java:629)
	at com.hd123.h4.panther.dts.dao.datageneration.PDataGenerationTaskDao$$EnhancerBySpringCGLIB$$d1276e48.queryPk(<generated>)
	at com.hd123.h4.panther.dts.job.JobDispatcher$Executor.existDataGenerationTask(JobDispatcher.java:522)
	at com.hd123.h4.panther.dts.job.JobDispatcher$Executor.autoStartPosDataUpdateJob(JobDispatcher.java:407)
	at com.hd123.h4.panther.dts.job.JobDispatcher$Executor.execute(JobDispatcher.java:317)
	at com.hd123.h4.panther.dts.job.JobDispatcher.doExecute(JobDispatcher.java:300)
	at com.hd123.rumba.quartz.job.AbstractJob.execute(AbstractJob.java:50)
	at com.hd123.h4.panther.dts.job.JobDispatcher.execute(JobDispatcher.java:278)
	at org.quartz.core.JobRunShell.run(JobRunShell.java:202)
	at org.quartz.simpl.SimpleThreadPool$WorkerThread.run(SimpleThreadPool.java:573)
Caused by: org.hibernate.exception.SQLGrammarException: could not execute query
	at org.hibernate.exception.SQLStateConverter.convert(SQLStateConverter.java:92)
	at org.hibernate.exception.JDBCExceptionHelper.convert(JDBCExceptionHelper.java:66)
	at org.hibernate.loader.Loader.doList(Loader.java:2545)
	at org.hibernate.loader.Loader.listIgnoreQueryCache(Loader.java:2276)
	at org.hibernate.loader.Loader.list(Loader.java:2271)
	at org.hibernate.loader.hql.QueryLoader.list(QueryLoader.java:459)
	at org.hibernate.hql.ast.QueryTranslatorImpl.list(QueryTranslatorImpl.java:365)
	at org.hibernate.engine.query.HQLQueryPlan.performList(HQLQueryPlan.java:196)
	at org.hibernate.impl.SessionImpl.list(SessionImpl.java:1268)
	at org.hibernate.impl.QueryImpl.list(QueryImpl.java:102)
	at org.hibernate.ejb.QueryImpl.getResultList(QueryImpl.java:246)
	... 24 more
Caused by: java.sql.SQLSyntaxErrorException: ORA-00942: 表或视图不存在

	at oracle.jdbc.driver.T4CTTIoer.processError(T4CTTIoer.java:447)
	at oracle.jdbc.driver.T4CTTIoer.processError(T4CTTIoer.java:396)
	at oracle.jdbc.driver.T4C8Oall.processError(T4C8Oall.java:951)
	at oracle.jdbc.driver.T4CTTIfun.receive(T4CTTIfun.java:513)
	at oracle.jdbc.driver.T4CTTIfun.doRPC(T4CTTIfun.java:227)
	at oracle.jdbc.driver.T4C8Oall.doOALL(T4C8Oall.java:531)
	at oracle.jdbc.driver.T4CPreparedStatement.doOall8(T4CPreparedStatement.java:208)
	at oracle.jdbc.driver.T4CPreparedStatement.executeForDescribe(T4CPreparedStatement.java:886)
	at oracle.jdbc.driver.OracleStatement.executeMaybeDescribe(OracleStatement.java:1175)
	at oracle.jdbc.driver.OracleStatement.doExecuteWithTimeout(OracleStatement.java:1296)
	at oracle.jdbc.driver.OraclePreparedStatement.executeInternal(OraclePreparedStatement.java:3613)
	at oracle.jdbc.driver.OraclePreparedStatement.executeQuery(OraclePreparedStatement.java:3657)
	at oracle.jdbc.driver.OraclePreparedStatementWrapper.executeQuery(OraclePreparedStatementWrapper.java:1495)
	at org.apache.commons.dbcp.DelegatingPreparedStatement.executeQuery(DelegatingPreparedStatement.java:96)
	at org.apache.commons.dbcp.DelegatingPreparedStatement.executeQuery(DelegatingPreparedStatement.java:96)
	at sun.reflect.GeneratedMethodAccessor59.invoke(Unknown Source)
	at sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
	at java.lang.reflect.Method.invoke(Method.java:498)
	at org.jdbcdslog.PreparedStatementLoggingHandler.invoke(PreparedStatementLoggingHandler.java:35)
	at com.sun.proxy.$Proxy79.executeQuery(Unknown Source)
	at org.hibernate.jdbc.AbstractBatcher.getResultSet(AbstractBatcher.java:208)
	at org.hibernate.loader.Loader.getResultSet(Loader.java:1953)
	at org.hibernate.loader.Loader.doQuery(Loader.java:802)
	at org.hibernate.loader.Loader.doQueryAndInitializeNonLazyCollections(Loader.java:274)
	at org.hibernate.loader.Loader.doList(Loader.java:2542)
	... 32 more
```

