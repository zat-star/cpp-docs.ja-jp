---
title: "C 言語の実行形式で使う C++ 関数のエクスポート | Microsoft Docs"
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
  - "エクスポート (DLL を) [C++], C++ 関数 (C 実行可能ファイルの)"
  - "エクスポート (関数を) [C++], C++ 関数 (C 実行可能ファイルの)"
  - "関数 [C++], C++ 関数 (C 実行可能ファイルの)"
  - "関数 [C++], エクスポート"
ms.assetid: 80b9e982-f52d-4312-a891-f73cc69f3c2b
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# C 言語の実行形式で使う C++ 関数のエクスポート
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+ で記述された DLL 内の関数に C 言語のモジュールからアクセスするには、C\+\+ リンケージではなく C リンケージを使って関数を宣言する必要があります。  特に指定しない限り、C\+\+ コンパイラは C\+\+ のタイプ セーフな名前付け規約 \(名前の装飾\) と C\+\+ の呼び出し規約を使います。C\+\+ の規約を使うと、C からの呼び出しが難しくなります。  
  
 C リンケージを指定するには、関数の宣言に **extern** "**C**" を指定します。  たとえば、次のようになります。  
  
```  
extern "C" __declspec( dllexport ) int MyFunc(long parm1);  
```  
  
## 目的に合ったトピックをクリックしてください  
  
-   [.def ファイルを使った DLL からのエクスポート](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [\_\_declspec\(dllexport\) を使った DLL からのエクスポート](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [AFX\_EXT\_CLASS を使ったエクスポート\/インポート](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [C\/C\+\+ 言語の実行形式で使う C 関数のエクスポート](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [エクスポート方式の使い分け](../build/determining-which-exporting-method-to-use.md)  
  
-   [\_\_declspec\(dllimport\) を使ったアプリケーションへのインポート](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [DLL の初期化](../build/initializing-a-dll.md)  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [装飾名](../Topic/Decorated%20Names.md)  
  
-   [リンケージ指定](http://msdn.microsoft.com/ja-jp/d2b0cff1-7798-4c38-9ac8-61c3bfe2bfb9)  
  
## 参照  
 [DLL からのエクスポート](../build/exporting-from-a-dll.md)