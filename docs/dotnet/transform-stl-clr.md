---
title: "変換 (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::transform
dev_langs: C++
helpviewer_keywords: transform function [STL/CLR]
ms.assetid: 08940969-6d10-40e4-a35b-68dd801b3949
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f5120b2408649893e0b796bbdb256ff0187741ba
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="transform-stlclr"></a>変換 (STL/CLR)
指定された関数オブジェクトをソース範囲内の各要素、または 2 つのソース範囲内の要素のペアに適用し、関数オブジェクトの戻り値をターゲット範囲にコピーします。  
  
## <a name="syntax"></a>構文  
  
```  
template<class _InIt, class _OutIt, class _Fn1> inline  
    _OutIt transform(_InIt _First, _InIt _Last, _OutIt _Dest,  
        _Fn1 _Func);  
template<class _InIt1, class _InIt2, class _OutIt, class _Fn2> inline  
    _OutIt transform(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2,  
        _OutIt _Dest, _Fn2 _Func);  
```  
  
## <a name="remarks"></a>コメント  
 この関数の動作は、C++ 標準ライブラリ関数と同じ`transform`です。 詳細については、次を参照してください。[変換](../standard-library/algorithm-functions.md#transform)です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<cliext アルゴリズム/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>参照  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)