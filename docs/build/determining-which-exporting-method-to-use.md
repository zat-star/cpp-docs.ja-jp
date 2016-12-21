---
title: "エクスポート方式の使い分け | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".def ファイル [C++], エクスポート (DLL から)"
  - "__declspec(dllexport) キーワード [C++]"
  - "def ファイル [C++], エクスポート (DLL から)"
  - "エクスポート (DLL を) [C++], メソッドの比較"
ms.assetid: 66d773ed-935c-45c2-ad03-1a060874b34d
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# エクスポート方式の使い分け
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

方法 2 .def ファイルまたは `__declspec(dllexport)` キーワードの関数をエクスポートできます。  どの方法を DLL に対して適切かを判断するには、次の事項を検討する:  
  
-   そのほかの関数を後でエクスポートする予定がある場合。  
  
-   DLL は、リビルド、またはその使用されます。使用するアプリケーションによってのみアプリケーション、第三者によって作成されたアプリケーションでリビルド例にできないか。  
  
## .def ファイルを使う場合の利点と欠点  
 .def ファイルを使って関数をエクスポートする場合、エクスポート序数のコントロールを提供します。  DLL にエクスポート関数を追加すると、そのほかのエクスポート関数よりも高い序数値を割り当てることができます。  こうすると、暗黙的なリンクを使用するアプリケーションは、新しい関数を含むインポート ライブラリとリンクし直す必要はありません。  これは、新しい機能を追加し、既に依存するアプリケーションで正しく動作し続けることを確認できるため、多くのアプリケーションで使用するための DLL をデザインする場合、非常に便利です。  たとえば、MFC DLL は、.def ファイルを使用して構築されます。  
  
 .def ファイルを使うもう一つの利点は、関数をエクスポートするために `NONAME` 属性を使用できるようになります。  これは、DLL のエクスポート テーブル内の序数のみを配置します。  `NONAME` 属性を使用して DLL にエクスポート関数が多数あり、DLL ファイルのサイズを単純化するできます。  モジュール定義文を記述する方法の詳細については、「[モジュール定義ステートメントに関する規則](../build/reference/rules-for-module-definition-statements.md)」を参照してください。  順序をエクスポートする方法の詳細については、「[名前ではなく序数値による DLL 関数のエクスポート](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md)」を参照してください。  
  
 .def ファイルを使うの欠点は、C\+\+. C\+\+ ファイル内の関数をエクスポートする場合は、Visual C\+\+ コンパイラで装飾された名前でを避けるには、装飾名を .def ファイルに配置したり、extern 「C」を使用してエクスポート関数を定義する必要があります。  
  
 配置の装飾名を .def ファイル\) は、[DUMPBIN](../build/reference/dumpbin-reference.md) ツールを使用するか、[\/MAP](../build/reference/map-generate-mapfile.md) リンカー オプションを使用してそれらを取得できます。  コンパイラが作成した装飾名はコンパイラ固有;です したがって、.def ファイルにコンパイラが作成した装飾名を指定すると、DLL へのリンクは、DLL の .def ファイルで呼び出し元のアプリケーションの一致でコンパイラと同じバージョンは、装飾名がエクスポートされる名前を使用して構成する必要があります。アプリケーション。  
  
## \_\_declspec\(dllexport\) を使う場合の利点と欠点  
 `__declspec(dllexport)` を使用して .def ファイルを維持し、エクスポート関数の装飾名を取得することを考慮する必要がないため、便利です。  ただし、エクスポートするこの方法の有効性はリンクされたなアプリケーションの数リビルドする意思があるという制限されます。  新しいエクスポートで DLL をビルドし直すと、それを再度ビルドする場合は、異なるバージョンのコンパイラを使用する場合、エクスポートされた C\+\+ 関数の装飾名が変更されている可能性があるため、アプリケーションを再度ビルドする必要があります。  
  
### 目的に合ったトピックをクリックしてください  
  
-   [DEF ファイルを使った DLL からのエクスポート](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [\_\_declspec\(dllexport\) を使った DLL からのエクスポート](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [AFX\_EXT\_CLASS を使ったエクスポート\/インポート](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [C 言語の実行形式で使う C\+\+ 関数のエクスポート](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [C\/C\+\+ 言語の実行形式で使う C 関数のエクスポート](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [\_\_declspec\(dllimport\) を使ったアプリケーションへのインポート](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [DLL の初期化](../build/initializing-a-dll.md)  
  
### さらに詳しくは次のトピックをクリックしてください  
  
-   [インライン関数のインポートとエクスポート](../Topic/Importing%20and%20Exporting%20Inline%20Functions.md)  
  
-   [相互インポート](../Topic/Mutual%20Imports.md)  
  
-   [装飾名](../Topic/Decorated%20Names.md)  
  
## 参照  
 [DLL からのエクスポート](../build/exporting-from-a-dll.md)