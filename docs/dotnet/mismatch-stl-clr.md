---
title: "一致しません (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::mismatch
dev_langs:
- C++
helpviewer_keywords:
- mismatch function [STL/CLR]
ms.assetid: 77876875-44bb-4476-afd9-390da4eaac16
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 8e08b5280b378c55ef0b3144522f6af6cafbc7c1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="mismatch-stlclr"></a>mismatch (STL/CLR)
二項述語によって指定された等値または等価について、2 つの範囲を要素ごとに比較し、相違点が発生する最初の位置を検索します。  
  
## <a name="syntax"></a>構文  
  
```  
template<class _InIt1, class _InIt2> inline  
    _PAIR_TYPE(_InIt1)  
        mismatch(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2);  
template<class _InIt1, class _InIt2, class _Pr> inline  
    _PAIR_TYPE(_InIt1)  
        mismatch(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2,  
            _Pr _Pred);  
```  
  
## <a name="remarks"></a>コメント  
 この関数の動作は、C++ 標準ライブラリ関数と同じ`mismatch`です。 詳細については、次を参照してください。[不一致](../standard-library/algorithm-functions.md#mismatch)です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<cliext アルゴリズム/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>参照  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)