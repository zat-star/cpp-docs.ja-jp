---
title: "フレームワーク (MFC) | Microsoft Docs"
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
  - "API [C++], カプセル化 (MFC Win32 によって)"
  - "アプリケーション フレームワーク [C++], MFC アプリケーション フレームワークの概要"
  - "カプセル化された Win32 API"
  - "カプセル化 [C++]"
  - "カプセル化 [C++], Win32 API"
  - "MFC [C++], アプリケーション フレームワーク"
  - "Win32 [C++], API カプセル化 MFC"
  - "Windows API [C++], カプセル化 (MFC によって)"
  - "ラッパー クラス, 説明"
ms.assetid: 3be0fec8-9843-4119-ae42-ece993ef500b
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# フレームワーク (MFC)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Microsoft Foundation Class \(MFC\) ライブラリ フレームワークを使用するには、いくつかの主要なクラスおよび Visual C\+\+ のいくつかのツールとして主に基づいています。  このクラスは、Win32 アプリケーション プログラミング インターフェイスの大きな \(API\) 部分をカプセル化します。  そのほかのクラスは、ドキュメント、ビュー、アプリケーション自体のようなアプリケーションの概念をカプセル化しています。  さらに、OLE 機能と ODBC と DAO のデータ アクセスの機能をカプセル化します。  
  
 たとえば、ウィンドウの Win32 の概念は、MFC クラス `CWnd`にカプセル化されます。  つまり、C\+\+. C\+\+ クラスによって呼び出される `CWnd` はカプセル化しますまたはウィンドウを表す `HWND` ハンドルを「ラップします」。  同様に、クラス `CDialog` は Win32 ダイアログ ボックスをカプセル化します。  
  
 カプセル化は C\+\+ クラス `CWnd`がたとえば `HWND`型のメンバー変数が含まれ、クラスのメンバー関数をパラメーターとして `HWND` を受け取る Win32 の呼び出しを処理するカプセル化することを意味します。  クラス メンバー関数には、Win32 関数をカプセル化するのと同じ名前になります。  
  
## このセクションの内容  
 [SDI と MDI](../mfc/sdi-and-mdi.md)  
  
 [ドキュメント、ビュー、およびフレームワーク](../mfc/documents-views-and-the-framework.md)  
  
 [ウィザードとリソース エディター](../Topic/Wizards%20and%20the%20Resource%20Editors.md)  
  
## 関連するセクション  
 [フレームワークを使ったアプリケーションの作成](../mfc/building-on-the-framework.md)  
  
 [フレームワークがコードを呼び出す。](../mfc/how-the-framework-calls-your-code.md)  
  
 [CWinApp : アプリケーション クラス](../Topic/CWinApp:%20The%20Application%20Class.md)  
  
 [ドキュメント テンプレートとドキュメント\/ビューの作成手順](../mfc/document-templates-and-the-document-view-creation-process.md)  
  
 [メッセージの処理とマップ](../mfc/message-handling-and-mapping.md)  
  
 [ウィンドウ オブジェクト](../mfc/window-objects.md)  
  
## 参照  
 [クラスを使用した Windows アプリケーションの作成](../Topic/Using%20the%20Classes%20to%20Write%20Applications%20for%20Windows.md)