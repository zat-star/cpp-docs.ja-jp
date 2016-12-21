---
title: "_ATL_COM_MODULE70 構造体 | Microsoft Docs"
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
  - "ATL::_ATL_COM_MODULE70"
  - "ATL._ATL_COM_MODULE70"
  - "_ATL_COM_MODULE70"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ATL_COM_MODULE70 構造体"
  - "ATL_COM_MODULE70 構造体"
ms.assetid: 5b0b2fd0-bdeb-4c7e-8870-78fa69ace6e6
caps.latest.revision: 15
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _ATL_COM_MODULE70 構造体
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ATL で COM 関連のコードによって使用されます。  
  
## 構文  
  
```  
  
      struct _ATL_COM_MODULE70{  
   UINT cbSize;  
   HINSTANCE m_hInstTypeLib;  
   _ATL_OBJMAP_ENTRY** m_ppAutoObjMapFirst;  
   _ATL_OBJMAP_ENTRY** m_ppAutoObjMapLast;  
   CRITICAL_SECTION m_csObjMap;  
};  
```  
  
## メンバー  
 `cbSize`  
 バージョン管理に使用する、構造体のサイズ。  
  
 `m_hInstTypeLib`  
 このモジュールのタイプ ライブラリへのハンドルのインスタンス。  
  
 **m\_ppAutoObjMapFirst**  
 このモジュールのオブジェクトのエントリ マップの開始を示す配列要素のアドレス。  
  
 **m\_ppAutoObjMapLast**  
 このモジュールのオブジェクト マップのエントリの終了を示す配列要素のアドレス。  
  
 `m_csObjMap`  
 オブジェクト マップのエントリへのアクセスをシリアル化するクリティカル セクション。  ATL によって内部的に使用されます。  
  
## 解説  
 [\_ATL\_COM\_MODULE](../Topic/_ATL_COM_MODULE.md) は `_ATL_COM_MODULE70`の typedef として定義されます。  
  
## 必要条件  
 **ヘッダー:** atlbase.h  
  
## 参照  
 [構造体](../../atl/reference/atl-structures.md)