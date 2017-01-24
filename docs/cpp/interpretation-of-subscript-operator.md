---
title: "添字演算子の解釈 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "配列 [C++], 添字"
  - "添字演算子の解釈"
  - "演算子 [C++], 添字の解釈"
  - "添字演算子, 解釈"
ms.assetid: 8852ca18-9d5b-43f7-b8bd-abc89364fbf2
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 添字演算子の解釈
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

他の演算子のように、添字演算子 \(**\[ \]**\) は、ユーザーによって再定義できます。  添字演算子の既定の動作では、オーバーロードしない場合、次のメソッドを使用して配列名と添字を組み合わせます。  
  
 \*\(\(*array\-name*\) \+ \(*subscript*\)\)  
  
 ポインター型を含むすべての加算と同様に、スケーリングは型のサイズを調整するように自動的に実行されます。  したがって、結果の値は *array\-name* の原点からの *subscript* バイトではなく、配列の *subscript* 番目の要素です  \(この変換の詳細については、「[加法演算子](../cpp/additive-operators-plus-and.md)」を参照\)。  
  
 同様に、多次元配列の場合は、次のメソッドを使用してアドレスが派生されます。  
  
 **\(\(**   
 ***array\-name* \) \+ \(**   
 ***subscript* 1**  *max*2 *\* max*3*...max*n\)               **\+** *subscript*2 *\* max*3*...max*n\)                    . . .  *\+* *subscript*n\)\)  
  
## 参照  
 [配列](../Topic/Arrays%20\(C++\).md)