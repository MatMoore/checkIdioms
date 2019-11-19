# checkIdioms checkstyle plugin

This is an experiment at writing a plugin for checkstyle

## End goal

This plugin should search legacy code for coding patterns that can be expressed in a more idiomatic way in modern Java.

For example, since Java 7 it's better to use [try-with-resources](https://docs.oracle.com/javase/tutorial/essential/exceptions/tryResourceClose.html)
instead of closing resources in a finally block.

[Most loop based code can be written more declaratively using filters and maps](https://ncrcoe.gitbooks.io/java-for-small-teams/specifics/500_prefer_maps_and_filters_to_imperative_loops.html).

If not, [`for each` can be used instead of indexed for loops or iterators](https://ncrcoe.gitbooks.io/java-for-small-teams/specifics/400_prefer_for_each_loops_to_for_loops.html).

Since Java 9, there are many [one liners for things that used to require verbose blocks of code](https://ncrcoe.gitbooks.io/java-for-small-teams/specifics/1100_one_liners.html).


## How to test

```
java -classpath ./build/libs/checkIdioms-1.0-SNAPSHOT.jar:checkstyle-${projectVersion}-all.jar \
    com.puppycrawl.tools.checkstyle.Main -c example-config.xml myproject
```

See https://checkstyle.sourceforge.io/writingchecks.html#Integrate_your_Check for more details.

## Versioning
This is still a work in progress. Don't rely on it working.

## Further reading
This project was inspired by [Source Code Rejuvenation is not Refactoring](http://www.stroustrup.com/sofsem10.pdf).

## License
All code is free to use under the [MIT license](LICENSE).
