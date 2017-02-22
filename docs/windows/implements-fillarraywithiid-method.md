---
title: "Implements::FillArrayWithIid メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Implements::FillArrayWithIid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "FillArrayWithIid メソッド"
ms.assetid: b2e62e3f-0ab9-4c70-aad7-856268544f44
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# Implements::FillArrayWithIid メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

現在の zeroth のテンプレート パラメーターによって指定された型指定された配列の要素のインターフェイス ID を挿入します。  
  
## 構文  
  
```  
__forceinline static void FillArrayWithIid(  
   unsigned long &index,  
   _In_ IID* iids  
);  
```  
  
#### パラメーター  
 `index`  
 この操作の開始の配列要素を示す 0 から始まるインデックス。  この操作が完了したら、`index` は 1.でインクリメントされます。  
  
 `iids`  
 型 IID の配列。  
  
## 解説  
 内部ヘルパー関数です。  
  
## 必要条件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [Implements 構造体](../Topic/Implements%20Structure.md)