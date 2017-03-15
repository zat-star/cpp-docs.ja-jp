---
title: "コンパイラの警告 (レベル 1) C4490 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4490"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4490"
ms.assetid: f9b03ecf-41a1-4f4d-a74c-2c1e88234ccc
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# コンパイラの警告 (レベル 1) C4490
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'override' : オーバーライド指定子の使用法が不適切です。'関数' は基本 ref クラス メソッドと一致しません  
  
 オーバーライド指定子が正しく使用されていません。  たとえば、インターフェイス関数をオーバーライドしないで実装しています。  
  
 詳細については、「[オーバーライド指定子](../../windows/override-specifiers-cpp-component-extensions.md)」を参照してください。  
  
## 使用例  
 次の例では C4490 エラーが生成されます。  
  
```  
// C4490.cpp  
// compile with: /clr /c /W1  
  
interface struct IFace {  
   void Test();  
};  
  
ref struct Class1 : public IFace {  
   virtual void Test() override {}   // C4490  
   // try the following line instead  
   // virtual void Test() {}  
};  
```