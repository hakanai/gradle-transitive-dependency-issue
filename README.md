Dependencies for `a` are missing the dependency declared through project `c`:

```
$ ./gradlew :a:dependencies --configuration runtimeClasspath

> Task :a:dependencies

------------------------------------------------------------
Project :a
------------------------------------------------------------

runtimeClasspath - Runtime classpath of source set 'main'.
+--- project :b
|    \--- org.jdom:jdom2:2.0.6
\--- project :c
     \--- org.jdom:jdom2:2.0.6

(*) - dependencies omitted (listed previously)

A web-based, searchable dependency report is available by adding the --scan option.

BUILD SUCCESSFUL in 0s
1 actionable task: 1 executed
```

Dependencies for `c` _do_ show the dependency:

```
$ ./gradlew :c:dependencies --configuration runtimeClasspath

> Task :c:dependencies

------------------------------------------------------------
Project :c
------------------------------------------------------------

runtimeClasspath - Runtime classpath of source set 'main'.
\--- org.jdom:jdom2:2.0.6
     \--- jaxen:jaxen:1.1.6

A web-based, searchable dependency report is available by adding the --scan option.

BUILD SUCCESSFUL in 1s
1 actionable task: 1 executed
```

