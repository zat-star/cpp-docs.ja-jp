---
title: "DEF ファイルを使ったインポート | Microsoft Docs"
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
  - ".def ファイル [C++], インポートで使用"
  - "def ファイル [C++], インポートで使用"
  - "dllimport 属性 [C++], DEF ファイル"
  - "DLL [C++], DEF ファイル"
  - "インポート (DLL を) [C++], DEF ファイル"
ms.assetid: aefdbf50-f603-488a-b0d7-ed737bae311d
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# DEF ファイルを使ったインポート
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

.def ファイルと共に **\_\_declspec\(dllimport\)** を使用する場合は、CONSTANT の代わりに DATA を使用するように .def ファイルを変更して、不正なコーディングによる問題の発生を抑える必要があります。  
  
```  
// project.def  
LIBRARY project  
EXPORTS  
   ulDataInDll   DATA  
```  
  
 次の表に、その理由を示します。  
  
|キーワード|インポート ライブラリに送られる名前|エクスポート|  
|-----------|------------------------|------------|  
|`CONSTANT`|`_imp_ulDataInDll_ulDataInDll`|`_ulDataInDll`|  
|`DATA`|`_imp_ulDataInDll`|`_ulDataInDll`|  
  
 **\_\_declspec\(dllimport\)** と CONSTANT を使うと、明示的リンクを行うために作成される .lib DLL インポート ライブラリには、`imp` バージョンと未装飾名の両方が送られます。  **\_\_declspec\(dllimport\)** と DATA を使うと、`imp` バージョンの名前だけが送られます。  
  
 CONSTANT を使う場合、`ulDataInDll` にアクセスするには、以下のコードのどちらかを使います。  
  
```  
__declspec(dllimport) ULONG ulDataInDll; /*prototype*/  
if (ulDataInDll == 0L)   /*sample code fragment*/  
```  
  
 または  
  
```  
ULONG *ulDataInDll;      /*prototype*/  
if (*ulDataInDll == 0L)  /*sample code fragment*/  
```  
  
 ただし、.def ファイルに DATA を使っている場合、変数 `ulDataInDll` にアクセスできるのは、次の定義を追加してコンパイルしたコードだけです。  
  
```  
__declspec(dllimport) ULONG ulDataInDll;  
  
if (ulDataInDll == 0L)   /*sample code fragment*/  
```  
  
 間接操作のレベルの追加を忘れると、インポート アドレス テーブルのその変数自体ではなく、その変数へのポインターにアクセスする可能性があります。このため、CONSTANT を使う方が危険性は増します。  この種の問題は、多くの場合、アクセス違反として扱われます。インポート アドレス テーブルは、現在、コンパイラとリンカーによって読み取り専用に設定されているためです。  
  
 .def ファイル内に CONSTANT が見つかった場合、現在の Visual C\+\+ リンカーは警告を出すことでこの問題に対処します。  CONSTANT を使うのは、ヘッダー ファイルのプロトタイプに **\_\_declspec\(dllimport\)** が記述されていないため、一部のオブジェクト ファイルが再コンパイルできない場合だけにしてください。  
  
## 参照  
 [アプリケーションへのインポート](../build/importing-into-an-application.md)