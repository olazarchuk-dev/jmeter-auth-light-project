
```shell
> apache-jmeter-5.0/bin/jmeter
```
![Screenshot-06](img/screenshot_06.png)

* Set config remote API-address for rest-test:
![Screenshot-09](img/screenshot_09.png)
![Screenshot-08](img/screenshot_08.png)
![Screenshot-07](img/screenshot_07.png)

* Start = 1.0 only first time (request/second)
* End = 3.0 always time (request/second)
* Duration = 10 load duration period (seconds)
  ![Screenshot-01](img/screenshot_01.png)

* Duration to assert = 15 timeout response duration (milliseconds)
  ![Screenshot-02](img/screenshot_02.png)

* Successful status code = 200
  ![Screenshot-03](img/screenshot_03.png)

* Samples - Count requests on load duration period
* Average - Average time on response duration
* Throughput - Count requests on one-second
* Error - Percent response failures
  ![Screenshot-04](img/screenshot_04.png)

* Response time draw on graphic
  ![Screenshot-05](img/screenshot_05.png)

---

Passing variable from response to header in JMETER
---

* https://stackoverflow.com/questions/49318467/passing-variable-from-response-to-header-in-jmeter
  ![Screenshot-10](img/screenshot_10.png)
  ![Screenshot-11](img/screenshot_11.png)
* [How to handle cookie in Apache JMeter](https://www.perfmatrix.com/jmeter-http-cookie-manager)
* [How to generate a cookie and send it in a request in Jmeter](https://stackoverflow.com/questions/40010164/how-to-generate-a-cookie-and-send-it-in-a-request-in-jmeter)
  1. Add the next line to user.properties file (lives in JMeter's "bin" folder
     ```text
     CookieManager.save.cookies=true
     ```
  2. Restart JMeter to pick the property up.
  3. Add HTTP Header Manager and set it up to send the desired header using ${COOKIE_foo} as a value (replace foo with your actual cookie name)
* https://www.capacitas.co.uk/insights/thats-the-way-the-cookie-crumbles-jmeter-style-part-2
  ![Screenshot-12](img/screenshot_12.png)


---

Jmeter - Increment value before each sampler request
---
+ https://jmetervn.com/2016/12/05/jsr223-with-groovy-variables-part-1
+ https://stackoverflow.com/questions/52000899/jmeter-increment-value-before-each-sampler-request
  - In Test Plan, define variable "counter" set to 0
  - Then add a User Parameters which is a PreProcessor (so executed BEFORE SAMPLER) component using __intSum function
  - For auto increment, initialize a variable let say "id" with 0 in the user defined variable then use ${__intSum(${id},1,id)} for auto increment
    ![Screenshot-13](img/screenshot_13.png)
    ![Screenshot-14](img/screenshot_14.png)
    ![Screenshot-15](img/screenshot_15.png)


JMeter Tutorial 
---
* `JMeter User's Manual` https://jmeter.apache.org/usermanual  **(** https://sqa.stackexchange.com/questions/2546/where-can-i-find-good-jmeter-tutorials **)**
* `jmeter_tutorial.pdf (full)` https://www.aaterminals.com.au/wp-content/uploads/2018/01/jmeter_tutorial.pdf
* `JMeter best practices` http://index-of.es/Varios-2/JMeter-Tutorial.pdf
* `?????????? Apache Jmeter` https://riptutorial.com/Download/apache-jmeter-ru.pdf

* `NobleProg - Apache JMeter Testing` https://training-course-material.com/training/Apache_JMeter_Testing


* [(Fuse) ActiveMQ Tuning Guide](https://access.redhat.com/documentation/en-US/Fuse_ESB_Enterprise/7.1/html-single/ActiveMQ_Tuning_Guide/index.html)
* [Monitor ActiveMQ metrics and performance](https://www.datadoghq.com/blog/monitor-activemq-metrics-performance)
  * **(** [mail.google.com](https://mail.google.com/mail/u/0/#inbox/FMfcgxwBVDCvxfCPQXBQKwLsQgKnJzTn) **)**
  * [Installing on Windows](https://app.datadoghq.com/signup/agent#windows) `skmets@gmail.com / a***n`
    ```bash
    msiexec /qn /i datadog-agent-6-latest.amd64.msi APIKEY="43badebfebd35f7401abc04748d758c9" HOSTNAME="my_hostname" TAGS="mytag1,mytag2"
    ```
* [Running Apache ActiveMQ and Hawtio in Standalone Mode](http://bennet-schulz.com/2016/07/apache-activemq-and-hawtio.html)
  * **(** https://dzone.com/articles/running-apache-activemq-and-hawtio-in-standalone-m-1 **)**
  * https://github.com/bennetelli/activemq-hawtio-standalone


---

Rest API Login
---

* `JMeter Introduction`: https://jmeter.apache.org/usermanual/component_reference.html
* `Rest API Login Testing with JMeter` (Step by Step Guide) https://octoperf.com/blog/2018/04/23/jmeter-rest-api-testing/#rest-api-login
* [Meter Distributed Testing Step-by-step](https://jmeter.apache.org/usermanual/jmeter_distributed_testing_step_by_step.pdf)


BeanShell 
---
* `Simple Java Scripting` http://www.beanshell.org/manual/bshmanual.html
* `Count the number of occurences of a string in response data` https://stackoverflow.com/questions/39573591/count-the-number-of-occurences-of-a-string-in-response-data **|** https://www.blazemeter.com/blog/how-to-work-with-strings-in-jmeter
    ```java
    import org.apache.commons.lang.StringUtils;
    
    String response = SampleResult.getResponseDataAsString();
    int count = StringUtils.countMatches(response, "STAN");
    ```



OS_Process_Sampler
---
* http://jmeter.apache.org/usermanual/component_reference.html#OS_Process_Sampler


Setting JDBC SQL Server Connection with JMeter
---

* `Can JMeter be used to delete records from a database?` https://stackoverflow.com/questions/22021865/can-jmeter-be-used-to-delete-records-from-a-database
  ```text
  You must choose Callable Statement in JDBC Request as  delete from Stocks where StockIdent=1
  ```

* https://habr.com/ru/post/261483
* `https://performancebasics.wordpress.com/2016/01/25/setting-up-a-jdbc-sql-server-connection-in-jmeter`
* https://www.blazemeter.com/blog/how-to-retrieve-database-data-for-api-testing-with-jmeter



* `Assertion on JMeter JDBC Request sampler` https://stackoverflow.com/questions/24133498/assertion-on-jmeter-jdbc-request-sampler
* `How to Retrieve Database Data for API Testing with JMeter` https://www.blazemeter.com/blog/how-to-retrieve-database-data-for-api-testing-with-jmeter

* `JMeter: ???????????????? ?????? BeanShell Sampler` https://habr.com/ru/post/250731
* http://performanceoptimize.blogspot.com/2017/05/TimeFucntionInJmeter.html
    ```java
    import java.text.SimpleDateFormat;
    import java.util.Calendar;
    import java.util.Date;
    
    
    Date tokenStatusUpdate = token.get("token_status_update");
    
    int AddSeconds = 01;
    int AddMinutes = 00;
    int AddHours   = 00;
    
    Date now       = new Date();
    Calendar c     = Calendar.getInstance();
    c.setTime(now);
    c.add(Calendar.SECOND, AddSeconds);
    c.add(Calendar.MINUTE, AddMinutes);
    c.add(Calendar.HOUR,   AddHours);
    SimpleDateFormat df = new SimpleDateFormat("HH:mm:ss");
    //String mytime       = df.format(now);
    
    Date nowTime        = c.getTime();
    String mytime       = df.format(nowTime);
    
    FailureMessage = "'token_status_update': " + mytime;
    
    String srtTokenStatusUpdate = df.format(tokenStatusUpdate);
    
    long timeTokenStatusUpdate = tokenStatusUpdate.getTime() / 100;
    long timeNow = (now.getTime() - 100) / 100;
    FailureMessage = "'token_status_update': " + timeTokenStatusUpdate + " --- " + timeNow;
    
  //FailureMessage = "'token_status_update': " + ${__time(/1000,)};
    ```


How to Run External Commands and Programs from JMeter
---
* `run sh script in jmeter` https://stackoverflow.com/questions/30596880/run-sh-script-in-jmeter
                            https://www.blazemeter.com/blog/how-run-external-commands-and-programs-locally-and-remotely-jmeter
* `How to execute jar from OS Process Sampler in Linux` https://stackoverflow.com/questions/38181399/how-to-execute-jar-from-os-process-sampler-in-linux
* `How to Run External Commands and Programs Locally and Remotely from JMeter` https://www.blazemeter.com/blog/how-run-external-commands-and-programs-locally-and-remotely-jmeter



* `https://www.blazemeter.com/blog/creating-and-testing-dates-in-jmeter-learn-how`
* `https://stackoverflow.com/questions/27043029/jmeter-get-current-date-and-time/27048364`
* `https://stackoverflow.com/questions/42364226/jmeter-how-to-get-current-date-and-time-in-seconds`

---

* `JMETER VS SOAPUI` https://octoperf.com/blog/2018/06/05/jmeter-vs-soapui/


* `How to Use JMeter Assertions in Three Easy Steps` https://www.blazemeter.com/blog/how-use-jmeter-assertions-three-easy-steps


* `how to empty or truncate a file in linux` http://www.lostsaloon.com/technology/how-to-empty-or-truncate-files-in-linux
* `???????????????? ?????????????????? ????????????` http://www.linuxcookbook.ru/books/opensuse/sec.new.bash.view.html



|   | windows  |
|---|---|
| serverUrl  | dev-api.smarttrader.com  |
| start_time  | ${__time(YMDHMS)}  |
| testPlanUrl  | ${__BeanShell(import org.apache.jmeter.services.FileServer; FileServer.getFileServer().getBaseDir();)}  |
| correlationIDFile  | ${__BeanShell(import org.apache.jmeter.services.FileServer; FileServer.getFileServer().getBaseDir();)}\start_correlationID  |
| tokenReferenceIDFile  | ${__BeanShell(import org.apache.jmeter.services.FileServer; FileServer.getFileServer().getBaseDir();)}\start_tokenReferenceID  |
| nmon_start_time  | ${__time(yyyy-MM-dd'T'HH:mm:ss,)}  |
| resultDir  | ${__BeanShell(import org.apache.jmeter.services.FileServer; FileServer.getFileServer().getBaseDir();)}\results\\${__time(YMDHMS)}  |


|   | linux  |
|---|---|
| serverUrl  | dev-api.smarttrader.com  |
| start_time  | ${__time(YMDHMS)}  |
| testPlanUrl  | ${__BeanShell(import org.apache.jmeter.services.FileServer; FileServer.getFileServer().getBaseDir();)}  |
| correlationIDFile  | ${__BeanShell(import org.apache.jmeter.services.FileServer; FileServer.getFileServer().getBaseDir();)}/conf/start_correlationId.conf  |
| tokenReferenceIDFile  | ${__BeanShell(import org.apache.jmeter.services.FileServer; FileServer.getFileServer().getBaseDir();)}/conf/start_tokenReferenceId.conf  |
| nmon_start_time  | ${__time(yyyy-MM-dd'T'HH:mm:ss,)}  |
| resultDir  | ${__BeanShell(import org.apache.jmeter.services.FileServer; FileServer.getFileServer().getBaseDir();)}/results/${__time(YMDHMS)}  |
