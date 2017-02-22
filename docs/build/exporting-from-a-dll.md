---
title: "DLL からのエクスポート | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLL のエクスポート [C++]"
  - "DLL [C++], エクスポート"
  - "エクスポート (DLL を) [C++]"
  - "エクスポート (DLL を) [C++], エクスポート (DLL から) の概要"
  - "エクスポート (関数を) [C++], DLL (エクスポート元)"
  - "エクスポート テーブル [C++]"
  - "関数 [C++], エクスポート"
ms.assetid: a08f86c4-5996-460b-ae54-da2b764045f0
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# DLL からのエクスポート
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

.DLL のレイアウトは .exe ファイルとよく似ていますが、重要な相違点が 1 つあります。DLL ファイルには、エクスポート テーブルが含まれています。  エクスポート テーブルには、DLL が別の実行形式に対してエクスポートする各関数の名前が含まれています。  これらの関数は、DLL のエントリ ポイントです。エクスポート テーブルに記述されたエクスポート関数のみが、別の実行形式にアクセスできます。  DLL 内のその他の関数は、その DLL でしか使えません。  DLL のエクスポート テーブルを表示するには、[DUMPBIN](../build/reference/dumpbin-reference.md) ツールに \/EXPORTS オプションを指定します。  
  
 DLL から関数をエクスポートする方法には、次の 2 つがあります。  
  
-   モジュール定義 \(.def\) ファイルを作成し、DLL をビルドするときに .def ファイルを使用します。  [名前ではなく序数で DLL から関数をエクスポートする](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md)場合は、この方法を使用します。  
  
-   関数の定義に **\_\_declspec\(dllexport\)** キーワードを使用します。  
  
 上のどちらかの方法を使って関数をエクスポートする場合は、必ず [\_\_stdcall](../cpp/stdcall.md) の呼び出し規約を使います。  
  
## 目的に合ったトピックをクリックしてください  
  
-   [.def ファイルを使った DLL からのエクスポート](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [\_\_declspec\(dllexport\) を使った DLL からのエクスポート](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [AFX\_EXT\_CLASS を使ったエクスポート\/インポート](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [C 言語の実行形式で使う C\+\+ 関数のエクスポート](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [C\/C\+\+ 言語の実行形式で使う C 関数のエクスポート](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [名前ではなく序数値による DLL 関数のエクスポート](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md)  
  
-   [エクスポート方式の使い分け](../build/determining-which-exporting-method-to-use.md)  
  
-   [リンク方式の使い分け](../build/determining-which-linking-method-to-use.md)  
  
-   [DLL の初期化](../build/initializing-a-dll.md)  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [アプリケーションへのインポート](../build/importing-into-an-application.md)  
  
-   [インライン関数のインポートとエクスポート](../Topic/Importing%20and%20Exporting%20Inline%20Functions.md)  
  
-   [相互インポート](../Topic/Mutual%20Imports.md)  
  
## 参照  
 [インポートとエクスポート](../build/importing-and-exporting.md)