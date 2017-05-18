---
title: codecvt_utf16 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- codecvt/std::codecvt_utf16
- codecvt_utf16
dev_langs:
- C++
helpviewer_keywords:
- codecvt_utf16 class
ms.assetid: a9897f98-f84d-4db6-90ad-858b2727570c
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: 8ee859512a6b4a3050eec6f91d4b3c8449cf918a
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="codecvtutf16"></a>codecvt_utf16
UCS-2 または UCS-4 としてエンコードされたワイド文字と、UTF-16LE または UTF-16BE としてエンコードされたバイト ストリームを変換する[ロケール](../standard-library/locale-class.md) ファセットを表します。

```
template<class Elem, unsigned long Maxcode = 0x10ffff, codecvt_mode Mode = (codecvt_mode)0>
class codecvt_utf16 : public std::codecvt<Elem, char, StateType>
```
## <a name="parameters"></a>パラメーター
`Elem`  
ワイド文字要素型。  
`Maxcode`  
ロケール ファセットの文字の最大数。  
`Mode`  
ロケール ファセットの構成情報。  

## <a name="remarks"></a>コメント
このテンプレート クラスでは、UCS-2 または UCS-4 としてエンコードされたワイド文字と、UTF-16LE (Mode と little_endian の場合) または UTF-16BE (その他の場合) としてエンコードされたバイト ストリームを変換します。

このバイト ストリームはバイナリ ファイルに書き込む必要があります。テキスト ファイルに書き込むと、破損する場合があります。

## <a name="requirements"></a>要件
ヘッダー: \<codecvt> 名前空間: std
