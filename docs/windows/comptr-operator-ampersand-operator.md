---
title: "ComPtr::operator&amp; 演算子 | Microsoft Docs"
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
  - "client/Microsoft::WRL::ComPtr::operator&"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator& 演算子"
ms.assetid: 2d77fda6-f4b2-45c1-8a0e-fbc355013531
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtr::operator&amp; 演算子
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`ComPtr` オブジェクトに関連付けられたインターフェイスを解放し、`ComPtr` オブジェクトのアドレスを取得します。  
  
## 構文  
  
```cpp  
Details::ComPtrRef<WeakRef> operator&()  
  
const Details::ComPtrRef<const WeakRef> operator&() const  
```  
  
## 戻り値  
 現在の `ComPtr`への弱い参照。  
  
## 解説  
 このメソッドは [ComPtr::GetAddressOf](../Topic/ComPtr::GetAddressOf%20Method.md) とこのメソッドがインターフェイス ポインターへの参照を解放することです。  インターフェイス ポインターのアドレスを必要とするを使用します。そのインターフェイスを解放しない場合 `ComPtr::GetAddressOf` を呼び出さないでください。  
  
## 必要条件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [ComPtr クラス](../windows/comptr-class.md)