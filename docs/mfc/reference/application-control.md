---
title: "アプリケーションの制御 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "アプリケーションの制御"
ms.assetid: c1f69f15-e0fe-4515-9f36-d63d31869deb
caps.latest.revision: 12
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# アプリケーションの制御
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE アプリケーションやオブジェクトの多くのコントロールが必要です。  OLE システム DLL は起動必要があり、アプリケーションを自動的に解放するために、オブジェクトの運用および変更などを調整します。  このトピックの関数はこれらの要件を満たします。  OLE システム DLL によって呼び出されることに加え、これらの関数は、アプリケーションでも呼び出す必要があります。  
  
### アプリケーション コントロール  
  
|||  
|-|-|  
|[AfxOleCanExitApp](../Topic/AfxOleCanExitApp.md)|アプリケーションが終了できるかどうかを示します。|  
|[AfxOleGetMessageFilter](../Topic/AfxOleGetMessageFilter.md)|アプリケーションの現在のメッセージ フィルターを取得します。|  
|[AfxOleGetUserCtrl](../Topic/AfxOleGetUserCtrl.md)|現在の制御フラグを取得します。|  
|[AfxOleSetUserCtrl](../Topic/AfxOleSetUserCtrl.md)|設定またはクリア制御フラグ。|  
|[AfxOleLockApp](../Topic/AfxOleLockApp.md)|フレームワークの実行中のアプリケーションのオブジェクトの数のグローバル数をインクリメントします。|  
|[AfxOleUnlockApp](../Topic/AfxOleUnlockApp.md)|フレームワークの実行中のアプリケーションのオブジェクトの数をデクリメントします。|  
|[AfxOleRegisterServerClass](../Topic/AfxOleRegisterServerClass.md)|OLE システム レジストリにサーバーが登録されます。|  
|[AfxOleSetEditMenu](../Topic/AfxOleSetEditMenu.md)|*型名の* コマンド オブジェクトのユーザー インターフェイスを実装します。|  
  
## 参照  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)