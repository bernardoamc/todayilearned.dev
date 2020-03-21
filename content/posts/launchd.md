---
author: "Bernardo"
title: "launchd timed jobs"
date: 2020-03-21T19:45:10-04:00
tags: ["macos"]
---

TIL about scheduling timed jobs on MacOS through `launchd`.

Each launchd job is described by a separate `plist` file, meaning you can manage
launchd timed jobs by simply adding or removing a file. These files should be
placed in certain folders according to the goal of the job:

* System tasks go to:

{{< highlight bash >}}
/Library/LaunchDaemons/
{{< /highlight >}}

if they need to run **no matter if a user is logged in to the system or not**. These tasks will be started with "root" privileges.

* If they need to run **if any user** is logged in, they go to:

{{< highlight bash >}}
/Library/LaunchAgents/
{{< /highlight >}}

and will be executed with the privileges of the user that just logged in.

* If they need to run **if only you** are logged in, they go to:

{{< highlight bash >}}
~/Library/LaunchAgents/
{{< /highlight >}}

The documentation can be found [here](https://developer.apple.com/library/archive/documentation/MacOSX/Conceptual/BPSystemStartup/Chapters/CreatingLaunchdJobs.html).
Examples of timed jobs can be found [here](https://developer.apple.com/library/archive/documentation/MacOSX/Conceptual/BPSystemStartup/Chapters/ScheduledJobs.html).
