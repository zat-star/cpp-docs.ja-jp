---
title: "pop_heap (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::pop_heap
dev_langs: C++
helpviewer_keywords: pop_heap function [STL/CLR]
ms.assetid: d9bde0ed-2122-4d83-b4b3-f47f6fb3729a
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cf4f3e94035af0ce12ddcfabdee21459918a039c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="popheap-stlclr"></a>pop_heap (STL/CLR)
ヒープの先頭と範囲内の最後から 2 番目の位置との間で最大の要素を削除し、残りの要素から新しいヒープを形成します。  
  
## <a name="syntax"></a>構文  
  
```  
template<class _RanIt> inline  
    void pop_heap(_RanIt _First, _RanIt _Last);  
template<class _RanIt, class _Pr> inline  
    void pop_heap(_RanIt _First, _RanIt _Last, _Pr _Pred);  
```  
  
## <a name="remarks"></a>コメント  
 この関数の動作は、C++ 標準ライブラリ関数と同じ`pop_heap`です。 詳細については、次を参照してください。 [pop_heap](../standard-library/algorithm-functions.md#pop_heap)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext アルゴリズム/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)