---
title: "C/C++ 言語の実行形式で使う C 関数のエクスポート | Microsoft Docs"
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
  - "__cplusplus マクロ"
  - "エクスポート (DLL を) [C++], C 関数 (C++ 実行ファイルの)"
  - "エクスポート (関数を) [C++], C 関数 (C++ 実行ファイルの)"
  - "関数 [C], C または C++ 実行可能ファイル"
  - "関数 [C], エクスポート"
ms.assetid: b51d6e5e-37cf-4c1c-b0bf-fcf188c82f00
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# C/C++ 言語の実行形式で使う C 関数のエクスポート
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C で記述された DLL 内の関数に C\/C\+\+ 言語のモジュールからアクセスするには、**\_\_cplusplus** プリプロセッサ マクロを使って、コンパイルする言語を指定する必要があります。また、C\+\+ 言語モジュールから使う場合は、これらの関数を C リンケージで宣言します。  この方法で DLL 用ヘッダー ファイルを作成すると、関数を変更しなくても C\/C\+\+ から利用できます。  
  
 以下のコードは、C\/C\+\+ クライアント アプリケーションによって使われるヘッダー ファイルを示しています。  
  
```  
// MyCFuncs.h  
#ifdef __cplusplus  
extern "C" {  // only need to export C interface if  
              // used by C++ source code  
#endif  
  
__declspec( dllimport ) void MyCFunc();  
__declspec( dllimport ) void AnotherCFunc();  
  
#ifdef __cplusplus  
}  
#endif  
```  
  
 C\+\+ の実行形式にリンクする C 関数の宣言ヘッダー ファイルで上の手法を使っていない場合は、C\+\+ ソース ファイルに上のコードを記述します。こうすると、コンパイラは C 関数名を装飾しません。  
  
```  
extern "C" {  
#include "MyCHeader.h"  
}  
```  
  
## 目的に合ったトピックをクリックしてください  
  
-   [.def ファイルを使った DLL からのエクスポート](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [\_\_declspec\(dllexport\) を使った DLL からのエクスポート](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [AFX\_EXT\_CLASS を使ったエクスポート\/インポート](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [エクスポート方式の使い分け](../build/determining-which-exporting-method-to-use.md)  
  
-   [\_\_declspec\(dllimport\) を使ったアプリケーションへのインポート](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [DLL の初期化](../build/initializing-a-dll.md)  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [装飾名](../Topic/Decorated%20Names.md)  
  
-   [リンケージ指定](http://msdn.microsoft.com/ja-jp/d2b0cff1-7798-4c38-9ac8-61c3bfe2bfb9)  
  
## 参照  
 [DLL からのエクスポート](../build/exporting-from-a-dll.md)