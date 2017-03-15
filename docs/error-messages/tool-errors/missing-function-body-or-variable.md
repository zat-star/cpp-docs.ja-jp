---
title: "関数本体または変数の未定義 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "関数本体"
  - "変数, 未定義"
ms.assetid: 1a88d809-b14f-46a4-97c4-3e48beb418f2
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 関数本体または変数の未定義
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

関数のプロトタイプしか与えていない場合でも、エラーなしでコンパイルを継続できます。ただし、実際の関数コードや変数領域が予約されていないので、リンカーは呼び出しのアドレスを解決できません。  リンカーが関数呼び出しを解決し、生成するまで、このエラーは発生しません。  
  
## 使用例  
 Main からの関数を呼び出すと、プロトタイプにより関数が存在していると見なされるため、LNK2019 エラーが発生します。ただしリンカーは、関数が存在していないことを検出します。  
  
```  
// LNK2019_MFBV.cpp  
// LNK2019 expected  
void DoSomething(void);  
int main() {  
   DoSomething();  
}  
```  
  
## 使用例  
 C\+\+ では、クラス定義で、プロトタイプだけではなく関数の実装が含まれていることを確認してください。  クラスをヘッダー ファイルの外部で定義するときには、`Classname``::``memberfunction` の形式で関数の前にクラス名を忘れずに付けてください。  
  
```  
// LNK2019_MFBV_2.cpp  
// LNK2019 expected  
struct A {  
   static void Test();  
};  
  
// Should be void A::Test() {}  
void Test() {}  
  
int main() {  
   A AObject;  
   AObject.Test();  
}  
```  
  
## 参照  
 [リンカ ツール エラー LNK2019](../Topic/Linker%20Tools%20Error%20LNK2019.md)