# 12 FACTOR APP

1. Codebase
All code exists under repositories

2. Dependencies
A twelve-factor app never relies on implicit existence of system-wide packages.
Twelve-factor apps also do not rely on the implicit existence of any system
tools. This includes Curl or OpenSSL

3. CONFIG
settings should be stored in env vars.
Litmus test: should be able to be open sourced at anytime.
Deployed style shouldn't affect app
In a twelve-factor app, env vars are granular controls, each fully orthogonal
to other env vars. They are never grouped together as “environments”, but
instead are independently managed for each deploy

4. Backing services
No distinction between local and third party services. To the app, both are
attached resources, accessed via a URL or other locator/credentials stored in
the config

5. Build release run
The twelve-factor app uses strict separation between the build, release, and
run stages

6. Processes
Twelve-factor processes are stateless and share-nothing.
The twelve-factor app never assumes that anything cached in memory or on disk
will be available on a future request or job

Asset packagers (such as Jammit or django-compressor) use the filesystem as a
cache for compiled assets. A twelve-factor app prefers to do this compiling
during the build stage, such as the Rails asset pipeline, rather than at runtime

Sticky sessions are a violation of twelve-factor and should never be used or
relied upon

7. Port Binding
Note also that the port-binding approach means that one app can become the
backing service for another app, by providing the URL to the backing app as a
resource handle in the config for the consuming app

8.  Concurrency
The twelve-factor app, processes are a first class citizen.
The share-nothing, horizontally partitionable nature of twelve-factor app
processes means that adding more concurrency is a simple and reliable operation.

The array of process types and number of processes of each type is known as the
process formation

Twelve-factor app processes should never daemonize or write PID files. Instead,
rely on the operating system’s process manager

9. Disposability
The twelve-factor app’s processes are disposable, meaning they can be started
or stopped at a moment’s notice

Processes should strive to minimize startup time. Ideally, a process takes a
few seconds

Processes shut down gracefully when they receive a SIGTERM signal

10. Dev/Prod Parity
The twelve-factor app is designed for continuous deployment by keeping the gap
between development and production small

The twelve-factor developer resists the urge to use different backing services
between development and production

11. Logs
Logs have no fixed beginning or end, but flow continuously as long as the app
is operating

A twelve-factor app never concerns itself with routing or storage of its output
stream

In staging or production deploys, each process’ stream will be captured by the
execution environment, collated together with all other streams from the app,
and routed to one or more final destinations for viewing and long-term archival

Most significantly, the stream can be sent to a log indexing and analysis system
such as Splunk, or a general-purpose data warehousing system such as
Hadoop/Hive

12. Admin Processes
One-off admin processes should be run in an identical environment as the regular
long-running processes of the app. They run against a release, using the same
codebase and config as any process run against that release. Admin code must
ship with application code to avoid synchronization issues

The same dependency isolation techniques should be used on all process types
