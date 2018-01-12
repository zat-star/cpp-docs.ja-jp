---
title: "remove_if (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::remove_if
dev_langs: C++
helpviewer_keywords: remove_if function [STL/CLR]
ms.assetid: de501d3f-965b-4a99-b833-f6fa303fbcdc
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a8e9b30e7f3627758ed905f95f1b700cfa5034e7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="removeif-stlclr"></a>remove_if (STL/CLR)
特定の範囲から述語を満たす要素を除去します。残りの要素の順序に影響を及ぼすことはなく、指定された値を含まない新しい範囲の末尾を返します。  
  
## <a name="syntax"></a>構文  
  
```  
template<class _FwdIt, class _Pr> inline  
    _FwdIt remove_if(_FwdIt _First, _FwdIt _Last, _Pr _Pred);  
```  
  
## <a name="remarks"></a>コメント  
 この関数の動作は、C++ 標準ライブラリ関数と同じ`remove_if`です。 詳細については、次を参照してください。 [remove_if](../standard-library/algorithm-functions.md#remove_if)です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<cliext アルゴリズム/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>参照  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)