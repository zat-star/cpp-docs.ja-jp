---
title: "adjacent_difference (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::adjacent_difference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "adjacent_difference 関数"
ms.assetid: 2b462e2e-b8f2-4b2e-9b87-5f688d8da9f4
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# adjacent_difference (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

入力範囲内の各要素と過去の連続する相違点を計算し、割り当て先範囲に結果を出力するか、相違点操作が他方の置換一般化されたプロシージャ、指定二項演算の結果を計算します。  
  
## 構文  
  
```  
template<class _InIt, class _OutIt> inline  
    _OutIt adjacent_difference(_InIt _First, _InIt _Last,  
        _OutIt _Dest);  
template<class _InIt, class _OutIt, class _Fn2> inline  
    _OutIt adjacent_difference(_InIt _First, _InIt _Last,  
        _OutIt _Dest, _Fn2 _Func);  
```  
  
## 解説  
 この関数は、STL の数値関数 `adjacent_difference`と同様に動作します。  詳細については、「[adjacent\_difference](../Topic/adjacent_difference.md)」を参照してください。  
  
## 必要条件  
 **ヘッダー:** の \<cliext\/桁数\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [数値](../dotnet/numeric-stl-clr.md)