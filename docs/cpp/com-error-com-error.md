---
title: "_com_error::_com_error |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_error::_com_error
dev_langs:
- C++
helpviewer_keywords:
- _com_error method [C++]
ms.assetid: 0a69e46c-caab-49ef-b091-eee401253ce6
caps.latest.revision: 6
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
ms.openlocfilehash: 81efabf796d8d596326629af999f1932501befb5
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="comerrorcomerror"></a>_com_error::_com_error
**Microsoft 固有の仕様**  
  
 `_com_error` オブジェクトを構築します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      _com_error(  
   HRESULT hr,  
   IErrorInfo* perrinfo = NULL,  
   bool fAddRef=false  
) throw( );  
_com_error(  
   const _com_error& that   
) throw( );  
```  
  
#### <a name="parameters"></a>パラメーター  
 `hr`  
 `HRESULT` 情報。  
  
 `perrinfo`  
 **IErrorInfo**オブジェクト。  
  
 **bool fAddRef = false**  
 コンス トラクターに null 以外の AddRef を呼び出すことと、 **IErrorInfo**インターフェイスです。 こうすることで、次の例のように、インターフェイスの所有権が `_com_error` オブジェクトに渡される一般的なケースで参照カウントが正しく実行されます。  
  
```  
throw _com_error(hr, perrinfo);  
```  
  
 所有権を転送するようにコードをしないかどうか、`_com_error`オブジェクト、および`AddRef`をオフセットするために必要な**リリース**で、`_com_error`デストラクター、次のように、オブジェクトの構築します。  
  
```  
_com_error err(hr, perrinfo, true);  
```  
  
 `that`  
 既存の `_com_error` オブジェクト。  
  
## <a name="remarks"></a>コメント  
 最初のコンス トラクターは、指定された新しいオブジェクトを作成、`HRESULT`と省略可能な**IErrorInfo**オブジェクト。 2 つ目のコンストラクターは、既存の `_com_error` オブジェクトのコピーを作成します。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_com_error クラス](../cpp/com-error-class.md)
