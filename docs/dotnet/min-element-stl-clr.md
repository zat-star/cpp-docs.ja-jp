---
title: "min_element (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::min_element
dev_langs: C++
helpviewer_keywords: min_element function [STL/CLR]
ms.assetid: 2a9c6828-9722-454f-9c10-d4a184d4d21b
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7996e368abff6d82c346ff58eb19d2d53ff208d1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="minelement-stlclr"></a>min_element (STL/CLR)
指定された範囲内の最小の要素の最初の出現箇所を検索します。順序の基準は二項述語によって指定できます。  
  
## <a name="syntax"></a>構文  
  
```  
template<class _FwdIt> inline  
    _FwdIt min_element(_FwdIt _First, _FwdIt _Last);  
template<class _FwdIt, class _Pr> inline  
    _FwdIt min_element(_FwdIt _First, _FwdIt _Last, _Pr _Pred);  
```  
  
## <a name="remarks"></a>コメント  
 この関数の動作は、C++ 標準ライブラリ関数と同じ`min_element`です。 詳細については、次を参照してください。 [min_element](../standard-library/algorithm-functions.md#min_element)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext アルゴリズム/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)