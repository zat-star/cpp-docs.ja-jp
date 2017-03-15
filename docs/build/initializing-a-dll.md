---
title: "DLL の初期化 | Microsoft Docs"
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
  - "DLL [C++], 初期化"
  - "初期化 (DLL を)"
  - "終了コード [C++]"
ms.assetid: f655c5ff-ab5b-493a-a1da-4d1074e60c5b
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# DLL の初期化
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

通常、DLL には、DLL の読み込み時に実行する必要がある初期化コードが含まれています。  Visual C\+\+ を使う場合は、DLL を初期化するコードを追加する場所は、ビルドする DLL の種類によって異なります。  初期化コードや終了コードを追加する必要のない場合は、DLL のビルド時にしなければならないことは特にありません。  次の表では、DLL を初期化する必要がある場合の、初期化コードを追加する場所を示しています。  
  
|\[DLL の種類\]|初期化\/終了コードを追加する場所|  
|-----------------|-----------------------|  
|標準 DLL|DLL 内の `CWinApp` オブジェクトの `InitInstance` および `ExitInstance`|  
|拡張 DLL|MFC DLL ウィザード によって生成される `DllMain` 関数の中|  
|非 MFC DLL|プログラマが提供する `DllMain` 関数の中|  
  
 Win32 では、すべての DLL にオプションのエントリ ポイント関数 \(通常、`DllMain`\) が含まれます。エントリ ポイント関数は、初期化と終了の両方で呼び出されます。  これによって、追加のリソースを必要に応じて、割り当て\/解放する機会が与えられます。  Windows には、エントリ ポイント関数が呼び出される 4 つの状況 \(プロセスのアタッチ、プロセス デタッチ、スレッド アタッチ、スレッド デタッチ\) があります。  
  
 C のランタイム ライブラリでは、**\_DllMainCRTStartup** というエントリ ポイント関数が提供されています。この関数は `DllMain` を呼び出します。  ソース コードから `DllMain` を呼び出すか、MFC ライブラリ内に提供されている `DllMain` を使うかは、DLL の種類によって異なります。  
  
## 目的に合ったトピックをクリックしてください  
  
-   [レギュラー DLL の初期化](../Topic/Initializing%20Regular%20DLLs.md)  
  
-   [拡張 DLL の初期化](../build/initializing-extension-dlls.md)  
  
-   [非 MFC DLL の初期化](../Topic/Initializing%20Non-MFC%20DLLs.md)  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [C ランタイム ライブラリの動作と \_DllMainCRTStartup](../build/run-time-library-behavior.md)  
  
-   [\<caps:sentence id\="tgt24" sentenceid\="58bb7328659bda9ffb73a1dcd39da06b" class\="tgtSentence"\>The function specification for DllMain \(Windows SDK\)\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms682583)  
  
-   [\<caps:sentence id\="tgt25" sentenceid\="f29344705c59343b34b642944921cbdf" class\="tgtSentence"\>Dynamic\-link library entry\-point function \(Windows SDK\)\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms682596)  
  
## 参照  
 [Visual C\+\+ の DLL](../build/dlls-in-visual-cpp.md)