---
title: "コンパイラ エラー C3675 | Microsoft Docs"
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
  - "C3675"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3675"
ms.assetid: 87461613-6633-430b-b95d-c7cb1bb63776
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3675
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'関数' : 'プロパティ' が定義されているため、予約されています  
  
 簡単なプロパティを宣言すると、コンパイラによって get アクセサー メソッドおよび set アクセサー メソッドが生成されます。これらの名前は、プログラムのスコープ内に存在します。コンパイラは、プロパティ名の前に get\_ および set\_ を追加して名前を生成します。したがって、コンパイラにより生成されたアクセサーと同じ名前で関数を宣言することはできません。  
  
 詳細については、「[property](../../windows/property-cpp-component-extensions.md)」を参照してください。  
  
## 使用例  
 次の例では C3675 エラーが生成されます。  
  
```  
// C3675.cpp  
// compile with: /clr /c  
ref struct C {  
public:  
   property int Size;  
   int get_Size() { return 0; }   // C3675  
};  
```