---
title: "inner_product (STL/CLR) | Microsoft Docs"
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
  - "cliext::inner_product"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "inner_product 関数 [STL/CLR]"
ms.assetid: 97d7a507-7494-4216-aedf-0546ed0edb3f
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# inner_product (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

2 種類の span 要素の積の合計を計算し、指定された初期値に追加したり、合計や製品の二項演算が他の指定二項演算が別の一般的な手順の結果を計算します。  
  
## 構文  
  
```  
template<class _InIt1, class _InIt2, class _Ty> inline  
    _Ty inner_product(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2,  
        _Ty _Val);  
template<class _InIt1, class _InIt2, class _Ty, class _Fn21,  
       class _Fn22> inline  
    _Ty inner_product(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2,  
        _Ty _Val, _Fn21 _Func1, _Fn22 _Func2);  
```  
  
## 解説  
 この関数は、STL の数値関数 `inner_product`と同様に動作します。  詳細については、「[inner\_product](../Topic/inner_product.md)」を参照してください。  
  
## 必要条件  
 **ヘッダー:** の \<cliext\/桁数\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [数値](../dotnet/numeric-stl-clr.md)