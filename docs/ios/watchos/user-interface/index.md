---
title: watchOS Xamarin 中的使用者介面控制項
description: 本文件說明的各種控制項，可供 watchOS 使用者介面中使用。 它提供的標籤、 按鈕、 參數、 滑桿、 影像、 分隔符號、 對應和更多的描述。
ms.prod: xamarin
ms.assetid: EDFAD203-02EA-4A74-9CE2-7B8513BC90E1
ms.technology: xamarin-ios
author: bradumbaugh
ms.author: brumbaug
ms.date: 09/19/2016
ms.openlocfilehash: b56cfed8f045d824996a004539533b27d66c8cb1
ms.sourcegitcommit: ea1dc12a3c2d7322f234997daacbfdb6ad542507
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/05/2018
ms.locfileid: "34791406"
---
# <a name="watchos-user-interface-controls-in-xamarin"></a>watchOS Xamarin 中的使用者介面控制項

[ **WatchKitCatalog** ](https://github.com/xamarin/monotouch-samples/tree/master/watchOS/WatchKitCatalog)範例會示範各種 watchOS 控制項。 應用程式的分鏡腳本如下所示 （按一下以顯示比例）：

[![](images/storyboard-sml.png "範例 watchOS 版面配置")](images/storyboard.png#lightbox)

所有控制項的程式設計名稱前面會加上`WKInterface`（例如。 `WKInterfaceLabel`, `WKInterfaceButton`).

|控制項|描述|螢幕擷取畫面|
|---|---|---|
|ThisAddIn|使用`SetText`和其他屬性，以控制標籤控制項中文字的外觀。 `NSAttributedString` 也支援。<br />[類別目錄的程式碼](https://github.com/xamarin/ios-samples/blob/master/watchOS/WatchKitCatalog/WatchKit3Extension/LabelDetailController.cs)|![](Images/label.png)|
|按鈕|建立並設定屬性中的分鏡腳本。 Ctrl + 拖曳來新增`Action`實作按一下時的處理常式。<br />[類別目錄的程式碼](https://github.com/xamarin/ios-samples/blob/master/watchOS/WatchKitCatalog/WatchKit3Extension/ButtonDetailController.cs)|![](Images/button.png)|
|參數|使用`SetOn`控制切換狀態。<br />[類別目錄的程式碼](https://github.com/xamarin/ios-samples/blob/master/watchOS/WatchKitCatalog/WatchKit3Extension/SwitchDetailController.cs)|![](Images/switch.png)|
|滑桿|可能會有許多不同的樣式。<br />[類別目錄的程式碼](https://github.com/xamarin/ios-samples/blob/master/watchOS/WatchKitCatalog/WatchKit3Extension/SliderDetailController.cs)|![](Images/slider.png)|
|Image|使用`myImage.SetImage("MyWatchImage")`載入監看式 上的映像或`WKInterfaceDevice.CurrentDevice.AddCachedImage`進行快取上監看式重複使用。<br />[影像控制項文件](~/ios/watchos/user-interface/image.md)<br />[類別目錄的程式碼](https://github.com/xamarin/ios-samples/blob/master/watchOS/WatchKitCatalog/WatchKit3Extension/ImageDetailController.cs)|![](Images/image.png)|
|Separator|您可以使用分隔符號，幫助您建立具吸引力的監看式 Ui。<br />[類別目錄的程式碼](https://github.com/xamarin/ios-samples/blob/master/watchOS/WatchKitCatalog/WatchKit3Extension/SeparatorDetailController.cs)|![](Images/separator.png)| 
|對應|地圖影像會以靜態方式顯示在 監看式，但是您可以控制其外觀，包括新增 pin 的許多層面。<br />[類別目錄的程式碼](https://github.com/xamarin/ios-samples/blob/master/watchOS/WatchKitCatalog/WatchKit3Extension/MapDetailController.cs)|![](Images/map.png)|
|影片 & InlineMove|影片可以開啟在其本身或內嵌<br />[類別目錄的程式碼](https://github.com/xamarin/ios-samples/blob/master/watchOS/WatchKitCatalog/WatchKit3Extension/MovieDetailController.cs)|![](Images/movie.png)|
|群組|使用群組來幫助您建立具吸引力的監看式 Ui。<br />[類別目錄的程式碼](https://github.com/xamarin/ios-samples/blob/master/watchOS/WatchKitCatalog/WatchKit3Extension/GroupDetailController.cs)|![](Images/group.png)|
|資料表|在 iOS 上資料表的簡化的版本。 實作`DidSelectRow`回應使用者選取 （或使用 segue）。<br />[表格控制項文件](~/ios/watchos/user-interface/table.md)<br />[類別目錄的程式碼](https://github.com/xamarin/ios-samples/blob/master/watchOS/WatchKitCatalog/WatchKit3Extension/Table%20Detail%20Controller/TableDetailController.cs)|![](Images/table.png)|
|裝置|`WKInterfaceDevice.CurrentDevice` 包含屬性，例如`ScreenBounds`， `ScreenScale`，和`PreferredContentSizeCategory`。<br />[類別目錄的程式碼](https://github.com/xamarin/ios-samples/blob/master/watchOS/WatchKitCatalog/WatchKit3Extension/DeviceDetailController.cs)|![](Images/device.png)|
|[Menu](~/ios/watchos/user-interface/menu.md)|在分鏡腳本中定義的強制按下功能表和實作程式碼中的每個按鈕的動作。<br />[功能表控制項 （強制觸控） 文件](~/ios/watchos/user-interface/menu.md)<br />[類別目錄的程式碼](https://github.com/xamarin/ios-samples/blob/master/watchOS/WatchKitCatalog/WatchKit3Extension/ControllerDetailController.cs)|![](Images/controller.png)|
|文字輸入|使用`PresentTextInputController`和`WKTextInputMode`列舉型別。<br />[文字輸入文件](~/ios/watchos/user-interface/text-input.md)<br />[類別目錄的程式碼](https://github.com/xamarin/ios-samples/blob/master/watchOS/WatchKitCatalog/WatchKit3Extension/TextInputController.cs)|![](Images/textinput.png)|
|數位皇冠|數位皇冠可以用來驅動選擇器，或在程式碼中可追蹤它的旋轉。<br />[類別目錄的程式碼](https://github.com/xamarin/ios-samples/blob/master/watchOS/WatchKitCatalog/WatchKit3Extension/CrownDetailController.cs)|![](Images/digital-crown.png)|
|軌跡|有四種類型的筆勢辨識可加入至場景： 點選、 撥動、 取景位置調整和 LongPress。<br />[類別目錄的程式碼](https://github.com/xamarin/ios-samples/blob/master/watchOS/WatchKitCatalog/WatchKit3Extension/GestureDetailController.cs)|![](Images/gestures.png)|


## <a name="related-links"></a>相關連結

- [WatchKitCatalog （範例）](https://developer.xamarin.com/samples/monotouch/watchOS/WatchKitCatalog/)
- [監看式套件 API 參考](https://developer.xamarin.com/api/namespace/WatchKit/)
