---
title: "partial_sum (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::partial_sum
dev_langs:
- C++
helpviewer_keywords:
- partial_sum function [STL/CLR]
ms.assetid: 845badae-8519-4ac8-9ea7-2b921bac7c51
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7200fbf4adb7866125cfd8956b7b35ad5d5a2657
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="partialsum-stlclr"></a>partial_sum (STL/CLR)
一連の最初の要素から入力範囲内の合計を計算、`i`番目の要素でこのような各合計の結果を格納および`i`番目の要素をターゲット範囲の汎用化されたプロシージャの結果を計算または場所合計演算指定した別の二項演算に置き換えられます。  
  
## <a name="syntax"></a>構文  
  
```  
template<class _InIt, class _OutIt> inline  
    _OutIt partial_sum(_InIt _First, _InIt _Last, _OutIt _Dest);  
template<class _InIt, class _OutIt, class _Fn2> inline  
    _OutIt partial_sum(_InIt _First, _InIt _Last,  
        _OutIt _Dest, _Fn2 _Func);  
```  
  
## <a name="remarks"></a>コメント  
 この関数の動作は、C++ 標準ライブラリの数値関数と同じ`partial_sum`です。 詳細については、次を参照してください。 [partial_sum](../standard-library/numeric-functions.md#partial_sum)です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<cliext/numeric >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>参照  
 [numeric (STL/CLR)](../dotnet/numeric-stl-clr.md)