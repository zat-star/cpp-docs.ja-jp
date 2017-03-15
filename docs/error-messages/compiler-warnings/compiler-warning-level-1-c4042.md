---
title: "コンパイラの警告 (レベル 1) C4042 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4042"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4042"
ms.assetid: e4bd861b-1194-426b-bf79-68c5b021eb0a
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コンパイラの警告 (レベル 1) C4042
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 指定されたストレージ クラスは、このコンテキストでは使えません。  
  
 指定されたストレージ クラスは、このコンテキストのこの識別子と共に使用できません。  以下の規則に従って、既定のストレージ クラスが使用されます。  
  
-   *identifier* が関数の場合は、`extern` が使用されます。  
  
-   *identifier* が仮パラメーターまたはローカル変数の場合は、**auto** が使用されます。  
  
-   *identifier* がグローバル変数の場合、ストレージ クラスは使用されません。  
  
 この警告は、パラメーター宣言で **register** 以外のストレージ クラスを指定したことが原因で発生する場合があります。  
  
 次の例では C4042 警告が生成されます。  
  
```  
// C4042.cpp  
// compile with: /W1 /LD  
int func2( __declspec( thread ) int tls_i )    // C4042  
// try the following line instead  
// int func2( int tls_i )  
{  
   return tls_i;  
}  
```