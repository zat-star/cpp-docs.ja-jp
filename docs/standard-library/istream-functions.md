---
title: '&lt;istream&gt; 関数 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- istream/std::swap
- istream/std::ws
ms.assetid: 0301ea0d-4ded-4841-83dd-4253b55b3188
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 18fa27845c84103ac1a0bd751871fdc97449a7f9
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="ltistreamgt-functions"></a>&lt;istream&gt; 関数

|||
|-|-|
|[swap](#istream_swap)|[ws](#ws)|

## <a name="istream_swap"></a>  swap

2 つのストリーム オブジェクトの要素を交換します。

```cpp
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

`left` ストリームです。

`right` ストリームです。

## <a name="ws"></a>  ws

ストリーム内の空白をスキップします。

```cpp
template class<Elem, Tr> basic_istream<Elem, Tr>& ws(basic_istream<Elem, Tr>& _Istr);
```

### <a name="parameters"></a>パラメーター

`_Istr` ストリームです。

### <a name="return-value"></a>戻り値

ストリーム。

### <a name="remarks"></a>コメント

マニピュレーターを抽出し、すべての要素を破棄`ch`を[use_facet](../standard-library/basic-filebuf-class.md#open)< **ctype** \< **Elem**>> ( [getloc](../standard-library/ios-base-class.md#getloc))。 **is**( **ctype** \< **Elem**>::**領域**、 **ch**) は true です。

この関数は、要素の抽出中にファイルの終わりに達した場合 [setstate](../standard-library/basic-ios-class.md#setstate)( **eofbit**) を呼び出します。 `_Istr` を返します。

### <a name="example"></a>例

`ws` の使用例については [operator>>](../standard-library/istream-operators.md#op_gt_gt) に関する記事をご覧ください。

## <a name="see-also"></a>関連項目

[\<istream>](../standard-library/istream.md)<br/>
