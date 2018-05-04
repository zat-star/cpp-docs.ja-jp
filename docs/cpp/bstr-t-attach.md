---
title: _bstr_t::Attach |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::Attach
dev_langs:
- C++
helpviewer_keywords:
- Attach method [C++]
ms.assetid: 8cad867e-40fc-435b-841f-0d412c2f58d3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eeb114a33d3ac356bff16aeab47b8d894b7513e6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="bstrtattach"></a>_bstr_t::Attach
**Microsoft 固有の仕様**  
  
 `_bstr_t` ラッパーを `BSTR` にリンクします。  
  
## <a name="syntax"></a>構文  
  
```  
  
      void Attach(  
   BSTR s  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *s*  
 `BSTR` 変数に関連付けられる、または割り当てられる `_bstr_t`。  
  
## <a name="remarks"></a>コメント  
 `_bstr_t` が以前別の `BSTR` にアタッチされている場合、`_bstr_t` は、`BSTR` の他の変数が `_bstr_t` を使用していない場合 `BSTR` リソースをクリーンアップします。  
  
## <a name="example"></a>例  
 参照してください[_bstr_t::assign](../cpp/bstr-t-assign.md)使用例については**アタッチ**です。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_bstr_t クラス](../cpp/bstr-t-class.md)