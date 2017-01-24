---
title: "ActivationFactory::GetIids メソッド | Microsoft Docs"
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
  - "module/Microsoft::WRL::ActivationFactory::GetIids"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetIids メソッド"
ms.assetid: 0983d709-d155-4d65-aae4-5b2c8bb0fede
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ActivationFactory::GetIids メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

実装されたインターフェイスの ID の配列を取得します。  
  
## 構文  
  
```  
STDMETHOD(  
   GetIids  
)(_Out_ ULONG *iidCount, _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids);  
```  
  
#### パラメーター  
 `iidCount`  
 この操作が完了すると、`iids` の配列の interace の ID の数。  
  
 `iids`  
 この操作が完了すると、実装されているインターフェイスの ID の配列。  
  
## 戻り値  
 成功した場合は S\_OK; それ以外の場合は失敗を示す HRESULT を返します。  E\_OUTOFMEMORY は有効なエラー HRESULT です。  
  
## 必要条件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [ActivationFactory クラス](../windows/activationfactory-class.md)