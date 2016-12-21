---
title: "Implements::CanCastTo メソッド | Microsoft Docs"
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
  - "implements/Microsoft::WRL::Implements::CanCastTo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CanCastTo メソッド"
ms.assetid: a8e85c7d-4dcd-446d-bebc-a97da46ce44a
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Implements::CanCastTo メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

指定されたインターフェイスへのポインターを取得します。  
  
## 構文  
  
```  
__forceinline HRESULT CanCastTo(  
   REFIID riid,  
   _Deref_out_ void **ppv  
);  
```  
  
#### パラメーター  
 `riid`  
 インターフェイス ID への参照。  
  
 `ppv`  
 、ポインター `riid`で指定されたインターフェイスに成功した。  
  
## 戻り値  
 成功した場合は S\_OK; それ以外の場合は、エラーを示す E\_NOINTERFACE などの HRESULT を返します。  
  
## 解説  
 これは、QueryInterface 操作を実行する内部ヘルパー関数です。  
  
## 必要条件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [Implements 構造体](../Topic/Implements%20Structure.md)