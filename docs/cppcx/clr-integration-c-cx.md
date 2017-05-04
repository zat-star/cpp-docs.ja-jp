---
title: "CLR 統合 (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 76e213cf-2f3d-4181-b35b-9fd25d5b307c
caps.latest.revision: 10
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 10
---
# CLR 統合 (C++/CX)
一部の [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 型は、[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] での特別な処理と、共通言語ランタイム \(CLR\) に基づく言語を受け取ります。 この記事では、1 つの言語のいくつかの型から別の言語へのマップの仕組みについて説明します。 たとえば、CLR は Windows.Foundation.IVector を System.Collections.IList へ、Windows.Foundation.IMap を System.Collections.IDictionary へ、というようにマップします。 同様に、[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] はPlatform::Delegate や Platform::String などの型を特別にマップします。  
  
## [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] から [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] へのマッピング  
 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] が Windows メタデータ \(.winmd\) ファイルを読み取る場合、コンパイラは共通の [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] の名前空間と型を [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] の名前空間と型にマップします。 たとえば、数値の [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 型 `UInt32` は `default::uint32` に自動的にマップされます。  
  
 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] は、他のいくつかの [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 型を **Platform** 名前空間にマップします。 たとえば、**Windows::Foundation** HSTRING ハンドル \(読み取り専用の Unicode テキスト文字列を表す\) は、[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] `Platform::String` クラスにマップされます。[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 操作によってエラー HRESULT が戻される場合、[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] `Platform::Exception` にマップされます。 詳細については、「[Built\-in Types](http://msdn.microsoft.com/ja-jp/acc196fd-09da-4882-b554-6c94685ec75f)」を参照してください。  
  
 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] は [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 名前空間の特定の型をマップすることで、型の機能強化も行います。 これらの型については、[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] は、C\+\+ に固有であり、型の標準 .winmd ファイルでは使用できないヘルパー コンストラクターおよびメソッドを提供しています。  
  
 新しいコンストラクターとヘルパー メソッドをサポートしている値構造体を次の一覧に示します。 構造体の初期化リストを使用するコードを既に作成済みの場合、新たに追加されたコンストラクターを使用するように変更してください。  
  
 **Windows::Foundation**  
  
-   ポイント  
  
-   Rect  
  
-   サイズ  
  
 **Windows::UI**  
  
-   色  
  
 **Windows::UI::Xaml**  
  
-   CornerRadius  
  
-   存続期間  
  
-   GridLength  
  
-   太さ  
  
 **Windows::UI::Xaml::Interop**  
  
1.  TypeName  
  
 **Windows::UI::Xaml::Media**  
  
-   \[マトリックス\]  
  
 **Windows::UI::Xaml::Media::Animation**  
  
-   KeyTime  
  
-   RepeatBehavior  
  
 **Windows::UI::Xaml::Media::Media3D**  
  
-   Matrix3D  
  
## CLR から [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] へのマッピング  
 Visual C\+\+ または C\# コンパイラーが .winmd ファイルを読み取るときに、メタデータ ファイル内の特定の型を、該当する [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] または CLR 型に自動的にマップします。 たとえば、CLR では、IVector\<T\> インターフェイスが IList\<T\> にマップされます。 しかし、[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] では、IVector\<T\> インターフェイスは別の型にマップされません。  
  
 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] の IReference\<T\> は .NET の Nullable\<T\> にマップします。  
  
## 参照  
 [その他の言語との相互運用](../cppcx/interoperating-with-other-languages-c-cx.md)