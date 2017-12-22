
Installation inside Jira itself
===============================

If there is no webserver or if the webserver is on a different server without access to a psql client, then you might consider to add the CGI to the Jira installation itself.

In /opt/atlassian/jira/conf/web.xml uncomment these two existing sections and add the parameter "executeable":
```
<servlet>
    <servlet-name>cgi</servlet-name>
    <servlet-class>org.apache.catalina.servlets.CGIServlet</servlet-class>
    <init-param>
      <param-name>cgiPathPrefix</param-name>
      <param-value>WEB-INF/cgi</param-value>
    </init-param>
    <init-param>
      <param-name>executable</param-name>
      <param-value>bash</param-value>
    </init-param>
    <load-on-startup>5</load-on-startup>
</servlet>

<servlet-mapping>
    <servlet-name>cgi</servlet-name>
    <url-pattern>/cgi-bin/*</url-pattern>
</servlet-mapping>
```

Then add the attribute privileged="true" to /opt/atlassian/jira/conf/server.xml:
```
<Context privileged="true" path="" docBase="${catalina.home}/atlassian-jira" reloadable="false" useHttpOnly="true">
```

Now create the directory /opt/atlassian/jira/atlassian-jira/WEB-INF/cgi and copy the script into it. 

A script name as9lL7f.ics would be a poor mans password protection.
