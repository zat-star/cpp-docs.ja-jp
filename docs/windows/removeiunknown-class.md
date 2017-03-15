---
title: "RemoveIUnknown クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::Details::RemoveIUnknown"
dev_langs: 
  - "C++"
ms.assetid: 998e711a-7d1a-44c6-a016-e6167aa40863
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# RemoveIUnknown クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL のインフラストラクチャをサポートします。コードから直接使用するためのものではありません。  
  
## 構文  
  
```  
template <  
   typename T  
>  
struct RemoveIUnknown;  
  
template <  
   typename T  
>  
class RemoveIUnknown : public T;  
```  
  
#### パラメーター  
 `T`  
 クラス。  
  
## 解説  
 `IUnknown`のベースの型と同じですが、仮想 `QueryInterface`揃える、`AddRef`と `Release` メンバー関数を持つ型。  
  
 既定で、COM メソッドは仮想 `QueryInterface`、`AddRef`および解放メソッドを提供します。  ただし、`ComPtr` は仮想メソッドのオーバーヘッドを必要としません。  `RemoveIUnknown` は プライベートな、仮想 `QueryInterface`、`AddRef`と `Release` のメソッドによって、このオーバーヘッドを削除します。  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|`ReturnType`|テンプレート パラメーター `T` と同じですが、型のシノニムに IUnknown の仮想メンバー。|  
  
## 継承階層  
 `T`  
  
 `RemoveIUnknown`  
  
## 必要条件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL::Details  
  
## 参照  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)