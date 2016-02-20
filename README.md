
# Configure assignments for Princeton University's Algorithms class using Maven
### custom checkstyle configuration file
i forced mavent to respect my checkstyle configuration file. first, forget about the configuration element because i could not get it to work.

```xml
<configuration>
    <configLocation>http://stackoverflow.com/questions/12513277/how-can-i-configure-checkstyle-in-maven</configLocation>
</configuration>
```
instead, use a property to accomplish this goal

```xml
<properties>
    <checkstyle.config.location>${project.basedir}/src/main/resources/checkstyle.xml</checkstyle.config.location>
</properties>
```
next, you have to execute the build with maven.
```sh
$ mvn clean install
```
due to a weird message (http://stackoverflow.com/questions/12038238/unable-to-locate-source-xref-to-link-to), you have to execute this with maven.
```sh
$ mvn jxr:jxr
```
next, you need to execute checkstyle via maven.
```sh
$ mvn checkstyle:checkstyle
```
of course, everything good seems to happen if you just run the following:
```sh
$ mvn site
```
except that you will need to run your own web server
```sh
$ python3 -m http.server
```
### Testing
 - gulp

### TODOs
 - write MOAR Tests!
 - write MOAR Comments!

Thank you to [Joe McCann] for creating [DILLINGER].

   [DILLINGER]: <http://dillinger.io/>
   [Joe McCann]: <https://github.com/joemccann>
