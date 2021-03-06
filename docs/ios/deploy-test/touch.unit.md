---
title: 單元測試 Xamarin.iOS 應用程式
description: 本文件提供如何對 Xamarin.iOS 應用程式進行單元測試的概觀。 描述如何建立單元測試專案、撰寫測試和執行測試。
ms.prod: xamarin
ms.assetid: BD959779-3239-79B6-5289-3A9ECDFBD973
ms.technology: xamarin-ios
author: bradumbaugh
ms.author: brumbaug
ms.date: 03/19/2017
ms.openlocfilehash: ce2b452d50222ac3561dab5b76915b7ae634934b
ms.sourcegitcommit: ea1dc12a3c2d7322f234997daacbfdb6ad542507
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/05/2018
ms.locfileid: "34785459"
---
# <a name="unit-testing-xamarinios-apps"></a>單元測試 Xamarin.iOS 應用程式

本文件說明如何為 Xamarin.iOS 專案建立單元測試。
為 Xamarin.iOS 進行單元測試時，是透過使用 Touch.Unit 架構來完成。該架構包含 iOS 測試執行器，以及修改過的 NUnit 版本 (稱為 [Touch.Unit](https://github.com/xamarin/Touch.Unit))；此版本會提供一組熟悉的 API，以供編寫單元測試之用。

## <a name="setting-up-a-test-project"></a>設定測試專案

# <a name="visual-studio-for-mactabvsmac"></a>[Visual Studio for Mac](#tab/vsmac)

若要為您的專案設定單元測試架構，只需要將 [iOS 單元測試專案] 類型的專案新增至您的方案即可。 在您的方案上按一下滑鼠右鍵，然後選取 [新增] > [新增專案] 即可完成此動作。 從清單中選取 [iOS] > [測試] > [Unified API] > [iOS 單元測試專案] (您可以選擇 C# 或 F#)。

![](touch.unit-images/00.png "選擇 C# 或 F#")

# <a name="visual-studiotabvswin"></a>[Visual Studio](#tab/vswin)

若要為您的專案設定單元測試架構，只需要將 [iOS 單元測試專案] 類型的專案新增至您的方案即可。 在您的方案上按一下滑鼠右鍵，然後選取 [新增] > [新增專案] 即可完成此動作。從清單中選取 [Visual C#] > [iOS] > [單元測試應用程式 (iOS)]。

![](touch.unit-images/00a.png "單元測試應用程式 iOS")

-----

上面的動作將會建立其中包含基本執行器程式，並會參考新 MonoTouch.NUnitLite 組件的基本專案，您的專案看起來像這樣：

# <a name="visual-studio-for-mactabvsmac"></a>[Visual Studio for Mac](#tab/vsmac)

![](touch.unit-images/01.png "[方案總管] 中的專案")

# <a name="visual-studiotabvswin"></a>[Visual Studio](#tab/vswin)

![](touch.unit-images/01a.png "[方案總管] 中的專案")

-----

`AppDelegate.cs` 類別包含測試執行器，而且它看起來像這樣：

```csharp
[Register ("AppDelegate")]
public partial class AppDelegate : UIApplicationDelegate
{
        UIWindow window;
        TouchRunner runner;

        public override bool FinishedLaunching (UIApplication app, NSDictionary options)
        {
                // create a new window instance based on the screen size
                window = new UIWindow (UIScreen.MainScreen.Bounds);
                runner = new TouchRunner (window);

                // register every tests included in the main application/assembly
                runner.Add (System.Reflection.Assembly.GetExecutingAssembly ());

                window.RootViewController = new UINavigationController (runner.GetViewController ());

                // make the window visible
                window.MakeKeyAndVisible ();

                return true;
        }
}
```

## <a name="writing-some-tests"></a>編寫一些測試

既然您已經備妥基本的殼層，您應該編寫您的第一組測試。

若要編寫測試，請建立已套用 `[TestFixture]` 屬性的類別。 您應該在每個 TestFixture 類別內，將 `[Test]` 屬性套用至您希望測試執行器叫用的每個方法。 實際的測試固件可以存在於測試專案中的任何檔案。

若要快速開始，請選取 [加入]/[加入新檔案]，然後在 Xamarin.iOS 群組中選取 [UnitTests]。 這將會新增包含一個通過測試、一個失敗測試，以及一個忽略測試的基本架構檔案，它看起來像這樣：

```csharp
using System;
using NUnit.Framework;

namespace Fixtures {

        [TestFixture]
        public class Tests {

                [Test]
                public void Pass ()
                {
                        Assert.True (true);
                }

                [Test]
                public void Fail ()
                {
                        Assert.False (true);
                }

                [Test]
                [Ignore ("another time")]
                public void Ignore ()
                {
                        Assert.True (false);
                }
        }
}
```

## <a name="running-your-tests"></a>執行您的測試

若要執行此專案，請在方案內以滑鼠右鍵按一下該專案，然後選取 [Debug Item] \(針對項目進行偵錯\)或 [Run Item] \(執行項目\)。

測試執行器可讓您查看已登錄的測試，並個別選取可以執行的測試。

[![](touch.unit-images/02.png "已註冊之測試的清單")](touch.unit-images/02.png#lightbox) 

[![](touch.unit-images/03.png "個別的文字")](touch.unit-images/03.png#lightbox) 

[![](touch.unit-images/04.png "執行結果")](touch.unit-images/04.png#lightbox)

您可以透過從巢狀檢視中選取測試固件來執行個別的測試固件，或者您可以使用 [Run Everything] \(全部執行\) 來執行所有測試。 如果您執行預設測試，應該包括一個通過測試、一個失敗測試以及一個忽略測試。 這是報表的外觀，而且您可以直接向下切入失敗測試，並找出有關失敗的詳細資訊：

[![](touch.unit-images/05.png "範例報表")](touch.unit-images/05.png#lightbox) [![](touch.unit-images/05.png "範例報表")](touch.unit-images/05.png#lightbox) [![](touch.unit-images/05.png "範例報表")](touch.unit-images/05.png#lightbox)

您也可以查看 IDE 中的 [應用程式輸出] 視窗，以了解正在執行哪些測試及其目前狀態。

## <a name="writing-new-tests"></a>編寫新的測試

NUnitLite 是修改後的 NUnit 版本，稱為 [Touch.Unit](https://github.com/xamarin/Touch.Unit) 專案。 它是適用於 .NET 的輕量型測試架構，以 [NUnit](http://nunit.com/) 的構想為基礎，並提供其功能的子集。
它使用最少的資源，並將在資源有限的平台上執行 (例如，用於內嵌和行動裝置開發的平台)。 您可以在 Xamarin.iOS 中[瀏覽可用的 NUnitLite API](https://developer.xamarin.com/api/namespace/NUnitLite/)。 如果有單元測試範本所提供的基本架構，您的主要進入點就是[判斷提示類別](https://developer.xamarin.com/api/type/NUnit.Framework.Assert/)方法。

除了「判斷提示類別」方法之外，單元測試功能會在 NUnitLite 所屬的下列命名空間上分割：

-   [NUnit.Framework](https://developer.xamarin.com/api/namespace/NUnit.Framework/)
-   [NUnit.Constraints](https://developer.xamarin.com/api/namespace/NUnit.Framework.Constraints/)
-   [NUnitLite](https://developer.xamarin.com/api/namespace/NUnitLite/)
-   [NUniteLite.Runner](https://developer.xamarin.com/api/namespace/NUnitLite.Runner/)


Xamarin.iOS 專屬的單元測試執行器記載於此處：

-   [NUnit.UI.TouchRunner](https://developer.xamarin.com/api/type/NUnit.UI.TouchRunner/)
