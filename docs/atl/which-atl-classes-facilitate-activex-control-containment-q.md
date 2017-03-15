---
title: "どの ATL クラスを使用すると ActiveX コントロール コンテインメントに役立ちますか? | Microsoft Docs"
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
  - "ActiveX コントロール コンテナー [C++], ATL コントロール ホスト"
  - "ホスト (ATL を使ってコントロールを)"
ms.assetid: 803a4605-7f4c-4139-8638-49d8783d31b0
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# どの ATL クラスを使用すると ActiveX コントロール コンテインメントに役立ちますか?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ATL のコントロール ホスト コードは ATL クラスを使用する必要はありません; **"AtlAxWin80"** のウィンドウを作成し、コントロール ホスト API を必要に応じて使用できます。詳細については、[ATL のコントロール ホスト API は何ですか。](../atl/what-is-the-atl-control-hosting-api-q.md)を参照\)。  ただし、次のクラスは、コンテインメントの機能を使用しやすくなります。  
  
|Class|説明|  
|-----------|--------|  
|[CAxWindow](../atl/reference/caxwindow-class.md)|ウィンドウを作成し、コントロールを作成することやウィンドウにホスト オブジェクトでコントロールを結合し、のインターフェイス ポインターを取得するメソッドを提供する **"AtlAxWin80"** のウィンドウをラップします。|  
|[CAxWindow2T](../Topic/CAxWindow2T%20Class.md)|ウィンドウを作成し、コントロールを作成することやウィンドウにホスト オブジェクト内のライセンス コントロールを結合し、のインターフェイス ポインターを取得するメソッドを提供する **"AtlAxWinLic80"** のウィンドウをラップします。|  
|[CComCompositeControl](../atl/reference/ccomcompositecontrol-class.md)|ようにダイアログ リソースに基づいて ActiveX コントロール クラスの基本クラスとして機能します。  このようなコントロールは、他の ActiveX コントロールを含めることができます。|  
|[CAxDialogImpl](../Topic/CAxDialogImpl%20Class.md)|ダイアログ リソースに基づいて、ダイアログ クラスの基本クラスとして機能します。  このようなダイアログは ActiveX コントロールを含めることができます。|  
|[CWindow](../atl/reference/cwindow-class.md)|メソッドは、コントロールのインターフェイス ポインターを返すホスト ウィンドウの ID を持つ [GetDlgControl](../Topic/CWindow::GetDlgControl.md)提供します。  また、`CWindow` によって公開される Windows API ラッパーは一般的に、ウィンドウ管理が簡単になります。|  
  
## 参照  
 [コントロール コンテインメント : Q & A 集](../atl/atl-control-containment-faq.md)