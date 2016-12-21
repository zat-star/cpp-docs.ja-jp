---
title: "_AtlCreateWndData 構造体 | Microsoft Docs"
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
  - "ATL::_AtlCreateWndData"
  - "ATL._AtlCreateWndData"
  - "_AtlCreateWndData"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_AtlCreateWndData 構造体"
  - "AtlCreateWndData 構造体"
ms.assetid: 76ed5382-bfbf-4b8b-8a29-912688dfd2ae
caps.latest.revision: 15
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _AtlCreateWndData 構造体
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

この構造体は、ATL ウィンドウ コードでクラスのインスタンス データが含まれます。  
  
## 構文  
  
```  
  
      struct _AtlCreateWndData{  
   void* m_pThis;  
   DWORD m_dwThreadID;  
   _AtlCreateWndData* m_pNext;  
};  
```  
  
## メンバー  
 **m\_pThis**  
 ウィンドウ プロシージャのクラスのインスタンスへのアクセスを取得するために使用されます **this** のポインター。  
  
 `m_dwThreadID`  
 現在のクラスのインスタンスのスレッドの ID。  
  
 **m\_pNext**  
 `_AtlCreateWndData` で次のオブジェクトへのポインター。  
  
## 必要条件  
 **ヘッダー:** atlbase.h  
  
## 参照  
 [構造体](../../atl/reference/atl-structures.md)