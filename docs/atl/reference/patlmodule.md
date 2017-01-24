---
title: "_pAtlModule | Microsoft Docs"
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
  - "ATLBASE/_pAtlModule"
  - "_pAtlModule"
  - "ATL::_pAtlModule"
  - "ATL._pAtlModule"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_pAtlModule 変数"
  - "pAtlModule 変数"
ms.assetid: 0ecde3a9-3f4d-4c7b-bb54-713ce05c4777
caps.latest.revision: 13
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _pAtlModule
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

現在のモジュールへのポインターを格納するグローバル変数。  
  
## 構文  
  
```  
__declspec(selectany) CAtlModule * _pAtlModule  
```  
  
## 解説  
 旧式 \(現在の\) クラス [CComModule](../../atl/reference/ccommodule-class.md) が Visual C\+\+ 6.0 で指定したこのグローバル変数のメソッドが機能を提供するために使用できます。  
  
## 使用例  
 [!code-cpp[NVC_ATL_Windowing#97](../../atl/codesnippet/CPP/patlmodule_1.cpp)]  
  
## 必要条件  
 atlbase.h**Header:**  
  
## 参照  
 [グローバル変数](../Topic/ATL%20Global%20Variables.md)