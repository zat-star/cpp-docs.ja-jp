---
title: "コンパイラ エラー C2581 | Microsoft Docs"
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
  - "C2581"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2581"
ms.assetid: 24a4e4c1-24d3-4e42-b760-7dcaf9740b16
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2581
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'型' : 代入演算子 'operator \=' が 'static' で宣言されています。  
  
 代入演算子 \(`=`\) が誤って `static` で宣言されています。  代入演算子は `static` で宣言できません。  詳細については、「[ユーザー定義の演算子](../../dotnet/user-defined-operators-cpp-cli.md)」を参照してください。  
  
## 使用例  
 次の例では C2581 エラーが生成されます。  
  
```  
// C2581.cpp  
// compile with: /clr /c  
ref struct Y {  
   static Y ^ operator = (Y^ me, int i);   // C2581  
   Y^ operator =(int i);   // OK  
};  
```