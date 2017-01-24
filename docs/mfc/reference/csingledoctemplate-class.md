---
title: "CSingleDocTemplate クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSingleDocTemplate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSingleDocTemplate クラス"
  - "ドキュメント テンプレート, single"
  - "シングル ドキュメント インターフェイス (SDI), アプリケーション"
  - "テンプレート, SDI"
ms.assetid: 4f3a8212-81ee-48a0-ad22-e0ed7c36a391
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSingleDocTemplate クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

SDI \(シングル ドキュメント インターフェイス\) を実装するドキュメント テンプレートを定義します。  
  
## 構文  
  
```  
class CSingleDocTemplate : public CDocTemplate  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CSingleDocTemplate::CSingleDocTemplate](../Topic/CSingleDocTemplate::CSingleDocTemplate.md)|`CSingleDocTemplate` オブジェクトを構築します。|  
  
## 解説  
 SDI アプリケーションでは、ドキュメントを表示するには、メイン フレーム ウィンドウを使用します; 1 個のドキュメントが一度に表示されます。  
  
 ドキュメント テンプレートは、3 種類のクラス間の関係を定義します:  
  
-   、**CDocument**から派生するドキュメントのクラス。  
  
-   ドキュメント クラスのデータを表示するビュー クラス、先頭にが表示されます。  `CView`、`CScrollView`、`CFormView`、または `CEditView`からこのクラスを派生させることができます。  \(または `CEditView` を直接使用できます\)。  
  
-   ビューを含むフレーム ウィンドウのクラス。  SDI ドキュメント テンプレートごとに、`CFrameWnd`からこのクラスを取得できます。; メイン フレーム ウィンドウの動作をカスタマイズする必要がない場合は、独自のクラスを派生せずに `CFrameWnd` を直接使用できます。  
  
 SDI アプリケーションでは、通常、ドキュメントの 1 種類がサポートしているため `CSingleDocTemplate` の 1 オブジェクトのみがあります。  1 個のドキュメントが一度に表示されます。  
  
 コンストラクター以外\) `CSingleDocTemplate` のメンバー関数を呼び出す必要はありません。  フレームワークは `CSingleDocTemplate` のオブジェクトを内部処理します。  
  
 `CSingleDocTemplate`の使用の詳細については、[ドキュメント テンプレートとドキュメント\/ビューの作成手順](../../mfc/document-templates-and-the-document-view-creation-process.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md)  
  
 `CSingleDocTemplate`  
  
## 必要条件  
 **ヘッダー:** afxwin.h  
  
## 参照  
 [MFC DOCKTOOL サンプル](../../top/visual-cpp-samples.md)   
 [CDocTemplate クラス](../../mfc/reference/cdoctemplate-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDocTemplate クラス](../../mfc/reference/cdoctemplate-class.md)   
 [CDocument クラス](../Topic/CDocument%20Class.md)   
 [CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)   
 [CMultiDocTemplate クラス](../../mfc/reference/cmultidoctemplate-class.md)   
 [CView クラス](../Topic/CView%20Class.md)   
 [CWinApp クラス](../../mfc/reference/cwinapp-class.md)