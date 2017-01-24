---
title: "partial_sum (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::partial_sum"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "partial_sum 関数 [STL/CLR]"
ms.assetid: 845badae-8519-4ac8-9ea7-2b921bac7c51
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# partial_sum (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

入力計算の一連の合計は最初の要素の `i`th 要素を受け取り、移動先の範囲または計算の `i`th 要素のこのような合計合計操作の結果が別の指定二項演算が別の一般的な手順の結果またがります。  
  
## 構文  
  
```  
template<class _InIt, class _OutIt> inline  
    _OutIt partial_sum(_InIt _First, _InIt _Last, _OutIt _Dest);  
template<class _InIt, class _OutIt, class _Fn2> inline  
    _OutIt partial_sum(_InIt _First, _InIt _Last,  
        _OutIt _Dest, _Fn2 _Func);  
```  
  
## 解説  
 この関数は、STL の数値関数 `partial_sum`と同様に動作します。  詳細については、「[partial\_sum](../Topic/partial_sum.md)」を参照してください。  
  
## 必要条件  
 **ヘッダー:** の \<cliext\/桁数\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [数値](../dotnet/numeric-stl-clr.md)