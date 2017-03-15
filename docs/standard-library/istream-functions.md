---
title: "&lt;istream&gt; 関数 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0301ea0d-4ded-4841-83dd-4253b55b3188
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: aa35f177bcb986e141d0e46e48dc007a96f94498
ms.lasthandoff: 02/24/2017

---
# <a name="ltistreamgt-functions"></a>&lt;istream&gt; 関数
|||  
|-|-|  
|[swap](#istream_swap)|[ws](#ws)|  
  
##  <a name="a-nameistreamswapa--swap"></a><a name="istream_swap"></a>  swap  
 2 つのストリーム オブジェクトの要素を交換します。  
  
```  
template <class Elem, class Tr>  
void swap(
    basic_istream<Elem, Tr>& left,  
    basic_istream<Elem, Tr>& right);

template <class Elem, class Tr>  
void swap(
    basic_iostream<Elem, Tr>& left,  
    basic_iostream<Elem, Tr>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 ` left`  
 ストリーム。  
  
 ` right`  
 ストリーム。  
  
##  <a name="a-namewsa--ws"></a><a name="ws"></a>  ws  
 ストリーム内の空白をスキップします。  
  
```  
template class<Elem, Tr> basic_istream<Elem, Tr>& ws(basic_istream<Elem, Tr>& _Istr);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Istr`  
 ストリーム。  
  
### <a name="return-value"></a>戻り値  
 ストリーム。  
  
### <a name="remarks"></a>コメント  
 マニピュレーターを抽出し、すべての要素を破棄`ch`を[use_facet](../standard-library/basic-filebuf-class.md#basic_filebuf__open)< **ctype** \< **Elem**> > ( [getloc](../standard-library/ios-base-class.md#ios_base__getloc))。 **is**( **ctype**\< **Elem**>:: **space**, **ch**) is true.  
  
 この関数は、要素の抽出中にファイルの終わりに達した場合 [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)( **eofbit**) を呼び出します。 `_Istr` を返します。  
  
### <a name="example"></a>例  
  `ws` の使用例については [operator>>](../standard-library/istream-operators.md#operator_gt__gt_) に関する記事をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [\<istream>](../standard-library/istream.md)


