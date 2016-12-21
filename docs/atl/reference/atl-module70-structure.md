---
title: "_ATL_MODULE70 構造体 | Microsoft Docs"
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
  - "_ATL_MODULE70"
  - "ATL::_ATL_MODULE70"
  - "ATL._ATL_MODULE70"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ATL_MODULE70 構造体"
  - "ATL_MODULE70 構造体"
ms.assetid: b059b2c8-dfd1-4ac9-b07d-39df638cc7b3
caps.latest.revision: 16
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _ATL_MODULE70 構造体
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

すべての ATL モジュールによって使用されるデータが含まれます。  
  
## 構文  
  
```  
  
      struct _ATL_MODULE70{  
   UINT cbSize;  
   LONG m_nLockCnt;  
   _ATL_TERMFUNC_ELEM* m_pTermFuncs;  
   CComCriticalSection m_csStaticDataInitAndTypeInfo;  
};  
```  
  
## メンバー  
 `cbSize`  
 バージョン管理に使用する、構造体のサイズ。  
  
 `m_nLockCnt`  
 モジュールがライブどの程度設定するかを決定する計算を参照してください。  
  
 **m\_pTermFuncs**  
 ATL がシャットダウンするというように登録された関数を追跡します。  
  
 **m\_csStaticDataInitAndTypeInfo**  
 マルチスレッドの内部状態データへのアクセスを調整するために使用します。  
  
## 解説  
 [\_ATL\_MODULE](../Topic/_ATL_MODULE.md) は `_ATL_MODULE70`の typedef として定義されます。  
  
## 必要条件  
 **ヘッダー:** atlbase.h  
  
## 参照  
 [構造体](../../atl/reference/atl-structures.md)