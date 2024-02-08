# Self-contained Lucene examples

This repository contains some examples of [Apache Lucene](https://lucene.apache.org/) features with verbose explanations
as code comments written in Markdown.

The goal is to provide code samples that can be used a few ways:

1. Read the source code. The comments should make what's going on pretty clear.
2. Open a code sample in your IDE and step through it with a debugger. Follow along with the comments as you go. Make 
changes to the code and see what happens. (Some examples include suggested changes.)
3. Read the code and documentation as a web page generated with [Docco](https://ashkenas.com/docco/) over at 
https://msfroh.github.io/lucene-university/docs/SimpleSearch.html. (Go to the "Jump to..." box in the top-right to load 
other examples.) This should feel kind of like reading a book.

## Getting started

This repository currently depends on a snapshot of Lucene 10, which requires JDK 17 or higher.

You can clone the repository and build the examples with:

```
git clone https://github.com/msfroh/lucene-university.git
cd lucene-university
./gradlew build
```

Using IntelliJ, you can use "File -> New -> Project from Existing Sources..." and point it to the location where the
code was cloned. Select "Import Project from Existing Model" and choose "Gradle" (assuming you have the Gradle plugin
installed). If you run into errors regarding class file versions, you may need to go to "File -> Project Structure..." 
to make sure that you have selected the correct JDK (17 or higher) and set an appropriate language level.

## Contributing

Contributions are welcome! Check the [GitHub issues](https://github.com/msfroh/lucene-university/issues) for requests
and suggestions for material to cover. If there is something else you think could use a worked example, feel free to
directly open a pull request with an example or create an issue requesting one.

Code examples should satisfy the following:

1. Each source file should be self-contained and should only import Lucene and Java classes. The example class should not inherit from 
anything else. If you need a small helper class, make it a `private static` inner class.
2. Each example class should have a `public static void main` method that clearly walks through the steps to demonstrate the given feature.
3. Each example should start with a comment with a large header (`// # This is title text`), and a summary explaining what the example
is about, before the `package` declaration.

## Running Visualize Point Tree on Specific Shard Path 
1. SSH into cluster and git clone repository into there
2. Run `ps aux | grep java` and grab the path that OpenSearch is using
3. Export the same path to `JAVA_HOME` but omit the `/bin/java`.
4. Run `./gradlew build` to compile files
5. Run `./gradlew run -PclassToExecute=example.points.VisualizePointTree` to run the program.

Example Output:
```
> Task :run
Tree for segment 0
0 [897249601000,897854400000] - 181463624
Finished printing segments

Deprecated Gradle features were used in this build, making it incompatible with Gradle 9.0.

You can use '--warning-mode all' to show the individual deprecation warnings and determine if they come from your own scripts or plugins.

For more on this, please refer to https://docs.gradle.org/8.5/userguide/command_line_interface.html#sec:command_line_warnings in the Gradle documentation.

BUILD SUCCESSFUL in 874ms
2 actionable tasks: 1 executed, 1 up-to-date
```

## License

All code in this repository is licensed under the Apache License, Version 2.0. See the LICENSE file in the root of the repository for the
full text of the license.
