# <font color="#007042">**Appendix D. Gradle Command Line**</font>

The gradle command has the following usage:

    gradle [option...] [task...]

The command-line options available for the gradle command are listed below:

    -?, -h, --help
Shows a help message.

    -a, --no-rebuild
Do not rebuild project dependencies.

    --all
Shows additional detail in the task listing. See Section 11.6.2, “Listing tasks”.

    -b, --build-file
Specifies the build file. See Section 11.5, “Selecting which build to execute”.

    -c, --settings-file
Specifies the settings file.

    --continue
Continues task execution after a task failure.

    --configure-on-demand (incubating)
Only relevant projects are configured in this build run. This means faster builds for large multi-projects. See Section 56.1.1.1, “Configuration on demand”.

    -D, --system-prop
Sets a system property of the JVM, for example -Dmyprop=myvalue. See Section 14.2, “Gradle properties and system properties”.

    -d, --debug
Log in debug mode (includes normal stacktrace). See Chapter 18, Logging.

    -g, --gradle-user-home
Specifies the Gradle user home directory. The default is the .gradle directory in the user's home directory.

    --gui
Launches the Gradle GUI. See Chapter 12, Using the Gradle Graphical User Interface.

    -I, --init-script
Specifies an initialization script. See Chapter 60, Initialization Scripts.

    -i, --info
Set log level to info. See Chapter 18, Logging.

    -m, --dry-run
Runs the build with all task actions disabled. See Section 11.7, “Dry Run”.

    --no-color
Do not use color in the console output.

    --offline
Specifies that the build should operate without accessing network resources. See Section 50.9.2, “Command line options to override caching”.

    -P, --project-prop
Sets a project property of the root project, for example -Pmyprop=myvalue. See Section 14.2, “Gradle properties and system properties”.

    -p, --project-dir
Specifies the start directory for Gradle. Defaults to current directory. See Section 11.5, “Selecting which build to execute”.

    --parallel (incubating)
Build projects in parallel. Gradle will attempt to determine the optimal number of executor threads to use. This option should only be used with decoupled projects (see Section 56.9, “Decoupled Projects”).

    --parallel-threads (incubating)
Build projects in parallel, using the specified number of executor threads. For example--parallel-threads=3. This option should only be used with decoupled projects (see Section 56.9, “Decoupled Projects”).

    --profile
Profiles build execution time and generates a report in the buildDir/reports/profile directory. See Section 11.6.7, “Profiling a build”.

    --project-cache-dir
Specifies the project-specific cache directory. Default value is .gradle in the root project directory. See Section 14.6, “Caching”.

    -q, --quiet
Log errors only. See Chapter 18, Logging.

    --recompile-scripts
Specifies that cached build scripts are skipped and forced to be recompiled. See Section 14.6, “Caching”.

    --refresh-dependencies
Refresh the state of dependencies. See Section 50.9.2, “Command line options to override caching”.

    --rerun-tasks
Specifies that any task optimization is ignored.

    -S, --full-stacktrace
Print out the full (very verbose) stacktrace for any exceptions. See Chapter 18, Logging.

    -s, --stacktrace
Print out the stacktrace also for user exceptions (e.g. compile error). See Chapter 18, Logging.

    -u, --no-search-upwards
Don't search in parent directories for a settings.gradle file.

    -v, --version
Prints version info.

    -x, --exclude-task
Specifies a task to be excluded from execution. See Section 11.2, “Excluding tasks”.

The above information is printed to the console when you execute gradle -h.

### <font color="#007042">**D.1. Deprecated command-line options**</font>
The following options are deprecated and will be removed in a future version of Gradle:

    -C, --cache
(deprecated) Specifies how compiled build scripts should be cached. Possible values are: rebuild or on. Default value is on. You should use --recompile-scripts instead.

    --no-opt
(deprecated) Specifies to ignore all task optimization. You should use --rerun-tasks instead.

    --refresh
(deprecated) Refresh the state of resources of the type(s) specified. Currently only dependencies is supported. You should use --refresh-dependencies instead.

### <font color="#007042">**D.2. Daemon command-line options:**</font>
The Chapter 19, The Gradle Daemon contains more information about the daemon. For example it includes information how to turn on the daemon by default so that you can avoid using --daemon all the time.

    --daemon
Uses the Gradle daemon to run the build. Starts the daemon if not running or existing daemon busy. Chapter 19, The Gradle Daemon contains more detailed information when new daemon processes are started.

    --foreground
Starts the Gradle daemon in the foreground. Useful for debugging or troubleshooting because you can easily monitor the build execution.

    --no-daemon
Do not use the Gradle daemon to run the build. Useful occasionally if you have configured Gradle to always run with the daemon by default.

    --stop
Stops the Gradle daemon if it is running. You can only stop daemons that were started with the Gradle version you use when running --stop.

### <font color="#007042">**D.3. System properties**</font>
The following system properties are available for the gradle command. Note that command-line options take precedence over system properties.

gradle.user.home
Specifies the Gradle user home directory.

The Section 20.1, “Configuring the build environment via gradle.properties” contains specific information about Gradle configuration available via system properties.

### <font color="#007042">**D.4. Environment variables**</font>
The following environment variables are available for the gradle command. Note that command-line options and system properties take precedence over environment variables.

GRADLE_OPTS
Specifies command-line arguments to use to start the JVM. This can be useful for setting the system properties to use for running Gradle. For example you could set GRADLE_OPTS="-Dorg.gradle.daemon=true" to use the Gradle daemon without needing to use the --daemon option every time you run Gradle. Section 20.1, “Configuring the build environment via gradle.properties” contains more information about ways of configuring the daemon without using environmental variables, e.g. in more maintainable and explicit way.

GRADLE_USER_HOME
Specifies the Gradle user home directory.

