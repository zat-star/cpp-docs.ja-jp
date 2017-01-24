---
title: "HString::HString コンストラクター | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HString::HString"
dev_langs: 
  - "C++"
ms.assetid: 6da12785-ed01-4720-a004-667db60298f1
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HString::HString コンストラクター
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

HString クラスの新しいインスタンスを初期化します。  
  
## 構文  
  
```cpp  
  
HString(HSTRING hstr = nullptr) throw();  
HString(HString&& other) throw();  
```  
  
#### パラメーター  
 `hstr`  
 HSTRING のハンドル。  
  
 `other`  
 HString の既存のオブジェクト。  
  
## 解説  
 最初のコンストラクターは空である HString オブジェクトを初期化します。  
  
 2 番目のコンストラクターは `other` 既存のパラメーターへの HString オブジェクトを初期化し、`other` パラメーターを破棄します。  
  
## 必要条件  
 **ヘッダー:** corewrappers.h  
  
 **名前空間:** Microsoft::WRL::Wrappers  
  
## 参照  
 [HString クラス](../windows/hstring-class.md)