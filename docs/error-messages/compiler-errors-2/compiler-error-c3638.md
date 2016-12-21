---
title: "コンパイラ エラー C3638 | Microsoft Docs"
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
  - "C3638"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3638"
ms.assetid: 8d8bc5ca-75aa-480e-b6b6-3178fab51b1d
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3638
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'演算子' : 標準ボックス化およびアンボックス化の変換演算子は再定義できません  
  
 コンパイラは、暗黙のボックス化をサポートするために、各マネージ クラスの変換演算子を定義します。  この演算子は再定義できません。  
  
 詳細については、「[暗黙のボックス化](../../windows/boxing-cpp-component-extensions.md)」を参照してください。  
  
 次の例では警告 C3638 が生成されます。  
  
```  
// C3638.cpp  
// compile with: /clr  
value struct V {  
   V(){}  
   static operator V^(V);   // C3638  
};  
  
int main() {  
   V myV;  
   V ^ pmyV = myV;   // operator supports implicit boxing  
}  
```