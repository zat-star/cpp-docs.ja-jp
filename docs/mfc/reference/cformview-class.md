---
title: "CFormView クラス | Microsoft Docs"
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
  - "CFormView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFormView クラス"
  - "フォーム ビュー"
  - "ビュー, コンテナーであるコントロール"
ms.assetid: a99ec313-36f0-4f28-9d2b-de11de14ac19
caps.latest.revision: 23
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CFormView クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

フォーム ビューの基底クラスです。  
  
## 構文  
  
```  
class CFormView : public CScrollView  
```  
  
## メンバー  
  
### プロテクト コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CFormView::CFormView](../Topic/CFormView::CFormView.md)|`CFormView` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CFormView::IsInitDlgCompleted](../Topic/CFormView::IsInitDlgCompleted.md)|初期化中に同期に使用されます。|  
  
## 解説  
 フォーム ビューは、基本的には、コントロールを含むビューです。  これらのコントロールは、ダイアログ テンプレート リソースに基づいて配置されます。  アプリケーションでフォームが必要な場合は、`CFormView` を使用します。  これらのビューでは、必要に応じて、[CScrollView](../../mfc/reference/cscrollview-class.md) 機能を使用してスクロールがサポートされます。  
  
 [フォーム ベースのアプリケーションを作成する](../Topic/Creating%20a%20Forms-Based%20MFC%20Application.md)場合は、`CFormView` に基づいてそのビュー クラスを作成することで、フォーム ベースのアプリケーションにすることができます。  
  
 新しい[フォームに関するトピック](../Topic/Form%20Views%20\(MFC\).md)をドキュメント ビュー ベースのアプリケーションに挿入することもできます。  アプリケーションで最初はフォームをサポートしていなかった場合でも、新しいフォームを挿入するときに、Visual C\+\+ によってフォームのサポートが追加されます。  
  
 MFC アプリケーション ウィザードと \[クラスの追加\] コマンドは、フォーム ベースのアプリケーションを作成する方法として推奨されています。  これらの方法を使用せずにフォーム ベースのアプリケーションを作成する必要がある場合は、「[フォーム ベースのアプリケーションの作成](../Topic/Creating%20a%20Forms-Based%20MFC%20Application.md)」を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CView](../Topic/CView%20Class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 `CFormView`  
  
## 必要条件  
 **ヘッダー:** afxext.h  
  
## 参照  
 [MFC サンプル SNAPVW](../../top/visual-cpp-samples.md)   
 [MFC サンプル VIEWEX](../../top/visual-cpp-samples.md)   
 [CScrollView クラス](../../mfc/reference/cscrollview-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDialog クラス](../../mfc/reference/cdialog-class.md)   
 [CScrollView クラス](../../mfc/reference/cscrollview-class.md)   
 [CView::OnUpdate](../Topic/CView::OnUpdate.md)   
 [CView::OnInitialUpdate](../Topic/CView::OnInitialUpdate.md)   
 [CView::OnPrint](../Topic/CView::OnPrint.md)   
 [CWnd::UpdateData](../Topic/CWnd::UpdateData.md)   
 [CScrollView::ResizeParentToFit](../Topic/CScrollView::ResizeParentToFit.md)