---
title: "コンパイラ エラー C3161 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3161"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3161"
ms.assetid: 1fe2be85-a343-487b-8476-bf9e257eb29d
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3161
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'interface' : クラス、構造体、共用体、またはインターフェイスをインターフェイスで入れ子にできません。インターフェイスをクラス、構造体、共用体に入れ子にできません。  
  
 [\_\_interface](../Topic/__interface.md) を使用できるのは、グローバル スコープまたは名前空間内だけです。  クラス、構造体、または共用体は、インターフェイスでは使用できません。  
  
## 使用例  
 次の例では C3161 エラーが生成されます。  
  
```  
// C3161.cpp  
// compile with: /c  
__interface X {  
   __interface Y {};   // C3161 A nested interface  
};  
```