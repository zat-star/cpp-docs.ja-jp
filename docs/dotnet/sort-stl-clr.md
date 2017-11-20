---
title: "並べ替え (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::sort
dev_langs: C++
helpviewer_keywords: sort function [STL/CLR]
ms.assetid: e30f3e97-60c4-4a8e-89f1-75ec056f587a
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: eed713de1f73fcf96c7327f583079f24a2379b8d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="sort-stlclr"></a>sort (STL/CLR)
指定された範囲の要素を、降順以外の順序、または二項述語で指定された順序の基準に従って配置します。  
  
## <a name="syntax"></a>構文  
  
```  
template<class _RanIt> inline  
    void sort(_RanIt _First, _RanIt _Last);  
template<class _RanIt, class _Pr> inline  
    void sort(_RanIt _First, _RanIt _Last, _Pr _Pred);  
```  
  
## <a name="remarks"></a>コメント  
 この関数の動作は、C++ 標準ライブラリ関数と同じ`sort`です。 詳細については、次を参照してください。[並べ替え](../mfc/reference/cmfclistctrl-class.md#sort)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext アルゴリズム/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)