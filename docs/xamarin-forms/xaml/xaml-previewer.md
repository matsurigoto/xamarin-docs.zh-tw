---
title: Xamarin.Forms 的 XAML 預覽程式
description: 本文說明如何使用 XAML 預覽程式，以查看 Xamarin.Forms 配置呈現您輸入。 XAML 預覽程式位於 Visual Studio 2017 和 Visual Studio for mac。
ms.prod: xamarin
ms.assetid: 84769ff1-72fd-4c44-8251-dd6d5bf8c7b2
ms.technology: xamarin-forms
author: charlespetzold
ms.author: chape
ms.date: 05/31/2018
ms.openlocfilehash: 25c8e1a34f8be5ab2f8491e75fa5aac470d55bc8
ms.sourcegitcommit: 66682dd8e93c0e4f5dee69f32b5fc5a96443e307
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2018
ms.locfileid: "35245855"
---
# <a name="xaml-previewer-for-xamarinforms"></a>Xamarin.Forms 的 XAML 預覽程式

_Xamarin.Forms 配置呈現您輸入時，請參閱 ！_

## <a name="requirements"></a>需求

專案需要 XAML 預覽程式運作的最新的 Xamarin.Forms NuGet 套件。 預覽 Android 應用程式需要[JDK 1.8 x64](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)。

中的詳細資訊[版本資訊](https://developer.xamarin.com/releases/studio/xamarin.studio_6.2/xamarin.studio_6.2/#Xamarin_Forms_Previewer)。

## <a name="getting-started"></a>快速入門

# <a name="visual-studiotabvswin"></a>[Visual Studio](#tab/vswin)

使用**檢視 > 其他視窗 > Xamarin.Forms 預覽程式**在 Visual Studio 中開啟 [預覽] 視窗的功能表。 使用**視窗 > 新增垂直索引標籤群組**功能表上，將它定位的並行。

[![在 Visual Studio 中的 ListView 控制項預覽](xaml-previewer-images/xamlp-list-vs-sml.png "Visual Studio 中的表單預覽程式")](xaml-previewer-images/xamlp-list-vs.png#lightbox "Visual Studio 中的表單預覽程式")

# <a name="visual-studio-for-mactabvsmac"></a>[Visual Studio for Mac](#tab/vsmac)

**預覽**按鈕可以顯示在編輯器 中，XAML 檔案後，以滑鼠右鍵按一下並選取**開啟 > Form 預覽程式**。 [預覽] 窗格可再顯示或隱藏按**預覽**任何 XAML 文件視窗右上角的按鈕：

[![在 Visual Studio for Mac 的 ListView 控制項預覽](xaml-previewer-images/xamlp-list-sml.png "適用於 Mac 的 Visual Studio 中的表單預覽程式")](xaml-previewer-images/xamlp-list.png#lightbox "Form 預覽程式，在 Visual Studio for Mac")

-----

## <a name="xaml-preview-options"></a>XAML [預覽] 選項

[預覽] 窗格頂端的選項如下：

* **電話**– 電話大小螢幕中轉譯
* **Tablet** – 呈現 tablet 大小螢幕中 （請注意右下方窗格的沒有縮放控制項）
* **Android** – 顯示螢幕的 Android 版本
* **iOS** – 顯示螢幕的 iOS 版本
* Portait （圖示） – 使用直式方向預覽
* 橫向 （圖示） – 使用橫向預覽

## <a name="adding-design-time-data"></a>將設計階段資料

某些版面配置可能會很難視覺化沒有任何繫結至使用者介面控制項的資料。 若要讓更實用的預覽，某些靜態將資料指派給控制項的硬式編碼繫結內容 （無論是在程式碼後置，或是使用 XAML）。

James Montemagno 是指[新增設計階段資料的部落格文章](http://motzcod.es/post/143702671962/xamarinforms-xaml-previewer-design-time-data)以了解如何將繫結至 XAML 中的靜態 ViewModel。

## <a name="detecting-design-mode"></a>偵測設計模式

靜態[ `DesignMode.IsDesignModeEnabled` ](xref:Xamarin.Forms.DesignMode.IsDesignModeEnabled)屬性可加以檢查來判斷應用程式是否正在執行中的預覽程式。 這可讓您指定只會在應用程式預覽程式在執行時，所執行的程式碼：

```csharp
if (DesignMode.IsDesignModeEnabled)
{
  // Previewer only code  
}
```

## <a name="troubleshooting"></a>疑難排解

檢查以下問題和[Xamarin 論壇](https://forums.xamarin.com/categories/xamarin-forms)，如果您遇到的問題。

### <a name="xaml-preview-isnt-showing"></a>未顯示 XAML 預覽

檢查下列項目：

* 應該建置專案 （編譯） 之前嘗試預覽 XAML 檔案。
* 設計工具代理程式必須安裝第一次預覽 XAML 檔-此問題之前準備好，將會出現在預覽程式，以及進行訊息的進度列指示器。
* 請嘗試關閉再重新開啟 XAML 檔案。

### <a name="invalid-xaml-the-android-project-needs-to-built-before-preview-can-be-created"></a>無效的 XAML： 需要可以建立預覽之前，先建立 Android 專案

XAML 預覽程式需要建置專案，然後再轉譯頁面。
如果以下的錯誤出現在 [預覽] 窗格的頂端，重新建置應用程式並再試一次。

![錯誤訊息： 必須先建置專案](xaml-previewer-images/error-not-built-sml.png "錯誤訊息： 重建專案")
