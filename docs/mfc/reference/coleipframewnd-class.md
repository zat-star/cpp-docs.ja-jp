---
title: "COleIPFrameWnd クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleIPFrameWnd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleIPFrameWnd クラス"
  - "埋め込み先編集"
  - "OLE, 編集"
  - "OLE, 埋め込み先編集の有効化"
ms.assetid: 24abb2cb-826c-4dda-a287-d8a8900a5763
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# COleIPFrameWnd クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

アプリケーションの埋め込み先編集ウィンドウの基本クラスです。  
  
## 構文  
  
```  
class COleIPFrameWnd : public CFrameWnd  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[COleIPFrameWnd::COleIPFrameWnd](../Topic/COleIPFrameWnd::COleIPFrameWnd.md)|`COleIPFrameWnd` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[COleIPFrameWnd::OnCreateControlBars](../Topic/COleIPFrameWnd::OnCreateControlBars.md)|項目が埋め込み先編集が有効なときに、フレームワークによって呼び出されます。|  
|[COleIPFrameWnd::RepositionFrame](../Topic/COleIPFrameWnd::RepositionFrame.md)|埋め込み先編集ウィンドウの位置を変更するために、フレームワークによって呼び出されます。|  
  
## 解説  
 このクラスは、コンテナー アプリケーションのドキュメント ウィンドウ内のコントロール バーを作成して設定します。  また、ユーザーが埋め込み先編集ウィンドウのサイズを変更すると [COleResizeBar](../../mfc/reference/coleresizebar-class.md) の埋め込みオブジェクトによって生成される通知を処理します。  
  
 `COleIPFrameWnd`の使用の詳細については、" " [&#91;アクティブ化&#93;](../../mfc/activation-cpp.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `COleIPFrameWnd`  
  
## 必要条件  
 **Header:** afxole.h  
  
## 参照  
 [MFC HIERSVR サンプル](../../top/visual-cpp-samples.md)   
 [CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)