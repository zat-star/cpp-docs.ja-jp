---
title: codecvt_utf8_utf16 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: codecvt/std::cvt_utf8_utf16
dev_langs: C++
helpviewer_keywords: codecvt_utf8_utf16 class
ms.assetid: 4c12c881-5dba-4e39-b338-0b9caff5af29
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d16a5e316119470f96c115c4ba8cbe47fabd3831
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="codecvtutf8utf16"></a>codecvt_utf8_utf16
UTF-16 としてエンコードされたワイド文字と、UTF-8 としてエンコードされたバイト ストリームを変換する[ロケール](../standard-library/locale-class.md) ファセットを表します。

```
template<class Elem, unsigned long Maxcode = 0x10ffff, codecvt_mode Mode = (codecvt_mode)0>
class codecvt_utf8_utf16 : public _STD codecvt<Elem, char, StateType>
```

## <a name="parameters"></a>パラメーター

`Elem`  
ワイド文字要素型。  
`Maxcode`  
ロケール ファセットの文字の最大数。  
`Mode`  
ロケール ファセットの構成情報。  

## <a name="remarks"></a>コメント

このバイト ストリームはバイナリ ファイルまたはテキスト ファイルに書き込むことができます。  

## <a name="requirements"></a>必要条件

ヘッダー: <codecvt> 名前空間: std
