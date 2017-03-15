---
title: "コンパイラの警告 (レベルs 2 and 4) C4200 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4200"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4200"
ms.assetid: e44d6073-937f-42b7-acc1-65e802b475c6
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラの警告 (レベルs 2 and 4) C4200
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

非標準の拡張機能が使用されています : 構造体または共用体中にサイズが 0 の配列があります。  
  
 構造体または共用体がサイズが 0 の配列が含まれていることを示します。  
  
 サイズが 0 の配列の宣言は、Microsoft 拡張機能です。  これにより、C ファイルをコンパイルした場合はレベル 2 の警告、C\+\+ ファイルをコンパイルした場合はレベル 4 の警告が発生します。  C\+\+ のコンパイルでも、"UDT にサイズが 0 の配列が含まれているときに、copy\-ctor または copy\-assignment オペレーターを生成することはできません。" という警告が発生します。次の例では警告 C4200 が生成されます。  
  
```cpp  
// C4200.cpp  
// compile by using: cl /W4 c4200.cpp  
struct A {  
    int a[0];  // C4200  
};  
int main() {  
}  
```  
  
 この非標準の拡張機能は、可変長の外部データ構造とのインターフェイス コードによく使用されます。  コードがこのシナリオに該当する場合は、次のように警告を無効にできます。  
  
## 使用例  
  
```cpp  
// C4200b.cpp  
// compile by using: cl /W4 c4200a.cpp  
#pragma warning(disable : 4200)  
struct A {  
    int a[0];  
};  
int main() {  
}  
```