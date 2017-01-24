---
title: "AsWeak 関数 | Microsoft Docs"
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
  - "client/Microsoft::WRL::AsWeak"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AsWeak 関数"
ms.assetid: a6f10cfc-c1d6-4761-adb9-1a119cc99913
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# AsWeak 関数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

指定されたインスタンスへの弱い参照を取得します。  
  
## 構文  
  
```  
template<  
   typename T  
>  
HRESULT AsWeak(  
   _In_ T* p,  
   _Out_ WeakRef* pWeak  
);  
```  
  
#### パラメーター  
 `T`  
 パラメーター `p`の型へのポインター。  
  
 `p`  
 型のインスタンス。  
  
 `pWeak`  
 この操作が完了すると、パラメーター `p`への弱い参照へのポインター。  
  
## 戻り値  
 この操作が成功した場合は、S\_OK; それ以外の場合は、失敗の理由を示すエラー HRESULT。  
  
## 必要条件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)