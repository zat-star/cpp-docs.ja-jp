---
title: "inner_product (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::inner_product
dev_langs: C++
helpviewer_keywords: inner_product function [STL/CLR]
ms.assetid: 97d7a507-7494-4216-aedf-0546ed0edb3f
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 5d61de34fcb029000ac27efcf74bd1321d1b7e32
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="innerproduct-stlclr"></a>inner_product (STL/CLR)
2 つの範囲の要素ごとの積の合計を計算し、それを指定された初期値に加算するか、または和や積の二項演算が指定された別の二項演算に置き換えられた汎用化されたプロシージャの結果を計算します。  
  
## <a name="syntax"></a>構文  
  
```  
template<class _InIt1, class _InIt2, class _Ty> inline  
    _Ty inner_product(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2,  
        _Ty _Val);  
template<class _InIt1, class _InIt2, class _Ty, class _Fn21,  
       class _Fn22> inline  
    _Ty inner_product(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2,  
        _Ty _Val, _Fn21 _Func1, _Fn22 _Func2);  
```  
  
## <a name="remarks"></a>コメント  
 この関数の動作は、C++ 標準ライブラリの数値関数と同じ`inner_product`です。 詳細については、次を参照してください。 [inner_product](../standard-library/numeric-functions.md#inner_product)です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<cliext/numeric >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>参照  
 [numeric (STL/CLR)](../dotnet/numeric-stl-clr.md)