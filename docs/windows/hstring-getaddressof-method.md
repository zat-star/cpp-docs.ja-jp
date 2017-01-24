---
title: "HString::GetAddressOf メソッド | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HString::GetAddressOf"
dev_langs: 
  - "C++"
ms.assetid: 6050decf-5f99-49f0-9497-1c8192c485ae
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HString::GetAddressOf メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

基になる HSTRING ハンドルへのポインターを取得します。  
  
## 構文  
  
```  
HSTRING* GetAddressOf() throw()  
```  
  
## 戻り値  
 基になる HSTRING のハンドルへのポインター。  
  
## 解説  
 この操作の後、基になる HSTRING ハンドルの文字列値は破棄されます。  
  
## 必要条件  
 **ヘッダー:** corewrappers.h  
  
 **名前空間:** Microsoft::WRL::Wrappers  
  
## 参照  
 [HString クラス](../windows/hstring-class.md)