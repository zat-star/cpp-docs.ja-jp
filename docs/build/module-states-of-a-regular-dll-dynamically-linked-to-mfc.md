---
title: "MFC と動的にリンクされるレギュラー DLL のモジュール状態 | Microsoft Docs"
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
  - "DLL [C++], モジュールの状態"
  - "MFC DLL [C++], 標準 DLL"
  - "モジュールの状態 [C++]"
  - "モジュールの状態 [C++], 標準 DLL (動的にリンクされた)"
  - "標準 DLL [C++], 動的リンク (MFC に)"
ms.assetid: b4493e79-d25e-4b7f-a565-60de5b32c723
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# MFC と動的にリンクされるレギュラー DLL のモジュール状態
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC DLL とレギュラー DLL を動的にリンクする機能を使うと、複雑な設定を行うことができます。  たとえば、レギュラー DLL とそれを使用する実行可能ファイルは、MFC DLL および任意の拡張 DLL と動的にリンクできます。  
  
 この設定では、現在の `CWinApp` オブジェクトへのポインターやハンドル マップなどの MFC グローバル データに関する問題が発生します。  
  
 MFC バージョン 4.0 以前では、このグローバル データは MFC DLL 内にあり、プロセス内の全モジュールで共有されていました。  Win32 DLL を使用する各プロセスはそれぞれ独自の DLL データのコピーを取得するため、このスキームによりプロセス単位のデータを簡単に追跡できました。  また、AFXDLL モデルでは、1 つのプロセス内に `CWinApp` オブジェクトやハンドル マップのセットが 1 つしか存在しないと想定されていたため、これらの項目を MFC DLL 自体の中で追跡できました。  
  
 しかし、MFC DLL とレギュラー DLL を動的にリンクする機能では、1 つのプロセス内に複数の `CWinApp` オブジェクトや複数のハンドル マップのセットが存在できるようになりました。  これらのうちどれを使用したらよいか、MFC はどのような方法で判断するのでしょうか。  
  
 この問題は、グローバル状態情報のコピーを各モジュール \(アプリケーションまたはレギュラー DLL\) に設定することで解決できます。  このため、レギュラー DLL 内の **AfxGetApp** を呼び出すと、実行可能ファイルではなく DLL 内の `CWinApp` オブジェクトへのポインターが返されます。  このような各モジュールに設定された MFC のグローバル データのコピーをモジュール状態と言います。モジュール状態については、「[テクニカル ノート 58: MFC のモジュール状態の実装](../mfc/tn058-mfc-module-state-implementation.md)」を参照してください。  
  
 MFC のコモン ウィンドウ プロシージャは、正しいモジュール状態に自動的に切り替えます。このため、レギュラー DLL に実装されたメッセージ ハンドラー内のモジュール状態を気にする必要はありません。  しかし、実行可能ファイルからレギュラー DLL を呼び出す場合は、現在のモジュール状態をその DLL に対して明示的に設定する必要があります。  このためには、DLL のすべてのエクスポート関数で **AFX\_MANAGE\_STATE** マクロを使用します。  これは、DLL からエクスポートされる関数の先頭に次のコード行を追加して行います。  
  
```  
AFX_MANAGE_STATE(AfxGetStaticModuleState( ))  
```  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [MFC モジュールの状態データの管理](../mfc/managing-the-state-data-of-mfc-modules.md)  
  
-   [MFC と動的にリンクされるレギュラー DLL](../Topic/Regular%20DLLs%20Dynamically%20Linked%20to%20MFC.md)  
  
-   [拡張 DLLs](../build/extension-dlls-overview.md)  
  
## 参照  
 [Visual C\+\+ の DLL](../build/dlls-in-visual-cpp.md)