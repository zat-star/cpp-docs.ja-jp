---
title: "コンパイラ エラー C2951 | Microsoft Docs"
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
  - "C2951"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2951"
ms.assetid: c6f95aa2-c894-425b-a51c-d40d70c8daa1
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2951
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'型' 宣言は、グローバル、名前空間、またはクラス スコープのみで許可されています  
  
 ジェネリック クラスまたはテンプレート クラスの宣言をグローバル スコープまたは名前空間スコープ以外で行うことはできません。  インクルード ファイル内でジェネリックの宣言またはテンプレートの宣言を行う場合は、そのインクルード ファイルを必ずグローバル スコープ内でインクルードしてください。  
  
 次の例では警告 C2951 が生成されます。  
  
```  
// C2951.cpp  
template <class T>  
class A {};  
  
int main() {  
   template <class T>   // C2951  
   class B {};  
}  
```  
  
 C2951 は、ジェネリックを使用しているときも発生します。  
  
```  
// C2951b.cpp  
// compile with: /clr /c  
  
// OK  
generic <class T>   
ref class GC { };  
  
int main() {  
   generic <class T> ref class GC2 {};   // C2951  
}  
```