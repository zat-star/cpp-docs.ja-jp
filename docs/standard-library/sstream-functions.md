---
title: "&lt;sstream&gt; 関数 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- sstream/std::swap
ms.assetid: bc9607e8-7c6b-44ef-949b-19e917b450ad
caps.latest.revision: 
manager: ghogen
ms.openlocfilehash: 1c186910203df481bef047f2d1813097590c7508
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="ltsstreamgt-functions"></a>&lt;sstream&gt; 関数
||  
|-|  
|[swap](#sstream_swap)|  
  
##  <a name="sstream_swap"></a>  swap  
 2 つの `sstream` オブジェクト間で値を交換します。  
  
```  
template <class Elem, class Tr, class Alloc>  
void swap(
    basic_stringbuf<Elem, Tr, Alloc>& left,  
    basic_stringbuf<Elem, Tr, Alloc>& right);

template <class Elem, class Tr, class Alloc>  
void swap(
    basic_istringstream<Elem, Tr, Alloc>& left,  
    basic_istringstream<Elem, Tr, Alloc>& right);

template <class Elem, class Tr, class Alloc>  
void swap(
    basic_ostringstream<Elem, Tr, Alloc>& left,  
    basic_ostringstream<Elem, Tr, Alloc>& right);

template <class Elem, class Tr, class Alloc>  
void swap(
    basic_stringstream<Elem, Tr, Alloc>& left,  
    basic_stringstream<Elem, Tr, Alloc>& right);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`left`|`sstream` オブジェクトへの参照。|  
|`right`|`sstream` オブジェクトへの参照。|  
  
### <a name="remarks"></a>コメント  
 このテンプレート関数は、`left.swap(right)` を実行します。  
  
## <a name="see-also"></a>参照  
 [\<sstream>](../standard-library/sstream.md)

