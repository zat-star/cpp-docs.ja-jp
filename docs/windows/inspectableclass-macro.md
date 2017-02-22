---
title: "InspectableClass マクロ | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::InspectableClass"
dev_langs: 
  - "C++"
ms.assetid: ff390b26-58cc-424f-87ac-1fe3cc692b59
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# InspectableClass マクロ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ランタイム クラス名と信頼レベルを設定します。  
  
## 構文  
  
```cpp  
  
InspectableClass(  
   runtimeClassName,   
   trustLevel)  
  
```  
  
#### パラメーター  
 `runtimeClassName`  
 ランタイム クラス名のテキスト形式の完全な名前です。  
  
 `trustLevel`  
 [TrustLevel](http://msdn.microsoft.com/library/br224625.aspx) 列挙値の 1 つです。  
  
## 解説  
 `InspectableClass` マクロは [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]型とのみ使用できます。  
  
## 必要条件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [RuntimeClass クラス](../windows/runtimeclass-class.md)