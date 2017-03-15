---
title: "拡張 DLL: 概要 | Microsoft Docs"
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
  - "AFXDLL ライブラリ"
  - "DLL [C++], 拡張機能"
  - "拡張 DLL [C++], 拡張 DLL の概要"
  - "MFC DLL [C++], 拡張 DLL"
  - "共有 DLL バージョン [C++]"
ms.assetid: eb5e10b7-d615-4bc7-908d-e3e99b7b1d5f
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 拡張 DLL: 概要
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC 拡張 DLL は、既存の MFC ライブラリ クラスから派生した再利用可能なクラスを主に実装する DLL です。  拡張 DLL は、MFC のダイナミック リンク ライブラリ バージョン \(MFC の共有バージョン\) を使ってビルドされます。  ただし、拡張 DLL を使用できるのは、MFC の共有バージョンを使ってビルドされた MFC の実行可能ファイル \(アプリケーションまたはレギュラー DLL\) だけです。  拡張 DLL を使うと、MFC から新しいカスタム クラスを派生し、この拡張バージョンの MFC を、DLL を呼び出すアプリケーションに提供できます。  
  
 また、拡張 DLL を使うと、アプリケーションと DLL の間で MFC の派生オブジェクトをやり取りすることもできます。  やり取りされるオブジェクトに関連付けられたメンバー関数は、そのオブジェクトが作成されたモジュール内にあります。  これらの関数は MFC の共有 DLL バージョンの使用時に正しくエクスポートされるので、MFC のポインターまたは MFC の派生オブジェクトのポインターをアプリケーションと拡張 DLL との間で自由にやり取りできます。  
  
 拡張 DLL の基本条件を満たす DLL の例については、MFC サンプルの [DLLHUSK](http://msdn.microsoft.com/ja-jp/dfcaa6ff-b8e2-4efd-8100-ee3650071f90) を参照してください。  特に Testdll1.cpp ファイルと Testdll2.cpp ファイルを参照してください。  
  
 AFXDLL という用語は、Visual C\+\+ のドキュメントでは今後使われません。  拡張 DLL は、これまで AFXDLL と呼ばれていたものと同じ性質のものです。  
  
## 目的に合ったトピックをクリックしてください  
  
-   [拡張 DLL の初期化](../build/initializing-extension-dlls.md)  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [拡張 DLLs](../build/extension-dlls.md)  
  
-   [レギュラー DLL でのデータベース、OLE、およびソケット拡張 DLL の使用](../build/using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)  
  
-   [非 MFC DLL: 概要](../Topic/Non-MFC%20DLLs:%20Overview.md)  
  
-   [MFC と静的にリンクされるレギュラー DLL](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [MFC と動的にリンクされるレギュラー DLL](../Topic/Regular%20DLLs%20Dynamically%20Linked%20to%20MFC.md)  
  
-   [MFC DLL ウィザード](../mfc/reference/mfc-dll-wizard.md)  
  
## 参照  
 [DLL の種類](../build/kinds-of-dlls.md)