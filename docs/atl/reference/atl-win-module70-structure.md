---
title: "_ATL_WIN_MODULE70 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_ATL_WIN_MODULE70"
  - "ATL::_ATL_WIN_MODULE70"
  - "ATL._ATL_WIN_MODULE70"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ATL_WIN_MODULE70 構造体"
  - "ATL_WIN_MODULE70 構造体"
ms.assetid: a0aaf3ea-ca77-46ec-bd53-4dfb61dffbea
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# _ATL_WIN_MODULE70 構造体
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ATL ウィンドウでコードによって使用されます。  
  
## 構文  
  
```  
  
      struct _ATL_WIN_MODULE70{  
   UNIT cbSize;  
   CRITICAL_SECTION m_csWindowCreate;  
   _AtlCreateWndData* m_pCreateWndList;  
   CSimpleArray<ATOM> m_rgWindowClassAtoms;  
};  
```  
  
## メンバー  
 `cbSize`  
 バージョン管理に使用する、構造体のサイズ。  
  
 `m_csWindowCreate`  
 ペインの登録コードへのアクセスをシリアル化するために使用します。  ATL によって内部的に使用されます。  
  
 **m\_pCreateWndList**  
 ウィンドウをオブジェクトにバインドするために使用します。  ATL によって内部的に使用されます。  
  
 **m\_rgWindowClassAtoms**  
 終了で正しく登録解除したりできるようにウィンドウ クラスを登録を追跡するために使用します。  ATL によって内部的に使用されます。  
  
## 解説  
 [\_ATL\_WIN\_MODULE](../Topic/_ATL_WIN_MODULE.md) は `_ATL_WIN_MODULE70`の typedef として定義されます。  
  
## 必要条件  
 **ヘッダー:** atlbase.h  
  
## 参照  
 [構造体](../../atl/reference/atl-structures.md)