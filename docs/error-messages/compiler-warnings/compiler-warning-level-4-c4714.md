---
title: "コンパイラの警告 (レベル 4) C4714 | Microsoft Docs"
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
  - "C4714"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4714"
ms.assetid: 22c7fd0c-899d-4e9b-95f3-725b2c49fb46
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 4) C4714
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

関数 'function' がインライン関数ではなく、\_\_forceinline として記述されています。  
  
 指定された関数がインライン展開の対象として選択されましたが、実際にはインライン展開されませんでした。  
  
 `__forceinline` は `__inline` より強力な指示ですが、インライン展開はコンパイラの判断によって行われます。この場合、関数のインライン展開を行うかどうかの判定には、コンパイラ独自の判断基準は使用されません。  
  
 機構上の理由に基づく判断により、特定の関数がインライン展開されないこともあります。  以下の関数はインライン展開されません。  
  
-   インライン展開すると SEH と C\+\+ EH が混在する関数  
  
-   \-GX\/EHs\/EHa がオンのとき、コピー構築されたオブジェクトが値で渡される関数  
  
-   \-GX\/EHs\/EHa がオンのとき、アンワインド可能オブジェクトを値で返す関数  
  
-   \-Og\/Ox\/O1\/O2 を指定せずにコンパイルした場合、インライン アセンブリを使用する関数  
  
-   可変の数のリストを取る関数  
  
-   **try** \(C\+\+ 例外処理\) ステートメントを持つ関数  
  
 次の例では警告 C4714 が生成されます。  
  
```  
// C4714.cpp  
// compile with: /Ob1 /GX /W4  
__forceinline void func1()  
{  
   try  
   {  
   }  
   catch (...)  
   {  
   }  
}  
  
void func2()  
{  
   func1();   // C4714  
}  
  
int main()  
{  
}  
```