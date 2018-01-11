---
title: "partial_sort_copy (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::partial_sort_copy
dev_langs: C++
helpviewer_keywords: partial_sort_copy function [STL/CLR]
ms.assetid: ed4af83e-7554-4f6d-bf54-c56fa6210fe8
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 351209d8f3bd68d614a45a9d4aa8f1b0dc767663
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="partialsortcopy-stlclr"></a>partial_sort_copy (STL/CLR)
ソース範囲からターゲット範囲に要素をコピーします。ソース要素は小なりまたは指定された別の二項述語によって並べ替えられます。  
  
## <a name="syntax"></a>構文  
  
```  
template<class _InIt, class _RanIt> inline  
    _RanIt partial_sort_copy(_InIt _First1, _InIt _Last1,  
        _RanIt _First2, _RanIt _Last2);  
template<class _InIt, class _RanIt, class _Pr> inline  
    _RanIt partial_sort_copy(_InIt _First1, _InIt _Last1,  
        _RanIt _First2, _RanIt _Last2, _Pr _Pred);  
```  
  
## <a name="remarks"></a>コメント  
 この関数の動作は、C++ 標準ライブラリ関数と同じ`partial_sort_copy`です。 詳細については、次を参照してください。 [partial_sort_copy](../standard-library/algorithm-functions.md#partial_sort_copy)です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<cliext アルゴリズム/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>参照  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)