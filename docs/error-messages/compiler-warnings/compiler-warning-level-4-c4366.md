---
title: "コンパイラの警告 (レベル 4) C4366 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4366"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4366"
ms.assetid: 65d2942f-3741-42f4-adf2-4920d5a055ca
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# コンパイラの警告 (レベル 4) C4366
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'演算子' 単項演算子の結果は適切でない可能性があります  
  
 パッキングにより構造体メンバーが適切に配置されない場合は、そのメンバーのアドレスが配置ポインターに代入されるときに警告が出されます。  既定では、すべてのポインターが整列されています。  
  
 C4366 を解決するには、構造体の配置を変更するか、[\_\_unaligned](../../cpp/unaligned.md) キーワードを指定してポインターを宣言します。  
  
 詳細については、\_\_unaligned および「[pack](../../preprocessor/pack.md)」を参照してください。  
  
## 使用例  
 次の例では C4366 エラーが生成されます。  
  
```  
// C4366.cpp  
// compile with: /W4 /c  
// processor: IPF x64  
#pragma pack(1)  
struct X {  
   short s1;  
   int s2;  
};  
  
int main() {  
   X x;  
   short * ps1 = &x.s1;   // OK  
   int * ps2 = &x.s2;   // C4366  
}  
```