---
title: "COM インターフェイスのエントリ ポイント | Microsoft Docs"
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
  - "COM インターフェイス, 開始ポイント"
  - "開始ポイント, COM インターフェイス"
  - "MFC COM, COM インターフェイス エントリ ポイント"
  - "MFC, 管理 (状態データを)"
  - "OLE, インターフェイス エントリ ポイント"
  - "状態管理, OLE/COM インターフェイス"
ms.assetid: 9e7421dc-0731-4748-9e1b-90acbaf26d77
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COM インターフェイスのエントリ ポイント
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

COM インターフェイスのメンバー関数の場合は、適切なグローバル状態を維持するために [METHOD\_PROLOGUE](../Topic/METHOD_PROLOGUE.md) マクロを実行エクスポートされたインターフェイスでメソッドを使用します。  
  
 通常、`CCmdTarget`によって実装されるインターフェイスのメンバー関数\-派生オブジェクトが既に `pThis` ポインターの自動初期化を提供するには、このマクロを使用します。  たとえば、次のようになります。  
  
 [!code-cpp[NVC_MFCConnectionPoints#5](../mfc/codesnippet/CPP/com-interface-entry-points_1.cpp)]  
  
 詳細については、MFC\/OLE **IUnknown** の実装の [テクニカル ノート 38](../mfc/tn038-mfc-ole-iunknown-implementation.md) を参照してください。  
  
 `METHOD_PROLOGUE` マクロは次のように定義されます。:  
  
 `#define METHOD_PROLOGUE(theClass, localClass) \`  
  
 `theClass* pThis = \`  
  
 `((theClass*)((BYTE*)this - offsetof(theClass, m_x##localClass))); \`  
  
 `AFX_MANAGE_STATE(pThis->m_pModuleState) \`  
  
 グローバル状態の管理に関係するマクロの部分は次のとおりです。:  
  
 `AFX_MANAGE_STATE( pThis->m_pModuleState )`  
  
 この式には、*m\_pModuleState は* コンテナー オブジェクトのメンバー変数と見なされます。  これは `CCmdTarget` の基本クラスによってオブジェクトがインスタンス化されると、実装され、適切な値に `COleObjectFactory`によって初期化されます。  
  
## 参照  
 [MFC モジュールの状態データの管理](../mfc/managing-the-state-data-of-mfc-modules.md)