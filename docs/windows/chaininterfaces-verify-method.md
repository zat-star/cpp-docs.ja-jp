---
title: "ChainInterfaces::Verify メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::ChainInterfaces::Verify"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Verify メソッド"
ms.assetid: c591e130-8686-4130-ba69-1aaedc250038
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# ChainInterfaces::Verify メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`I9` してテンプレート パラメーター `I0` で定義されている各インターフェイスが IUnknown または IInspectable から継承すること、および `I0` が `I1` から `I9`から継承することを確認します。  
  
## 構文  
  
```  
WRL_NOTHROW __forceinline static void Verify();  
```  
  
## 解説  
 検証操作が失敗した場合、`static_assert` は失敗を示すエラー メッセージが表示されます。  
  
## 解説  
 テンプレート パラメーター `I0` と `I1` は必須で、`I9` してパラメーター `I2` は省略可能です。  
  
## 必要条件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [ChainInterfaces 構造体](../windows/chaininterfaces-structure.md)