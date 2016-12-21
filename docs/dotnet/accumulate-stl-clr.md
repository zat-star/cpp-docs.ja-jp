---
title: "accumulate (STL/CLR) | Microsoft Docs"
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
  - "cliext::accumulate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "accumulate 関数 [STL/CLR]"
ms.assetid: b80e1ef1-1858-4c1d-817b-c42ad1f17a2f
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# accumulate (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

初期値を含めて、指定した範囲内のすべての要素の合計を逐次的に対する部分を計算して計算、または指定二項演算の使用から取得した合計以外の連続する部分的な結果の結果を計算します。  
  
## 構文  
  
```  
template<class _InIt, class _Ty> inline  
    _Ty accumulate(_InIt _First, _InIt _Last, _Ty _Val);  
template<class _InIt, class _Ty, class _Fn2> inline  
    _Ty accumulate(_InIt _First, _InIt _Last, _Ty _Val, _Fn2 _Func);  
```  
  
## 解説  
 この関数は、STL の数値関数 `accumulate`と同様に動作します。  詳細については、「[accumulate](../Topic/accumulate.md)」を参照してください。  
  
## 必要条件  
 **ヘッダー:** の \<cliext\/桁数\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [数値](../dotnet/numeric-stl-clr.md)