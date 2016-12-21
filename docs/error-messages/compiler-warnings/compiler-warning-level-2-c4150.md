---
title: "コンパイラの警告 (レベル 2) C4150 | Microsoft Docs"
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
  - "C4150"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4150"
ms.assetid: ff1760ec-0d9f-4d45-b797-94261624becf
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 2) C4150
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' 型を削除するため delete 演算子が呼び出されましたが、定義がありません。  
  
 宣言された型を削除するために **delete** 演算子が呼び出されましたが、定義がないためデストラクターが見つかりません。  
  
 次の例では警告 C4150 が生成されます。  
  
```  
// C4150.cpp  
// compile with: /W2  
class  IncClass;  
  
void NoDestruct( IncClass* pIncClass )  
{  
   delete pIncClass;  
} // C4150, define class to resolve  
  
int main()  
{  
}  
```