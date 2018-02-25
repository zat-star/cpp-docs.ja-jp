---
title: '&lt;ostream&gt; typedef | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- iosfwd/std::ostream
- iosfwd/std::wostream
ms.assetid: 2ec4dc52-a01f-4654-bd65-dd5288777c48
caps.latest.revision: 
manager: ghogen
ms.openlocfilehash: c9ab11cf6436888605a07c91051bf27c45e10fcf
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="ltostreamgt-typedefs"></a>&lt;ostream&gt; typedef
|||  
|-|-|  
|[ostream](#ostream)|[wostream](#wostream)|  
  
##  <a name="ostream"></a>  ostream  
 `char` に対して特殊化された basic_ostream と `char` に対して特殊化された `char_traits` に基づいて型を作成します。  
  
```
typedef basic_ostream<char, char_traits<char>> ostream;
```  
  
### <a name="remarks"></a>コメント  
 この型はテンプレート クラス [basic_ostream](../standard-library/basic-ostream-class.md) の同意語であり、既定の特性を持つ型 `char` の要素に対して特殊化されています。  
  
##  <a name="wostream"></a>  wostream  
 `wchar_t` に対して特殊化された basic_ostream と `wchar_t` に対して特殊化された `char_traits` に基づいて型を作成します。  
  
```
typedef basic_ostream<wchar_t, char_traits<wchar_t>> wostream;
```  
  
### <a name="remarks"></a>コメント  
 この型はテンプレート クラス [basic_ostream](../standard-library/basic-ostream-class.md) の同意語であり、既定の特性を持つ型 `wchar_t` の要素に対して特殊化されています。  
  
## <a name="see-also"></a>参照  
 [\<ostream>](../standard-library/ostream.md)



