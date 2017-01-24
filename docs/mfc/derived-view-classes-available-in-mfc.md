---
title: "MFC で使用できる派生ビュー クラス | Microsoft Docs"
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
  - "クラス [C++], 派生"
  - "CView クラス, クラス (派生)"
  - "派生クラス, ビュー クラス"
  - "ビュー クラス, 派生"
ms.assetid: dba42178-7459-4ccc-b025-f3d9b8a4b737
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC で使用できる派生ビュー クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

次の表は、互いに MFC ビュー クラスおよび関係を示しています。  ビュー クラスの機能が派生する MFC ビュー クラスに依存します。  
  
### ビュー クラス  
  
|\[クラス\]|説明|  
|-------------|--------|  
|[CView](../Topic/CView%20Class.md)|すべてのビューの基本クラスです。|  
|[CCtrlView](../mfc/reference/cctrlview-class.md)|`CTreeView`、`CListView`、`CEditView`と `CRichEditView`の基本クラスです。  これらのクラスは、指定された Windows コモン コントロールを使用したドキュメント\/ビュー アーキテクチャを使用することができます。|  
|[CEditView](../Topic/CEditView%20Class.md)|Windows のエディット ボックスのコントロールに基づいて簡単なビューです。  テキストを入力して編集する割り当ては単純なテキスト エディター アプリケーションのベースとして使用できます。  「`CRichEditView`」も参照してください。|  
|[CRichEditView](../mfc/reference/cricheditview-class.md)|[CRichEditCtrl](../Topic/CRichEditCtrl%20Class.md) オブジェクトを含むビュー。  このクラスは `CEditView`ですが、`CEditView`とは異なり似ていますが、`CRichEditView` ハンドルの書式設定されたテキスト。|  
|[CListView](../mfc/reference/clistview-class.md)|[CListCtrl](../Topic/CListCtrl%20Class.md) オブジェクトを含むビュー。|  
|[CTreeView](../mfc/reference/ctreeview-class.md)|Visual C\+\+ ソリューション エクスプローラー ウィンドウに似たビューの [CTreeCtrl](../mfc/reference/ctreectrl-class.md) オブジェクトを含むビュー。|  
|[CScrollView](../mfc/reference/cscrollview-class.md)|`CFormView`、`CRecordView`と `CDaoRecordView`の基本クラスです。  ビューのコンテンツをスクロールする実装。|  
|[CFormView](../mfc/reference/cformview-class.md)|フォーム ビュー、コントロールを含むビュー。  フォーム ベースのアプリケーションを一つ以上のこのようなフォーム インターフェイスを提供します。|  
|[CHtmlView](../mfc/reference/chtmlview-class.md)|アプリケーションのユーザーが WWW サイトを参照できる Web ブラウザーのビューは、ローカル ファイル システムとネットワーク フォルダー。  Web ブラウザーの表示は、Active ドキュメント コンテナーとして使用できます。|  
|[CRecordView](../mfc/reference/crecordview-class.md)|コントロールの ODBC データベース レコードを表示するフォーム ビュー。  プロジェクトの ODBC を選択すると、ビューの基本クラスは `CRecordView`です。  ビューは `CRowset` オブジェクトにアタッチされます。|  
|[CDaoRecordView クラス](../mfc/reference/cdaorecordview-class.md)|コントロールの DAO データベース レコードを表示するフォーム ビュー。  プロジェクトの DAO サポートを選択した場合、ビューの基本クラスは `CDaoRecordView`です。  ビューは `CDaoRecordset` オブジェクトにアタッチされます。|  
|[COleDBRecordView](../mfc/reference/coledbrecordview-class.md)|コントロールの OLE DB レコードを表示するフォーム ビュー。  プロジェクトの OLE DB サポートを選択した場合、ビューの基本クラスは `COleDBRecordView`です。  ビューは `CRowset` オブジェクトにアタッチされます。|  
  
> [!NOTE]
>  MFC 4.0 以降では、`CEditView` は `CCtrlView`から派生されます。  
  
 アプリケーションでこれらのクラスを使用するには、アプリケーションからビュー クラスを派生してください。  関連情報については、[ビューをスクロールし、スケーリングします。](../mfc/scrolling-and-scaling-views.md)を参照してください。  データベース クラスの詳細については、「[概要: データベース プログラミング](../data/data-access-programming-mfc-atl.md)」を参照してください。  
  
## 参照  
 [ビューの使い方](../mfc/using-views.md)