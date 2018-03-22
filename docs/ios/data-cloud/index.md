---
title: "資料和雲端服務"
description: "穩定和部署指南"
ms.topic: article
ms.prod: xamarin
ms.assetid: 945719F7-7CE6-4207-BF0F-23195125FC84
ms.technology: xamarin-ios
author: bradumbaugh
ms.author: brumbaug
ms.date: 06/13/2017
ms.openlocfilehash: b5e250c7c505958c8293970321b6173e6086e7b1
ms.sourcegitcommit: 0fdb243b46cf21be47584900805cadcd077121bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/12/2018
---
# <a name="data-and-cloud-services"></a>資料和雲端服務


##  <a name="data-accessiosdata-clouddataindexmd"></a>[資料存取](~/ios/data-cloud/data/index.md)

大部分的應用程式有某些需求，要將資料儲存在本機裝置上。 除非兩者小型的資料量，所以通常會要求資料庫和資料層應用程式來管理資料庫存取權。 iOS 具有 「 內建的 「 Sqlite 資料庫引擎和資料的存取權簡化了 Xamarin 的平台隨附於 SQLite 資料提供者。

##  <a name="icloudiosdata-cloudintroduction-to-icloudmd"></a>[iCloud](~/ios/data-cloud/introduction-to-icloud.md)

IOS 5 iCloud 儲存體 API 可讓應用程式，將使用者文件和應用程式特定資料儲存到中央位置，然後從所有使用者的裝置存取這些項目。

##  <a name="cloudkitiosdata-cloudintro-to-cloudkitmd"></a>[CloudKit](~/ios/data-cloud/intro-to-cloudkit.md)

CloudKit 架構來簡化應用程式的開發該存取 icloud 的功能。 這包括應用程式資料和資產的權限，以及能夠以安全地儲存應用程式資訊的擷取。 此套件可讓使用者的匿名層藉由允許存取其 iCloud Id 的應用程式，而不需要共用個人資訊。