---
title: Dock
description: description for Dock Controls.
author: CDiaz-MS
ms.author: cadia 
ms.date: 01/12/2021
keywords: Unity,HoloLens, HoloLens 2, Mixed Reality, development, MRTK,
---

# Dock &#8212; MRTK2

![Dock](../images/dock/MRTK_UX_Dock_Main.png)

This control enables moving objects in and out of predetermined positions, to create palettes, shelves and navigation bars.

## Features

- Supports any number of dock positions and layouts (works great with [`GridObjectCollection`](xref:Microsoft.MixedReality.Toolkit.Utilities.GridObjectCollection?view=mixed-reality-toolkit-unity-2020-dotnet-2.8.0&preserve-view=true))
- Docked objects automatically move away to make space for new objects
- Objects scale to fit the docked space, then resize to their original position when dragged out.

## Getting started with Dock

- Create a GameObject with the Dock component and add some children GameObjects to it.
- Add the DockPosition component to each of the children.
- Add the Dockable component to any number of objects in the scene to allow them to be docked. They must have the [`ObjectManipulator`](xref:Microsoft.MixedReality.Toolkit.UI.ObjectManipulator?view=mixed-reality-toolkit-unity-2020-dotnet-2.8.0&preserve-view=true) component and a Collider as well.
- *Optional:* use a [`GridObjectCollection`](xref:Microsoft.MixedReality.Toolkit.Utilities.GridObjectCollection?view=mixed-reality-toolkit-unity-2020-dotnet-2.8.0&preserve-view=true) to the Dock to automatically lay out the DockPositions.

### Prerequisites

- Every dockable object must have a collider with an [`ObjectManipulator`](xref:Microsoft.MixedReality.Toolkit.UI.ObjectManipulator?view=mixed-reality-toolkit-unity-2020-dotnet-2.8.0&preserve-view=true) or [`ManipulationHandler`](xref:Microsoft.MixedReality.Toolkit.UI.ManipulationHandler?view=mixed-reality-toolkit-unity-2020-dotnet-2.8.0&preserve-view=true).
- If you want an object to start Docked when the scene loads, assign it to any DockPosition's docked object property.

## How it works

The Dockable component builds upon manipulation events to allow dragged objects to be docked and undocked in specific positions. The placement is determined by the closest overlapping triggered DockPosition to the dragged object, so both objects need to have Colliders for the trigger to activate.
