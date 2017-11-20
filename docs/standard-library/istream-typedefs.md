---
title: '&lt;istream&gt; typedef | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- istream/std::iostream
- istream/std::istream
- istream/std::wiostream
- istream/std::wistream
ms.assetid: 55bc1f84-53a7-46ca-a36f-ac6ef75d0374
caps.latest.revision: "10"
manager: ghogen
ms.openlocfilehash: cc53eb1fed0dfc562ddb59ad239d716dd6057ebd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="ltistreamgt-typedefs"></a>&lt;istream&gt; typedef
||||  
|-|-|-|  
|[iostream](#iostream)|[istream](#istream)|[wiostream](#wiostream)|  
|[wistream](#wistream)|  
  
##  <a name="iostream"></a>  iostream  
 `char` に特殊化された型 `basic_iostream`。  
  
```  
typedef basic_iostream<char, char_traits<char>> iostream;  
```  
  
### <a name="remarks"></a>コメント  
 この型はテンプレート クラス [basic_ifstream](../standard-library/basic-iostream-class.md) の同意語であり、既定の特性を持つ型 `char` の要素に対して特殊化されています。  
  
##  <a name="istream"></a>  istream  
 `char` に特殊化された型 `basic_istream`。  
  
```  
typedef basic_istream<char, char_traits<char>> istream;  
```  
  
### <a name="remarks"></a>コメント  
 この型はテンプレート クラス [basic_istream](../standard-library/basic-istream-class.md) の同意語であり、既定の特性を持つ型 `char` の要素に対して特殊化されています。  
  
##  <a name="wiostream"></a>  wiostream  
 `wchar_t` に特殊化された型 `basic_iostream`。  
  
```  
typedef basic_iostream<wchar_t, char_traits<wchar_t>> wiostream;  
```  
  
### <a name="remarks"></a>コメント  
 この型はテンプレート クラス [basic_iostream](../standard-library/basic-iostream-class.md) の同意語であり、既定の特性を持つ型 `wchar_t` の要素に対して特殊化されています。  
  
##  <a name="wistream"></a>  wistream  
 `wchar_t` に特殊化された型 `basic_istream`。  
  
```  
typedef basic_istream<wchar_t, char_traits<wchar_t>> wistream;  
```  
  
### <a name="remarks"></a>コメント  
 この型はテンプレート クラス [basic_istream](../standard-library/basic-istream-class.md) の同意語であり、既定の特性を持つ型 `wchar_t` の要素に対して特殊化されています。  
  
## <a name="see-also"></a>関連項目  
 [\<istream>](../standard-library/istream.md)

