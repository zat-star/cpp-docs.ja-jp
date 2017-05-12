---
title: "スタティック ライブラリ (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "02/03/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7faf53c8-fa21-42cc-8246-d32533ef9dfa
caps.latest.revision: 10
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 10
---
# スタティック ライブラリ (C++/CX)
[!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] アプリケーションで使用されるスタティック ライブラリには、ISO 標準 C\+\+ コード、および [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] アプリケーション プラットフォームから除外されていない Win32 API への呼び出しも含めることができます。 スタティック ライブラリは [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] コンポーネントを使用します。また、特定の制約を持つ [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] コンポーネントを作成する場合があります。  
  
## スタティック ライブラリの作成  
  
#### [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] アプリケーションで使用するスタティック ライブラリを作成するには、次の手順に従います。  
  
1.  メニュー バーで、[!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] アプリの **\[ファイル\]** \> **\[新規\]** \> **\[プロジェクト\]** \> **\[空のスタティック ライブラリ\]** を選択します。  
  
2.  **ソリューション エクスプローラー**で、プロジェクトのショートカット メニューを開き、**\[プロパティ\]** をクリックします。**\[プロパティ\]** ダイアログ ボックスから **\[構成プロパティ\]** \> **\[全般\]** ページを開き、[!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] アプリケーション サポートを **\[あり\]** に設定します。  
  
3.  **\[構成プロパティ\]** \> **\[C\/C\+\+\]** ページで、**\[**[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]**拡張機能を使用\]** を **\[はい \(\/ZW\)\]** に設定します。  
  
 除外されている Win32 API の呼び出しを行う場合に新規のスタティック ライブラリをコンパイルするときに [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] アプリの場合、コンパイラは生成エラー C3861「識別子が見つかりません。」 サポートされている別の方法を探すように、 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)], を参照してください [Alternatives to Windows APIs in Windows Store apps](http://msdn.microsoft.com/ja-jp/75568012-61e0-41cc-a4df-c698f54f21ec)します。  
  
 C\+\+ スタティック ライブラリ プロジェクトを [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] アプリ ソリューションに追加する場合、[!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] サポート プロパティが **\[はい\]** に設定されるように、ライブラリ プロジェクトのプロパティ設定を更新する必要がある場合があります。 この設定がなくてもコードはビルドとリンクを実行しますが、[!INCLUDE[win8_appstore_long](../cppcx/includes/win8-appstore-long-md.md)] アプリケーションの検証を試みるとエラーが発生します。 スタティック ライブラリは、そのライブラリを利用するプロジェクトと同じコンパイラ設定でコンパイルする必要があります。  
  
 `ref` パブリック クラス、パブリック インターフェイス クラス、またはパブリック値クラスを作成するスタティック ライブラリを使用すると、リンクは次の警告を出します。  
  
> **warning LNK4264:** は \/ZW でコンパイルされたオブジェクト ファイルをスタティック ライブラリにアーカイブしています。[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]型を作成する場合、[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] メタデータを含むスタティック ライブラリとのリンクはお勧めできません。  
  
 スタティック ライブラリが、ライブラリ自体の外部で使用される [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] コンポーネントを生成しない場合のみ、安心して警告を無視できます。 ライブラリが、自らが定義したコンポーネントを利用していない場合、パブリック メタデータに型情報が含まれている状況でも、リンカーは実装を最適化できます。 このことは、スタティック ライブラリ内のパブリック コンポーネントはコンパイルされるが、実行時にアクティブにならないことを意味します。 この理由により、他のコンポーネントまたはアプリケーションで使用することを意図した任意の [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] コンポーネントは、ダイナミック リンク ライブラリ \(DLL\) で実装する必要があります。  
  
## 参照  
 [スレッドとマーシャリング](../cppcx/threading-and-marshaling-c-cx.md)