---
title: "コンパイラ エラー C2825 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2825"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2825"
ms.assetid: c832f1c1-5184-4fc2-9356-12b21daa7af3
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラ エラー C2825
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var': '::' が後に続くときは、クラスまたは名前空間でなければなりません  
  
 限定名の作成に失敗しました。  
  
 コードに :: で始まる関数名の関数宣言が含まれていないかどうかなどを確認してください。  
  
## 使用例  
 次の例では警告 C2825 が生成されます。  
  
```  
// C2825.cpp  
typedef int i;  
int main() {  
   int* p = new int;  
   p->i::i();   // C2825  
   // try the following line instead  
   // p->i::~i();  
}  
```