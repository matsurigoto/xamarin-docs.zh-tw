---
title: "Mac 應用程式組態"
description: "本指南逐步說明設定 Xamarin.Mac 應用程式以供發行。"
ms.topic: article
ms.prod: xamarin
ms.assetid: fea66a34-1581-4cd6-b714-3fbff215a542
ms.technology: xamarin-mac
author: bradumbaugh
ms.author: brumbaug
ms.date: 04/12/2017
ms.openlocfilehash: 0bc64d0b03aa4f80b19ea098904dc1e2155313f6
ms.sourcegitcommit: 30055c534d9caf5dffcfdeafd6f08e666fb870a8
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/09/2018
---
# <a name="mac-app-configuration"></a>Mac 應用程式組態

_本指南將逐步解說如何設定 Xamarin.Mac 應用程式以供發行。_


## <a name="mac-app-configuration"></a>Mac 應用程式組態

在 Visual Studio for Mac 中的 Mac 應用程式上按一下滑鼠右鍵，然後選擇 [選項]。


### <a name="application-settings"></a>應用程式設定

若要變更 Xamarin.Mac 應用程式的「應用程式設定」，請在 [Solution Pad] 中，按兩下 [Info.plist] 檔案：

![選取 Info.plist 檔案](app-configuration-images/config04.png "選取 Info.plist 檔案")

這會顯示應用程式可用的選項：

 [![編輯 Info.plist 檔案](app-configuration-images/config01.png "編輯 Info.plist 檔案")](app-configuration-images/config01-large.png#lightbox)

執行使用 Xamarin.Mac 建立的 Mac 應用程式有下列系統需求：

- 執行 Mac OS X 10.7 或更新版本的 Mac 電腦。


### <a name="signing-settings"></a>簽署設定

[專案選項] 對話方塊的 [Mac 簽署] 區段可讓開發人員簽署 Xamarin.Mac 應用程式以進行測試、自行發行或透過 Apple App Store 發行：

[![Mac 簽署 編輯器](app-configuration-images/config02.png "Mac 簽署 視窗")](app-configuration-images/config02-large.png#lightbox)

在此處選取身分識別、佈建設定檔，以及在編譯完成後要用來簽署應用程式的任何自訂權利。 開發人員可選擇性地簽署用來在其他 Mac 上安裝應用程式的安裝程式。


### <a name="build-settings"></a>組建設定

[專案選項] 對話方塊的 [Mac 組建] 區段可讓開發人員選取 Xamarin.Mac 應用程式的架構、控制應用程式將支援哪些 macOS 版本，以及視需要在應用程式成功編譯後建立安裝套件：

 [![編輯組建設定](app-configuration-images/config03.png "編輯組建設定")](app-configuration-images/config03-large.png#lightbox)


## <a name="related-links"></a>相關連結

- [安裝](/visualstudio/mac/installation/)
- [Hello, Mac 範例](~/mac/get-started/hello-mac.md)
- [在 Mac App Store 上散發應用程式](https://developer.apple.com/devcenter/mac/checklist/) \(英文\)
- [開發人員識別碼和 GateKeeper](https://developer.apple.com/resources/developer-id/) \(英文\)