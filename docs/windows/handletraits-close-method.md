---
title: "HANDLETraits::Close メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::Close"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Close メソッド"
ms.assetid: 3c631a7c-ccce-472a-b1da-aab8fa815c13
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# HANDLETraits::Close メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

指定したハンドルを閉じます。  
  
## 構文  
  
```  
inline static bool Close(  
   _In_ Type h  
);  
```  
  
#### パラメーター  
 `h`  
 終了するハンドル。  
  
## 戻り値  
 ハンドル `h` が正常に終了**true** ; それ以外の場合は **false**。  
  
## 必要条件  
 **ヘッダー:** corewrappers.h  
  
 **名前空間:** Microsoft::WRL::Wrappers::HandleTraits  
  
## 参照  
 [HANDLETraits 構造体](../windows/handletraits-structure.md)