---
title: "_bstr_t::_bstr_t |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _bstr_t::_bstr_t
dev_langs:
- C++
helpviewer_keywords:
- BSTR object
- _bstr_t method [C++]
- _bstr_t class
ms.assetid: 116d994e-5a72-4351-afbe-866c80b4c165
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: ccf087d3b48a00de00eab7016563f59d4ad2d974
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="bstrtbstrt"></a>_bstr_t::_bstr_t
**Microsoft 固有の仕様**  
  
 `_bstr_t` オブジェクトを構築します。  
  
## <a name="syntax"></a>構文  
  
```  
_bstr_t( ) throw( );   
_bstr_t(  
   const _bstr_t& s1   
) throw( );  
_bstr_t(  
   const char* s2   
);  
_bstr_t(  
   const wchar_t* s3   
);  
_bstr_t(  
   const _variant_t& var   
);  
_bstr_t(  
   BSTR bstr,  
   bool fCopy   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `s1`  
 コピーされる `_bstr_t` オブジェクト。  
  
 `s2`  
 マルチバイト文字列。  
  
 `s3`  
 Unicode 文字列。  
  
 `var`  
 A [_variant_t](../cpp/variant-t-class.md)オブジェクト。  
  
 `bstr`  
 既存の `BSTR` オブジェクト。  
  
 `fCopy`  
 `false` の場合、`bstr` を呼び出してコピーを作成せずに、`SysAllocString` 引数が新しいオブジェクトにアタッチされます。  
  
## <a name="remarks"></a>コメント  
 `_bstr_t` のコンストラクターについて次の表で説明します。  
  
|コンストラクター|説明|  
|-----------------|-----------------|  
|`_bstr_t( )`|既定値を構築`_bstr_t`null 値をカプセル化するオブジェクト`BSTR`オブジェクト。|  
|`_bstr_t( _bstr_t&`  `s1`  `)`|別のコピーとして `_bstr_t` オブジェクトを構築します。<br /><br /> これは、*シャロー*コピーで、カプセル化された参照カウントをインクリメント`BSTR`作成する代わりに、新しいオブジェクト。|  
|`_bstr_t( char*`  `s2`  `)`|`_bstr_t` を呼び出して新しい `SysAllocString` オブジェクトを作成することで `BSTR` オブジェクトを構築し、そのオブジェクトをカプセル化します。<br /><br /> このコンストラクターは、マルチバイトから Unicode への変換を最初に実行します。|  
|`_bstr_t( wchar_t*`  `s3`  `)`|`_bstr_t` を呼び出して新しい `SysAllocString` オブジェクトを作成することで `BSTR` オブジェクトを構築し、そのオブジェクトをカプセル化します。|  
|`_bstr_t( _variant_t&`  `var`  `)`|最初に、カプセル化された VARIANT オブジェクトから `_bstr_t` オブジェクトを取得することによって、`_variant_t` オブジェクトから `BSTR` オブジェクトを構築します。|  
|`_bstr_t( BSTR`  `bstr` `, bool`  `fCopy`  `)`|(`_bstr_t` 文字列ではなく) 既存の `BSTR` から `wchar_t*` オブジェクトを構築します。 `fCopy` が false の場合、指定された `BSTR` オブジェクトは、`SysAllocString` を使って新しいコピーを作成せずに、新しいオブジェクトにアタッチされます。<br /><br /> このコンストラクターは、インターフェイス メソッドによって返される `BSTR` をカプセル化し、その所有権を得るために、タイプ ライブラリ ヘッダーのラッパー関数によって使用されます。|  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_bstr_t クラス](../cpp/bstr-t-class.md)   
 [_variant_t クラス](../cpp/variant-t-class.md)
