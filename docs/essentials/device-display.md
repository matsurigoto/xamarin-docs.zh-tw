---
title: Xamarin.Essentials 裝置顯示的資訊
description: DeviceDisplay 類別會提供裝置的螢幕度量應用程式的相關資訊上執行。
ms.assetid: 2821C908-C613-490D-8E8C-1BD3269FCEEA
author: jamesmontemagno
ms.author: jamont
ms.date: 05/04/2018
ms.openlocfilehash: 570fb6cf3eadfbbc7e189f875498d3cea0bc1514
ms.sourcegitcommit: 0a72c7dea020b965378b6314f558bf5360dbd066
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/09/2018
---
# <a name="xamarinessentials-device-display-information"></a>Xamarin.Essentials 裝置顯示的資訊

![發行前版本的 NuGet](~/media/shared/pre-release.png)

**DeviceDisplay**類別會提供應用程式執行裝置的螢幕度量資訊。

## <a name="using-devicedisplay"></a>使用 DeviceDisplay

在您類別中加入 Xamarin.Essentials 的參考：

```csharp
using Xamarin.Essentials;
```

## <a name="screen-metrics"></a>螢幕度量

除了基本裝置資訊**DeviceDisplay**類別包含裝置的螢幕和方向的相關資訊。

```csharp
// Get Metrics
var metrics = DeviceDisplay.ScreenMetrics;

// Orientation (Landscape, Portrait, Square, Unknown)
var orientation = metrics.Orientation;

// Rotation (0, 90, 180, 270)
var rotation = metrics.Rotation;

// Width (in pixels)
var width = metrics.Width;

// Height (in pixels)
var height = metrics.Height;

// Screen density
var density = metrics.Density;
```

**DeviceDisplay**類別也會公開和可供訂閱所觸發的事件，每當任何畫面公制的變更的事件：

```csharp
public class ScreenMetricsTest
{
    public ScreenMetricsTest()
    {
        // Subscribe to changes of screen metrics
        DeviceDisplay.ScreenMetricsChanaged += OnScreenMetricsChanged;
    }

    void OnScreenMetricsChanged(ScreenMetricsChanagedEventArgs  e)
    {
        // Process changes
        var metrics = e.Metrics;
    }
}
```

## <a name="api"></a>API

- [DeviceDisplay 原始程式碼](https://github.com/xamarin/Essentials/tree/master/Essentials/DeviceDisplay)
- [DeviceDisplay API 文件](xref:Xamarin.Essentials.DeviceDisplay)