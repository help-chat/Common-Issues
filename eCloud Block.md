# eCloud Block

## Symptoms:

  - The "No expansions are available at this time" message when trying to list all expansion in game or via console.

  - Following error in console at startup or via the /papi ecloud list all:

```
[07:56:38 WARN]: [PlaceholderAPI] Plugin PlaceholderAPI v2.10.4 generated an exception while executing task 27
java.lang.NullPointerException: null
at me.clip.placeholderapi.expansion.cloud.ExpansionCloudManager.lambda$null$3(ExpansionCloudManager.java:181) ~[?:?]
at java.util.Map.forEach(Map.java:630) ~[?:1.8.0_212]
at me.clip.placeholderapi.expansion.cloud.ExpansionCloudManager.lambda$fetch$4(ExpansionCloudManager.java:172) ~[?:?]
at org.bukkit.craftbukkit.v1_14_R1.scheduler.CraftTask.run(CraftTask.java:84) ~[patched_1.14.4.jar:git-Paper-238]
at org.bukkit.craftbukkit.v1_14_R1.scheduler.CraftAsyncTask.run(CraftAsyncTask.java:54) ~[patched_1.14.4.jar:git-Paper-238]
at com.destroystokyo.paper.ServerSchedulerReportingWrapper.run(ServerSchedulerReportingWrapper.java:22) ~[patched_1.14.4.jar:git-Paper-238]
at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1149) [?:1.8.0_212]
at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624) [?:1.8.0_212]
at java.lang.Thread.run(Thread.java:748) [?:1.8.0_212]
```


## Cause:

  - PlaceholderAPI requires a connection to the api found at api.extendedclip.com/v2, some hosts will block the plugins attempt at making a connection to the URL.
  - The eCloud has gone offline. Unlikely but still possible.

## Solution:
  - If the eCloud is actually down which you can check by just going to api.extendedclip.com/v2 in browser, then notify an admin of the outage if a public announcement has yet to be made.
  - If the eCloud is up, the user will need to either discuss with their hosting provider to unblock the connection to the api or they can simply manually download expansions from https://placeholderapi.com/ecloud and place them in their /plugins/PlaceholderAPI/expansions/ folder. However the error will still come up each reboot unless they disable the use of the ecloud in the PAPI config.
