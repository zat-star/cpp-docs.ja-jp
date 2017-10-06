---
title: "_com_error::ErrorMessage |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_error::ErrorMessage
dev_langs:
- C++
helpviewer_keywords:
- ErrorMessage method [C++]
ms.assetid: e47335b6-01af-4975-a841-121597479eb7
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
ms.openlocfilehash: 01f244a07e46c70cbd4810af666f55dc899e5c3a
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="comerrorerrormessage"></a>_com_error::ErrorMessage
**Microsoft 固有の仕様**  
  
 `HRESULT` オブジェクトに格納された `_com_error` の文字列メッセージを取得します。  
  
## <a name="syntax"></a>構文  
  
```  
  
const TCHAR * ErrorMessage( ) const throw( );  
  
```  
  
## <a name="return-value"></a>戻り値  
 `HRESULT` オブジェクト内に記録された `_com_error` の文字列メッセージを返します。 場合、`HRESULT`マップされた 16 ビット[wCode](../cpp/com-error-wcode.md)、一般的なメッセージでは、"`IDispatch error #<wCode>`"が返されます。 メッセージがない場合、一般的なメッセージ "`Unknown error #<hresult>`" が返されます。 返される文字列は Unicode またはマルチバイト文字列は、の状態に応じて、 **_UNICODE**マクロです。  
  
## <a name="remarks"></a>コメント  
 `HRESULT` オブジェクト内に記録された `_com_error` に適したシステム メッセージ テキストを取得します。 システム メッセージのテキストは、win32 取得[FormatMessage](http://msdn.microsoft.com/library/windows/desktop/ms679351)関数。 返される文字列は `FormatMessage` API によって割り当てられ、`_com_error` オブジェクトが破棄されるときに解放されます。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_com_error クラス](../cpp/com-error-class.md)
