---
title: "コンパイラの警告 (レベル 1) C4742 | Microsoft Docs"
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
  - "C4742"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4742"
ms.assetid: e520881d-1eeb-48b1-9df0-8017ee8ba076
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1) C4742
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' は 'file1' および 'file2' 内で異なるアライメントを含んでいます: '数値' および '数値'  
  
 2 つのファイルで参照または定義された外部変数は、それぞれのファイルでのアライメントが異なっています。  この警告は *file1* の変数の `__alignof` は *file2*の変数の `__alignof` が異なることをコンパイラがわかったときに表示されます。  これは、異なるファイルで変数を宣言するときに互換性のない型を使用したか、異なるファイルで一致しない `#pragma pack` を使用したことが原因で発生する場合があります。  
  
 この警告を解決するには、同じ型定義を使用するか、変数ごとに異なる名前を使用します。  
  
 詳細については、「[pack](../../preprocessor/pack.md)」および「[\_\_alignof 演算子](../../cpp/alignof-operator.md)」を参照してください。  
  
## 使用例  
 これは、型を定義する 1 つ目のファイルです。  
  
```  
// C4742a.c  
// compile with: /c  
struct X {  
   char x, y, z, w;  
} global;  
```  
  
## 使用例  
 次の例では C4742 エラーが生成されます。  
  
```  
// C4742b.c  
// compile with: C4742a.c /W1 /GL  
// C4742 expected  
extern struct X {  
   int a;  
} global;  
  
int main() {  
   global.a = 0;  
}  
```