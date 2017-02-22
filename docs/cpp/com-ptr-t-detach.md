---
title: "_com_ptr_t::Detach | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_ptr_t::Detach"
  - "_com_ptr_t.Detach"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Detach メソッド"
ms.assetid: 0652053e-af37-44e9-a278-2522212ebfed
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _com_ptr_t::Detach
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 カプセル化されたインターフェイス ポインターを抽出して返します。  
  
## 構文  
  
```  
  
Interface* Detach( ) throw( );  
  
```  
  
## 解説  
 カプセル化されたインターフェイス ポインターを抽出して返した後、カプセル化されたポインター ストレージを **NULL** にクリアします。  これによって、カプセル化からインターフェイス ポインターが削除されます。  返されたインターフェイス ポインターの **Release** を呼び出すかどうかは開発者の責任です。  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [\_com\_ptr\_t クラス](../cpp/com-ptr-t-class.md)