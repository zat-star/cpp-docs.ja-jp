---
title: "コンパイラ エラー C3622 | Microsoft Docs"
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
  - "C3622"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3622"
ms.assetid: 02836f78-0cf2-4947-b87e-710187d81014
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3622
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'クラス' : 'キーワード' として宣言されたクラスをインスタンス生成することはできません  
  
 [abstract](../../windows/abstract-cpp-component-extensions.md) \(または[\_\_abstract](../../misc/abstract.md)\) でマークされたクラスのインスタンス化を試みました。  abstract としてマークされたクラスは基本クラスにできますが、インスタンス化はできません。  
  
## 使用例  
 次の例では C3622 エラーが生成されます。  
  
```  
// C3622.cpp  
// compile with: /clr  
ref class a abstract {};  
  
int main() {  
   a aa;   // C3622  
}  
```  
  
## 使用例  
 次の例では C3622 エラーが生成されます。  
  
```  
// C3622_b.cpp  
// compile with: /clr:oldSyntax  
__abstract class a {  
};  
int main() {  
   a aa;   // C3622  
}  
```