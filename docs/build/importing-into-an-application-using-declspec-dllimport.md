---
title: "__declspec(dllimport) を使ったアプリケーションへのインポート | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__declspec"
  - "dllimport"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec(dllimport) キーワード [C++]"
  - "インポート (DLL を) [C++], __declspec(dllimport)"
ms.assetid: edb4da4e-f83a-44cf-a668-9239d49dbe42
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# __declspec(dllimport) を使ったアプリケーションへのインポート
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

あるプログラムが DLL によって定義されたパブリック シンボルを使うことを、シンボルをインポートすると言います。  DLL を使ってビルドされるアプリケーション用のヘッダー ファイルを作成する場合、パブリック シンボルの宣言には **\_\_declspec\(dllimport**\) を使います。  キーワード **\_\_declspec\(dllimport\)** は、エクスポートに .def ファイルと **\_\_declspec\(dllexport\)** キーワードのどちらを使うかにかかわらず、動作します。  
  
 コードを読みやすくするために、次のように **\_\_declspec\(dllimport\)** 用のマクロを定義して、そのマクロを各インポート シンボルの宣言に使います。  
  
```  
#define DllImport   __declspec( dllimport )  
  
DllImport int  j;  
DllImport void func();  
```  
  
 関数の宣言としては、**\_\_declspec\(dllimport\)** は省略可能ですが、このキーワードを使うと、コンパイラはより効率的なコードを生成します。  ただし、インポートされる実行形式が DLL のパブリック データ シンボルとオブジェクトにアクセスするには、**\_\_declspec\(dllimport\)** を使う必要があります。  DLL を使う場合は、引き続きインポート ライブラリとリンクする必要があることに注意してください。  
  
 DLL とクライアント アプリケーションには、同じヘッダー ファイルを使うことができます。  こうする場合は、DLL のビルドとクライアント アプリケーションのビルドの区別を示すために、専用のプリプロセッサ シンボルを使います。  たとえば、次のようになります。  
  
```  
#ifdef _EXPORTING  
   #define CLASS_DECLSPEC    __declspec(dllexport)  
#else  
   #define CLASS_DECLSPEC    __declspec(dllimport)  
#endif  
  
class CLASS_DECLSPEC CExampleA : public CObject  
{ ... class definition ... };  
```  
  
## 目的に合ったトピックをクリックしてください  
  
-   [DLL の初期化](../build/initializing-a-dll.md)  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [インライン関数のインポートとエクスポート](../Topic/Importing%20and%20Exporting%20Inline%20Functions.md)  
  
-   [相互インポート](../Topic/Mutual%20Imports.md)  
  
## 参照  
 [アプリケーションへのインポート](../build/importing-into-an-application.md)