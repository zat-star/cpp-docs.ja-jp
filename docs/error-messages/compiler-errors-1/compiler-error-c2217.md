---
title: "コンパイラ エラー C2217 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2217"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2217"
ms.assetid: 1ce1e3f5-4171-4376-804d-967f7e612935
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラ エラー C2217
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'attribute1' には 'attribute2' が必要です。  
  
 関数に与える属性のうち、メッセージに示した最初の属性は 2 番目の属性と一緒に使う必要があります。  
  
### 次のような原因をチェックして問題を解決するには  
  
1.  割り込み \(`__interrupt`\) 関数が `near` として宣言されています。  割り込み関数は `far` にする必要があります。  
  
2.  割り込み関数が `__stdcall` または `__fastcall` で宣言されています。  割り込み関数では C の呼び出し規約を使う必要があります。  
  
## 使用例  
 また、C2217 エラーは、可変個の引数を受け取る CLR 関数にデリゲートをバインドする場合にも発生することがあります。  この関数にパラメーター配列のオーバーロードがある場合は、代わりにそれを使用します。  次の例では C2217 エラーが生成されます。  
  
```  
// C2217.cpp  
// compile with: /clr  
using namespace System;  
delegate void MyDel(String^, Object^, Object^, ...);   // C2217  
delegate void MyDel2(String ^, array<Object ^> ^);   // OK  
  
int main() {  
   MyDel2^ wl = gcnew MyDel2(Console::WriteLine);  
   array<Object ^ > ^ x = gcnew array<Object ^>(2);  
   x[0] = safe_cast<Object^>(0);  
   x[1] = safe_cast<Object^>(1);  
  
   // wl("{0}, {1}", 0, 1);  
   wl("{0}, {1}", x);  
}  
```