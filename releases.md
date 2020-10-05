# Releases

## 10/5/2020 ##


On **October 19th, 2020**, there will be a change to the Windows image that is used for new MPS builds from *“Windows Server 2019 Datacenter with Containers”* to *“[smalldisk] Windows Server, version 1809, with Containers”*. This change will have NO effect on existing builds or running servers which will continue to run using the old image. The new image should be identical in most respects, but it prunes rarely used files. In testing, this new image speeds VM creation times and allows additional hosting options to be leveraged which can further reduce creation times.

We strongly encourage you to use these two weeks to create a test build so you can validate that this change will not interfere with your services.

Please follow these instructions to access the new image:

- Container based builds: You should select the option *“Windows Server Core Preview”* on the UI page, or set the value of the ContainerFlavor property in your CreateBuild request to *“ManagedWindowsServerCorePreview”*
- Process based builds: You should set the property IsOSPreview to true on your CreateBuild requests, this is a new property. This property will be available in the PlayFab SDK by October 12, 2020.  Until then, you must set the property via the API.Or you may generate your own SDK independently at https://playfab.visualstudio.com/pf-main/_wiki/wikis/pf-main.wiki/318/Generating-the-SDK-Locally

This has NO impact for those of you running on Linux.

Going forward, we will continue to use the preview OS to roll out windows patches and any other OS Image updates before making them to the “Standard” OS image. We will always announce changes that could be breaking ahead of time, but we encourage you to always run the preview OS image in your test environments to catch regressions before they reach your retail deployments.