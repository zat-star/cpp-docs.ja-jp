---
title: "stable_partition (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::stable_partition
dev_langs: C++
helpviewer_keywords: stable_partition function [STL/CLR]
ms.assetid: b82c194c-ae38-4afb-b255-a95a4c2b3101
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cba7b0a8726bd4373320d0e60fd9d31d7e5899ee
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="stablepartition-stlclr"></a>stable_partition (STL/CLR)
範囲内の要素を 2 つの分離されたセットに分類し、等価要素の相対順序は維持して、単項述語を満たす要素が単項述語を満たさない要素よりも前に来るように配置します。  
  
## <a name="syntax"></a>構文  
  
```  
template<class _BidIt, class _Pr> inline  
    _BidIt stable_partition(_BidIt _First, _BidIt _Last, _Pr _Pred);  
```  
  
## <a name="remarks"></a>コメント  
 この関数の動作は、C++ 標準ライブラリ関数と同じ`stable_partition`です。 詳細については、次を参照してください。 [stable_partition](../standard-library/algorithm-functions.md#stable_partition)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext アルゴリズム/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)