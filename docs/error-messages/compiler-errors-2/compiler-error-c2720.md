---
title: "コンパイラ エラー C2720 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2720"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2720"
ms.assetid: 9ee3aab7-711b-4f5a-b2f1-cb62b130f1ce
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラ エラー C2720
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier': 'specifier' ストレージ クラスの指定子がメンバーに対して誤って指定されています。  
  
 ストレージ クラスは、宣言の外側のクラス メンバーに対して使用することはできません。  このエラーを修正するには、クラス宣言の外側にあるメンバーの定義から、不要な[ストレージ クラス指定子](http://msdn.microsoft.com/ja-jp/10b3d22d-cb40-450b-994b-08cf9a211b6c)を削除します。  
  
 次の例では、C2720 を生成し、その修正方法を示しています。  
  
```  
// C2720.cpp  
struct S {  
   static int i;  
};  
static S::i;   // C2720 - remove the unneeded 'static' to fix it  
  
```