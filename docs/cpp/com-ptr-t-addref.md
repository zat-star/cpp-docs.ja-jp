---
title: "_com_ptr_t::AddRef | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_ptr_t::AddRef"
  - "_com_ptr_t.AddRef"
  - "AddRef"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddRef メソッド [C++], インターフェイス ポインター"
ms.assetid: c104dac3-aad3-40bb-a298-75c6cd0e63a2
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _com_ptr_t::AddRef
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 カプセル化されたインターフェイス ポインターで **IUnknown** の `AddRef` メンバー関数を呼び出します。  
  
## 構文  
  
```  
  
void AddRef( );  
  
```  
  
## 解説  
 ポインターが **NULL** の場合、カプセル化されたインターフェイス ポインターで `IUnknown::AddRef` を呼び出し、`E_POINTER` エラーを発生させます。  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [\_com\_ptr\_t クラス](../cpp/com-ptr-t-class.md)