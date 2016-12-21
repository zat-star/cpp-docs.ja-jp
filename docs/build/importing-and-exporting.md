---
title: "インポートとエクスポート | Microsoft Docs"
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
  - "__declspec(dllimport) キーワード [C++]"
  - "DLL [C++], エクスポート"
  - "DLL [C++], インポート"
  - "エクスポート (DLL を) [C++]"
  - "インポート (DLL を) [C++]"
ms.assetid: 7c44c2aa-2117-4cec-9615-a65bfd3f8f7b
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# インポートとエクスポート
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

次の 2 つの方法を使って、アプリケーションにパブリック シンボルをインポートしたり、DLL から関数をエクスポートしたりできます。  
  
-   DLL をビルドするときにモジュール定義 \(.def\) ファイルを使用します。  
  
-   メイン アプリケーションの関数定義で、**\_\_declspec\(dllimport\)** キーワードまたは **\_\_declspec\(dllexport\)** キーワードを使用します。  
  
## .def ファイルの使用  
 モジュール定義ファイル \(.def\) は、テキスト ファイルです。DLL のさまざまな属性を記述する 1 つ以上のモジュール文が含まれています。  **\_\_declspec\(dllexport\)** キーワードまたは **\_\_declspec\(dllexport\)** キーワードを使わずに DLL の関数をエクスポートする場合は、DLL に .def ファイルが必要です。  
  
 .def ファイルを使うと、[アプリケーションへのインポート](../build/importing-using-def-files.md)や [DLL からのエクスポート](../build/exporting-from-a-dll-using-def-files.md)を行うことができます。  
  
## \_\_declspec の使用  
 Visual C\+\+ では、Visual C\+\+ の 16 ビット版で使用されていた **\_\_export** キーワードの代わりに、**\_\_declspec\(dllimport\)** と **\_\_declspec\(dllexport\)** を使用します。  
  
 **\_\_declspec\(dllimport\)** を使用しなくてもコードは正しくコンパイルされますが、使用した方がコードがより洗練されます。  \_\_declspec\(dllimport\) を使うと、ある関数が DLL 内にあるかないかをコンパイラが判断できるようになり、その結果、コードでは通常 DLL の境界を越える関数呼び出し内に存在する間接操作のレベルをスキップできます。  ただし、DLL 内に変数をインポートするには、**\_\_declspec\(dllimport\)** を必ず使用する必要があります。  
  
 .def ファイルの EXPORT セクションが適切な場合、**\_\_declspec\(dllexport\)** は不要です。  **\_\_declspec\(dllexport\)** を追加すると、.def ファイルを使わなくても .exe または .dll から関数を簡単にエクスポートできます。  
  
 Win32 移植可能実行可能形式は、インポートを固定するために参照しなければならないページ数を最小限に抑えるようにデザインされています。  このために、あらゆるプログラム用のインポート アドレス全部をインポート アドレス テーブルという場所にまとめています。  こうすることで、ローダーはインポートにアクセスするときに 1 ページか 2 ページを変更するだけで済みます。  
  
## 目的に合ったトピックをクリックしてください  
  
-   [\_\_declspec\(dllimport\) を使ったアプリケーションへのインポート](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [DLL からのエクスポート](../build/exporting-from-a-dll.md)  
  
## 参照  
 [Visual C\+\+ の DLL](../build/dlls-in-visual-cpp.md)