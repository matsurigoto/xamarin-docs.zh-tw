---
title: Xamarin.Essentials：Accelerometer
description: Xamarin.Essentials 中的 Accelerometer 類別可讓您監視裝置的加速度感應器，該感應器指出裝置在三維空間中的加速度。
ms.assetid: 97883573-F0D9-4854-AC7C-A654814401C5
author: jamesmontemagno
ms.author: jamont
ms.date: 05/04/2018
ms.openlocfilehash: 53e7ca70184270662d27043387da836ad44432fe
ms.sourcegitcommit: 47709db4d115d221e97f18bc8111c95723f6cb9b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/13/2018
ms.locfileid: "40184425"
---
# <a name="xamarinessentials-accelerometer"></a>Xamarin.Essentials：Accelerometer

![發行前的 NuGet](~/media/shared/pre-release.png)

**Accelerometer** 類別可讓您監視裝置的加速度感應器，該感應器指出裝置在三維空間中的加速度。

## <a name="using-accelerometer"></a>使用 Accelerometer

在類別中新增對 Xamarin.Essentials 的參考：

```csharp
using Xamarin.Essentials;
```

Accelerometer 功能的運作方式是呼叫 `Start` 和 `Stop` 方法，以觀察加速度的變化。 所有變化都會透過 `ReadingChanged` 事件傳回。 以下是範例使用方式：

```csharp

public class AccelerometerTest
{
    // Set speed delay for monitoring changes.
    SensorSpeed speed = SensorSpeed.UI;

    public AccelerometerTest()
    {
        // Register for reading changes, be sure to unsubscribe when finished
        Accelerometer.ReadingChanged += Accelerometer_ReadingChanged;
    }

    void Accelerometer_ReadingChanged(object sender, AccelerometerChangedEventArgs e)
    {
        var data = e.Reading;
        Console.WriteLine($"Reading: X: {data.Acceleration.X}, Y: {data.Acceleration.Y}, Z: {data.Acceleration.Z}");
        // Process Acceleration X, Y, and Z
    }

    public void ToggleAccelerometer()
    {
        try
        {
            if (Accelerometer.IsMonitoring)
              Accelerometer.Stop();
            else
              Accelerometer.Start(speed);
        }
        catch (FeatureNotSupportedException fnsEx)
        {
            // Feature not supported on device
        }
        catch (Exception ex)
        {
            // Other error has occurred.
        }
    }
}
```

Accelerometer 讀數會以 G 為單位回報。G 是一個重力單位，等於地球重力場所作用的重力 (9.81 m/s^2)。

座標系統的定義，相對於手機螢幕的預設方向。 當裝置的螢幕方向變更時，軸不會換位。

X 軸是指向右方的水平軸，Y 軸是指向上方的垂直軸，Z 軸則指向螢幕正面的外側。 在這個系統中，螢幕背面的座標會有負的 Z 值。

例如：

* 當裝置平放在桌上，然後從裝置左側往右側推時，x 加速度值為正。

* 當裝置平放在桌上時，加速度值為 +1.00 G 或 (+9.81 m/s^2)，也就是裝置加速度 (0 m/s^2) 減掉重力 (-9.81 m/s^2)，然後以 G 標準化。

* 當裝置平放在桌上，然後以 A m/s^2 的加速度向上空推動時，加速度值等於 A+9.81，也就是裝置加速度 (+A m/s^2) 減掉重力 (-9.81 m/s^2)，然後以 G 標準化。

[!include[](~/essentials/includes/sensor-speed.md)]

## <a name="api"></a>API

- [Accelerometer 原始程式碼](https://github.com/xamarin/Essentials/tree/master/Xamarin.Essentials/Accelerometer)
- [Accelerometer API 文件](xref:Xamarin.Essentials.Accelerometer)
