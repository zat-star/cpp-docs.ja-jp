---
title: "CComSimpleThreadAllocator クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComSimpleThreadAllocator"
  - "ATL::CComSimpleThreadAllocator"
  - "ATL.CComSimpleThreadAllocator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL スレッド"
  - "ATL スレッド, 割り当て"
  - "CComSimpleThreadAllocator クラス"
  - "スレッド処理 [ATL], 選択 (スレッドを)"
ms.assetid: 66b2166a-8c50-49fd-b8e4-7f293470327d
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CComSimpleThreadAllocator クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、クラス `CComAutoThreadModule`のスレッドの選択を管理します。  
  
## 構文  
  
```  
  
class CComSimpleThreadAllocator  
  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CComSimpleThreadAllocator::GetThread](../Topic/CComSimpleThreadAllocator::GetThread.md)|スレッドを選択します。|  
  
## 解説  
 `CComSimpleThreadAllocator` は [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)のスレッドの選択を管理します。  `CComSimpleThreadAllocator::GetThread` は、各スレッドを単に示すように、シーケンスから次の 1 を返します。  
  
## 必要条件  
 atlbase.h**Header:**  
  
## 参照  
 [CComApartment クラス](../../atl/reference/ccomapartment-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)