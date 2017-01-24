---
title: "RuntimeClass::GetIids メソッド | Microsoft Docs"
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
  - "implements/Microsoft::WRL::RuntimeClass::GetIids"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetIids メソッド"
ms.assetid: 826a67d1-ebc4-4940-b5d5-7cd66885e4a1
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# RuntimeClass::GetIids メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

RuntimeClass の現在のオブジェクトによって実装されるインターフェイス ID を格納できる配列を取得します。  
  
## 構文  
  
```  
STDMETHOD(  
   GetIids  
)  
   (_Out_ ULONG *iidCount,   
   _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids);  
```  
  
#### パラメーター  
 `iidCount`  
 この操作が完了すると、`iids`配列の要素の総数。  
  
 `iids`  
 この操作が完了すると、インターフェイス ID の配列へのポインター。  
  
## 戻り値  
 成功した場合は S\_OK; それ以外の場合、E\_OUTOFMEMORY。  
  
## 必要条件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [RuntimeClass クラス](../windows/runtimeclass-class.md)