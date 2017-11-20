---
title: "remove_copy_if (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::remove_copy_if
dev_langs: C++
helpviewer_keywords: remove_copy_if function [STL/CLR]
ms.assetid: 5307f5fe-b6bb-4968-8da1-fea84ab96655
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 199ee8f04fbc62d9251ebe77ae63715328fcfe20
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="removecopyif-stlclr"></a>remove_copy_if (STL/CLR)
ソース範囲からターゲット範囲に要素をコピーしますが、述語を満たす要素はコピーされません。残りの要素の順序に影響を及ぼすことはなく、新しいターゲット範囲の末尾を返します。  
  
## <a name="syntax"></a>構文  
  
```  
template<class _InIt, class _OutIt, class _Pr> inline  
    _OutIt remove_copy_if(_InIt _First, _InIt _Last, _OutIt _Dest,  
        _Pr _Pred);  
```  
  
## <a name="remarks"></a>コメント  
 この関数の動作は、C++ 標準ライブラリ関数と同じ`remove_copy_if`です。 詳細については、次を参照してください。 [remove_copy_if](../standard-library/algorithm-functions.md#remove_copy_if)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext アルゴリズム/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)