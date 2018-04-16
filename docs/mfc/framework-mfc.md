---
title: "フレームワーク (MFC) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- encapsulation [MFC], Win32 API
- MFC, application framework
- wrapper classes [MFC], explained
- Win32 [MFC], API encapsulation by MFC
- application framework [MFC], about MFC application framework
- APIs [MFC], encapsulation by MFC Win32
- encapsulation [MFC]
- Windows API [MFC], encapsulation by MFC
- encapsulated Win32 API [MFC]
ms.assetid: 3be0fec8-9843-4119-ae42-ece993ef500b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c021b11809b3e6598e694fdaa46b7f829358e24f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="framework-mfc"></a>フレームワーク (MFC)
Microsoft Foundation Class (MFC) ライブラリのフレームワークを使用する作業は、いくつかの主要なクラスといくつかの Visual C ツールに主に基づいています。 一部のクラスでは、Win32 アプリケーション プログラミング インターフェイス (API) の大部分をカプセル化します。 その他のクラスには、ドキュメント、ビュー、および、アプリケーション自体などのアプリケーションの概念がカプセル化します。 まだ他のユーザーは、OLE の機能とデータ アクセス機能が ODBC と DAO カプセル化します。  
  
 たとえば、ウィンドウの Win32 の概念は、MFC クラスによってカプセル化`CWnd`です。 つまり、C++ クラスと呼ばれる`CWnd`をカプセル化、または「ラップ」、 `HWND` Windows ウィンドウを表すハンドル。 同様に、クラス`CDialog`Win32 ダイアログ ボックスをカプセル化します。  
  
 カプセル化されることを意味 C++ クラス`CWnd`、たとえば、型のメンバー変数を含む`HWND`、クラスのメンバー関数が受け取る Win32 関数への呼び出しをカプセル化して、`HWND`をパラメーターとして。 クラス メンバー関数は、通常、同じ名前を持つカプセル化の Win32 関数として。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [SDI と MDI](../mfc/sdi-and-mdi.md)  
  
 [ドキュメント、ビュー、フレームワーク](../mfc/documents-views-and-the-framework.md)  
  
 [ウィザードおよびリソース エディター](../mfc/wizards-and-the-resource-editors.md)  
  
## <a name="in-related-sections"></a>関連項目  
 [フレームワークを使ったアプリケーションの作成](../mfc/building-on-the-framework.md)  
  
 [フレームワークと記述したコードとの関係](../mfc/how-the-framework-calls-your-code.md)  
  
 [CWinApp: アプリケーション クラス](../mfc/cwinapp-the-application-class.md)  
  
 [ドキュメント テンプレートとドキュメント/ビューの作成手順](../mfc/document-templates-and-the-document-view-creation-process.md)  
  
 [メッセージの処理とマップ](../mfc/message-handling-and-mapping.md)  
  
 [Window オブジェクト](../mfc/window-objects.md)  
  
## <a name="see-also"></a>参照  
 [クラスを使用した Windows アプリケーションの作成](../mfc/using-the-classes-to-write-applications-for-windows.md)
