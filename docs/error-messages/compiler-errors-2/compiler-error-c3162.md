---
title: "コンパイラ エラー C3162 | Microsoft Docs"
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
  - "C3162"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3162"
ms.assetid: 0d4c4a24-1456-4191-b7d8-c38cb7b17c32
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3162
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'型' : デストラクターを含む参照型は、スタティック データ メンバー 'メンバー' の型として使用できません  
  
 クラスに静的メンバー関数も含まれている場合、共通言語ランタイムはユーザー定義のデストラクターを実行するタイミングを認識できません。  
  
 デストラクターは、オブジェクトが明示的に削除されるまで実行されません。  
  
 詳細については、次のトピックを参照してください。  
  
-   [\/clr \(共通言語ランタイムのコンパイル\)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [Visual C\+\+ の 64 ビットへの移行に関する一般的な問題](../../build/common-visual-cpp-64-bit-migration-issues.md)  
  
## 使用例  
 次の例では C3162 エラーが生成されます。  
  
```  
// C3162.cpp  
// compile with: /clr /c  
ref struct A {  
   ~A() { System::Console::WriteLine("in destructor"); }  
   static A i;   // C3162  
   static A^ a = gcnew A;   // OK  
};  
  
int main() {  
   A ^ a = gcnew A;  
   delete a;  
}  
```