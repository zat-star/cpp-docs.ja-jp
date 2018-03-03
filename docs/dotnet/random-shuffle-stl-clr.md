---
title: "random_shuffle (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::random_shuffle
dev_langs:
- C++
helpviewer_keywords:
- random_shuffle function [STL/CLR]
ms.assetid: 0f9d93e2-f50f-40e6-bbe4-2ca3231a895e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: ed0a6e63fa11a531f090e367e9ae8cd82242608b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="randomshuffle-stlclr"></a>random_shuffle (STL/CLR)
シーケンスを並べ替えます`N`のいずれかに範囲内の要素`N`! 個の可能な配置の 1 つに再配置します。  
  
## <a name="syntax"></a>構文  
  
```  
template<class _RanIt> inline  
    void random_shuffle(_RanIt _First, _RanIt _Last);  
template<class _RanIt, class _Fn1> inline  
    void random_shuffle(_RanIt _First, _RanIt _Last, _Fn1% _Func);  
```  
  
## <a name="remarks"></a>コメント  
 この関数の動作は、C++ 標準ライブラリ関数と同じ`random_shuffle`です。 詳細については、次を参照してください。 [random_shuffle](../standard-library/algorithm-functions.md#random_shuffle)です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<cliext アルゴリズム/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>参照  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)