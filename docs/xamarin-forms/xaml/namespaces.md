---
title: "XAML 命名空間"
description: "XAML 會使用命名空間宣告 xmlns XML 屬性。 本文章導入 XAML 命名空間的語法，並示範如何宣告 XAML 命名空間，以存取的類型。"
ms.topic: article
ms.prod: xamarin
ms.assetid: C03B5553-B199-4A19-9F0F-E5BCE1DB268F
ms.technology: xamarin-forms
author: charlespetzold
ms.author: chape
ms.date: 07/10/2017
ms.openlocfilehash: 55b83151e9c345096aeb0bfdd686d50c5fde62fd
ms.sourcegitcommit: 8e722d72c5d1384889f70adb26c5675544897b1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/15/2018
---
# <a name="xaml-namespaces"></a>XAML 命名空間

_XAML 會使用命名空間宣告 xmlns XML 屬性。本文章導入 XAML 命名空間的語法，並示範如何宣告 XAML 命名空間，以存取的類型。_

## <a name="overview"></a>總覽

有兩個 XAML 命名空間宣告內，則會永遠 XAML 檔案的根項目。 第一個定義的預設命名空間中，下列 XAML 程式碼範例所示：

```csharp
xmlns="http://xamarin.com/schemas/2014/forms"
```

預設命名空間指定沒有前置詞在 XAML 檔中定義的項目參考 Xamarin.Forms 類別，例如[ `ContentPage` ](https://developer.xamarin.com/api/type/Xamarin.Forms.ContentPage/)。

第二個命名空間宣告會使用`x`首碼，如下列 XAML 程式碼範例所示：

```csharp
xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
```

XAML 使用前置詞來宣告非預設的命名空間，以參考型別在命名空間中的執行時，使用前置詞。 `x`命名空間宣告會指定具有的前置詞在 XAML 中定義項目`x`用於項目和都內建到 XAML （特別是 2009 XAML 規格） 的屬性。

下表概述`x`Xamarin.Forms 所支援的命名空間屬性：

|建構|描述|
|--- |--- |
|`x:Arguments`|指定非預設建構函式或 factory 方法物件宣告的建構函式引數。|
|`x:Class`|指定類別，在 XAML 中定義的命名空間和類別名稱。 類別名稱必須符合類別名稱的程式碼後置檔案。 請注意，這個建構只能出現在 XAML 檔案的根項目。|
|`x:FactoryMethod`|指定可以用來初始化物件的 factory 方法。|
|`x:Key`|指定使用者定義的唯一索引鍵中的每個資源`ResourceDictionary`。 索引鍵的值用來擷取 XAML 資源的方法，和通常是做為引數`StaticResource`標記延伸。|
|`x:Name`|指定的 XAML 項目執行階段物件名稱。 設定`x:Name`方式類似於宣告的變數在程式碼中。|
|`x:TypeArguments`|指定的泛型型別建構函式的泛型型別引數。|

如需有關`x:Arguments`， `x:FactoryMethod`，和`x:TypeArguments`屬性，請參閱[傳遞引數，在 XAML 中](~/xamarin-forms/xaml/passing-arguments.md)。

在 XAML 中，命名空間宣告繼承自父項目子系項目中。 因此，當定義命名空間中的 XAML 檔案的根項目，該檔案中的所有項目會繼承命名空間宣告。

## <a name="declaring-namespaces-for-types"></a>宣告類型的命名空間

以指定的 Common Language Runtime (CLR) 命名空間名稱，和 （選擇性） 組件名稱的命名空間宣告中宣告 XAML 命名空間與前置詞，可以在 XAML 中參考型別。 這被藉由定義下列關鍵字命名空間宣告內的值：

- **clr 命名空間：**或**使用：** – 包含將公開為 XAML 項目類型的組件內的 CLR 命名空間宣告。 這個關鍵字是必要項。
- **組件 =** – 包含參考的 CLR 命名空間的組件。 這個值會是組件，不含副檔名的名稱。 您應該建立組件的路徑，做為參考專案檔，其中包含將參考組件的 XAML 檔案中。 如果可以省略這個關鍵字**clr 命名空間**值是在相同的組件參考類型的應用程式程式碼。

請注意，區隔字元`clr-namespace`或`using`語彙基元的值是冒號，而字元區隔`assembly`語彙基元，其值為等號。 若要使用兩個語彙基元之間的字元是分號。

下列程式碼範例示範 XAML 命名空間宣告：

```xaml
<ContentPage ... xmlns:local="clr-namespace:HelloWorld" ...>
  ...
</ContentPage>
```

或者，這可以寫成：

```xaml
<ContentPage ... xmlns:local="using:HelloWorld" ...>
  ...
</ContentPage>
```

`local`前置詞是用來指出在命名空間中的型別是應用程式的本機的慣例。 或者，如果型別不同的組件中，組件名稱應該也定義在命名空間宣告中，如下列 XAML 程式碼範例所示：

```xaml
<ContentPage ... xmlns:behaviors="clr-namespace:Behaviors;assembly=BehaviorsLibrary" ...>
  ...
</ContentPage>
```

當宣告來自匯入的命名空間的型別執行個體為下列 XAML 程式碼範例所示，然後指定命名空間前置詞：

```xaml
<ListView ...>
  <ListView.Behaviors>
    <behaviors:EventToCommandBehavior EventName="ItemSelected" ... />
  </ListView.Behaviors>
</ListView>
```

## <a name="summary"></a>總結

本文章導入 XAML 命名空間的語法，並示範如何宣告 XAML 命名空間，以存取的類型。 XAML 使用`xmlns`XML 命名空間宣告和類型的屬性可以參考在 XAML 中宣告 XAML 命名空間與前置詞。


## <a name="related-links"></a>相關連結

- [在 XAML 中傳遞引數](~/xamarin-forms/xaml/passing-arguments.md)