---
title: "パーティション (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::partition
dev_langs:
- C++
helpviewer_keywords:
- partition function [STL/CLR]
ms.assetid: 3f551eb3-31ec-4b1d-b585-07718d6a1bd7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: dd14a691beda3930ffcb35f6b48ba04ca8ea5d00
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="partition-stlclr"></a>partition (STL/CLR)
範囲内の要素を 2 つの分離されたセットに分類し、単項述語を満たす要素が単項述語を満たさない要素よりも前に来るように配置します。  
  
## <a name="syntax"></a>構文  
  
```  
template<class _BidIt, class _Pr> inline  
    _BidIt partition(_BidIt _First, _BidIt _Last, _Pr _Pred);  
```  
  
## <a name="remarks"></a>コメント  
 この関数の動作は、C++ 標準ライブラリ関数と同じ`partition`です。 詳細については、次を参照してください。[パーティション](../standard-library/algorithm-functions.md#partition)です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<cliext アルゴリズム/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>参照  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)