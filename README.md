yarn-demo
=========

Simple YARN Demo project

 - Tested against plain Apache Hadoop 2.2.0 [1]

Build using:

    mvn clean package

Submit app to YARN:

    $ java -jar target/yarn-demo-0.1.0.jar

Check logs:

    $ yarn application -appStates ALL -list

(find latest application-Id - use that for next command)

    $ find hadoop-2.2.0/logs/userlogs/application_1400885161943_0004|grep std

(find the Container.stdout path and use that for next command)

    $ grep Hello hadoop-2.2.0/logs/userlogs/application_1400885161943_0004/container_1400885161943_0004_01_000002/Container.stdout
    07:27:41,246  INFO xample.spring.demo.Application$HelloPojo:  28 - Hello from YARN!

That's it!


[1] Spring XD has a simple guide for installing Apache Hadoop 2.2.0 - <https://github.com/spring-projects/spring-xd/wiki/Hadoop-Installation>
