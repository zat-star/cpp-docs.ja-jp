---
title: '&lt;streambuf&gt; typedef | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- iosfwd/std::streambuf
- iosfwd/std::wstreambuf
ms.assetid: 2678e18f-f0f0-4995-bc53-f1bc7dfc4ec6
caps.latest.revision: 11
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 932b5ce7a664f75eb92f19fdbf32363b9300fb09
ms.contentlocale: ja-jp
ms.lasthandoff: 10/03/2017

---
# <a name="ltstreambufgt-typedefs"></a>&lt;streambuf&gt; typedef
|||  
|-|-|  
|[streambuf](#streambuf)|[wstreambuf](#wstreambuf)|  
  
##  <a name="streambuf"></a>  streambuf  
 `char` を使用する `basic_streambuf` をテンプレート パラメーターとして特化したクラス。  
  
```
typedef basic_streambuf<char, char_traits<char>> streambuf;
```  
  
### <a name="remarks"></a>コメント  
 この型はテンプレート クラス [basic_streambuf](../standard-library/basic-streambuf-class.md) の同意語で、既定の文字の特性を持つ型 `char` の要素に対して特殊化されています。  
  
##  <a name="wstreambuf"></a>  wstreambuf  
 `wchar_t` を使用する `basic_streambuf` をテンプレート パラメーターとして特化したクラス。  
  
```
typedef basic_streambuf<wchar_t, char_traits<wchar_t>> wstreambuf;
```  
  
### <a name="remarks"></a>コメント  
 この型はテンプレート クラス [basic_streambuf](../standard-library/basic-streambuf-class.md) の同意語で、既定の文字の特性を持つ型 `wchar_t` の要素に対して特殊化されています。  
  
## <a name="see-also"></a>関連項目  
 [\<streambuf>](../standard-library/streambuf.md)




