---
layout: default
title: Example Walkthrough
nav_order: 99
---

# Project setup

To illustrate the logic behinde the Clean process we will be walking through an example, here is the content browser:

![image](https://user-images.githubusercontent.com/21221169/221209145-b010363c-59ae-4ad9-80a8-f76d11fb16bc.png)

We will consider the following:
- `MyLevel` is marked as a [Core Asset](core-assets#what-are-core-assets).
- `MyLevel` references `MyBlueprint` which references `MyMaterial`.
- `NotMyBlueprint` references `NotMyMaterial`.
- `UnusedMaterial` has no references.

Reference Viewer explanations:

![image](https://user-images.githubusercontent.com/21221169/221206255-4d1dba40-bfdd-4ddf-b1f5-374ad23f342c.png)

![image](https://user-images.githubusercontent.com/21221169/221206554-1f5bb389-f37a-4edb-9c5d-3e1ceebf2b95.png)

# Project state

![image](https://user-images.githubusercontent.com/21221169/221210154-620318e5-66e3-4037-9a68-91edbe76a2ff.png)

Since only `MyLevel` is marked as [Core Asset](core-assets#what-are-core-assets) it's the only one showing up in the [Core Assets List](dashboard#core-assets-list). `MyBlueprint` and `MyMaterial` are depedencies of `MyLevel`, therefore will be consired used.

In the [Unused Assets list](dashboard#unused-assets-list) we can find `NotMyBlueprint`, `NotMyMaterial` and `UnusedMaterial`. Even if `NotMyMaterial` is referenced by `NotMyBlueprint`, both will get deleted, because they are not Core Assets/referenced by a Core Asset.

# Report Result

As expected in the [Cleanup Report](cleanup-unused#what-is-the-cleanup-report) we get all the assets listed as unused in the dashboard.

![image](https://user-images.githubusercontent.com/21221169/221212231-5f43a05a-704a-4fe1-a81d-17bacc6d93da.png)

# Delete Result

After initiating the deletion of the unused assets, we get a warning about assets still beeing referenced. 

This normal and can have various reasons. The most common is the blueprint is currently open or was recently edited. 

The assets can be safely deleted with no errors during the process.

![image](https://user-images.githubusercontent.com/21221169/221211846-edf327a1-e51c-4bfd-8767-8724b24e4d6e.png)
