---
title: Xamarin Live Player 設定
description: 本文件說明如何設定 Xamarin Live Player，並用來對執行中應用程式進行即時編輯。
ms.prod: xamarin
ms.assetid: 5DDF9203-8826-4B04-93F5-B8D07EDE3873
author: topgenorth
ms.author: toopge
ms.date: 08/08/2018
ms.openlocfilehash: 10fdc09ec946ff57b87ad4749cf6edaf04b5f7e8
ms.sourcegitcommit: 47709db4d115d221e97f18bc8111c95723f6cb9b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/13/2018
ms.locfileid: "40250942"
---
# <a name="xamarin-live-player-setup"></a>Xamarin Live Player 設定

Xamarin Live Player 可讓您對您的應用程式進行即時編輯並且讓這些變更反映即時裝置上。 Xamarin Live Player 應用程式 – 不需要設定模擬器，或使用纜線來部署內執行的程式碼 ！ 本文說明如何設定 Xamarin Live Player。

![預覽功能](~/media/shared/preview.png)

## <a name="1-get-the-android-app"></a>1.取得 Android 應用程式

Xamarin Live Player 是適用於從 Google Play 的 Android:

[ ![Google Play 上提供](install-images/google-play-badge.png)](https://play.google.com/store/apps/details?id=com.xamarin.live)

沒有 Google Play 的 Android 裝置的 Xamarin Live Player 是可透過[HockeyApp](https://aka.ms/xlp-hockeyapp)發佈。 此外，早期的預覽組建可以直接從 Google Play 安裝 Android，藉由選擇在[開放的 beta 程式](https://play.google.com/apps/testing/com.xamarin.live)

# <a name="visual-studiotabwindows"></a>[Visual Studio](#tab/windows)

## <a name="2-get-visual-studio-2017"></a>2.取得 Visual Studio 2017

Xamarin Live Player 需要：

- Visual Studio 2017 15.4年或更新版本。
- Visual Studio 電腦和裝置上的相同的 WiFi 網路。

## <a name="3-using-xamarin-live-player-for-the-first-time"></a>3.第一次使用 Xamarin Live Player

1. 開啟**Visual Studio 2017**。
2. 移至**工具 > 選項...** ，然後選取**Xamarin > 其他** 索引標籤。
3. 刻度**啟用 Xamarin Live Player**:

    ![核取 [啟用 Xamarin Live Player] 方塊中 [選項] 視窗](install-images/vs2017-options.png)

4. 建立或開啟 Xamarin 專案 (或[範例](~/tools/live-player/samples.md))。
5. 選擇**Live Player**裝置清單中：

    ![裝置清單中包含的 Xamarin Live Player 選項](install-images/devices-empty-windows.png)

    - 如果您已經有配對的裝置，它可做為選項。
    - 否則您將會提示您時所需裝置配對。

6. 按下**執行** 按鈕或選取下列其中一個選項**執行**或以滑鼠右鍵按一下功能表：

    - **啟動但不偵錯**– 您可以編輯應用程式和裝置發生的變更，請參閱 （進行變更並儲存檔案，應用程式會重新啟動）。
    - **開始偵錯**– 您可以設定中斷點，並檢查變數，但無法編輯程式碼。

    或者，選取**工具 > Xamarin Live Player > 即時執行目前檢視**，可讓您編輯的應用程式和裝置發生的變更，請參閱。 目前的檢視是顯示 （而不是應用程式的主畫面）。

7. 如果已經配對裝置和裝置上執行 Xamarin Live Player 應用程式，就會立即執行程式碼 ！

    如果沒有裝置配對，QR 代碼會指示裝置配對：

    ![配對的裝置 視窗](install-images/manage-empty-windows.png)

    如果裝置無法連絡的配對，可能會出現錯誤。

# <a name="visual-studio-for-mactabmacos"></a>[Visual Studio for Mac](#tab/macos)

## <a name="2-get-visual-studio-for-mac"></a>2.取得 Visual Studio for Mac

Xamarin Live Player 需要：

- OS X 10.11，macOS 10.12，或更新版本
- Visual Studio for Mac
- Mac 和相同的 WiFi 網路上的裝置

## <a name="3-using-xamarin-live-player-for-the-first-time"></a>3.第一次使用 Xamarin Live Player

1. 開啟**Visual Studio for Mac**。
2. 移至**Visual Studio > 喜好設定...** ，然後選取**專案 > Xamarin Live Player （預覽）**  索引標籤。
3. 刻度**啟用 Xamarin Live Player**:

    [![核取 [啟用 Xamarin Live Player] 方塊中 [選項] 視窗](install-images/vsmac-options-sml.png)](install-images/vsmac-options.png#lightbox)

4. 建立或開啟 Xamarin 專案 (或[範例](~/tools/live-player/samples.md))。
5. 選擇**Live Player**裝置清單中。

    ![裝置清單中包含的 Xamarin Live Player 選項](install-images/devices.png)

    - 如果您已經有配對的裝置，它可做為選項。
    - 否則您將會提示您時所需裝置配對。
    - 選擇**Xamarin Live Player 裝置...** 來管理您想要使用 Xamarin Live Player 裝置。

6. 按下**執行** 按鈕或選取下列其中一個選項**執行**或以滑鼠右鍵按一下功能表：

    ![執行功能表選項](install-images/run-menu.png)

    - **啟動但不偵錯**– 您可以編輯應用程式和裝置發生的變更，請參閱 （進行變更並儲存檔案，應用程式會重新啟動）。
    - **開始偵錯**– 您可以設定中斷點，並檢查變數，但無法編輯程式碼。
    - **即時執行目前檢視**– 您可以編輯應用程式和裝置發生的變更，請參閱。 目前的檢視是顯示 （而不是應用程式的主畫面）。

7. 如果已經配對裝置和裝置上執行 Xamarin Live Player 應用程式，就會立即執行程式碼 ！

    如果沒有裝置配對，QR 代碼會指示裝置配對：

    ![配對的裝置 視窗](install-images/manage-empty.png)

    如果裝置無法連絡的配對，則會出現錯誤：

    ![無法連線到裝置錯誤訊息](install-images/error-cannot-connect.png)

-----

如果您遇到任何問題，或無法連線，請參閱[限制與疑難排解](~/tools/live-player/troubleshooting.md)。

## <a name="related-links"></a>相關連結

- [限制](~/tools/live-player/limitations.md)
- [疑難排解](~/tools/live-player/troubleshooting.md)
- [Xamarin Live Player 範例](~/tools/live-player/samples.md)
