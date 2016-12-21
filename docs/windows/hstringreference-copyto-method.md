---
title: "HStringReference::CopyTo メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: 179d9b14-1ced-4b16-b297-19ca1e92a462
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HStringReference::CopyTo メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

現在の HStringReference オブジェクトを HSTRING オブジェクトにコピーします。  
  
## 構文  
  
```  
  
HRESULT CopyTo(  
   _Out_ HSTRING *str  
   ) const throw();  
```  
  
#### パラメーター  
 `str`  
 コピーを受信する HSTRING です。  
  
## 解説  
 このメソッドは [WindowsDuplicateString](http://msdn.microsoft.com/library/br224634.aspx) 関数を呼び出します。  
  
## 必要条件  
 **ヘッダー:** corewrappers.h  
  
 **名前空間:** Microsoft::WRL::Wrappers  
  
## 参照  
 [HStringReference クラス](../windows/hstringreference-class.md)