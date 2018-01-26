---
title: "_com_raise_error |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _com_raise_error
dev_langs: C++
helpviewer_keywords: _com_raise_error function
ms.assetid: a98226c2-c3fe-44f1-8ff5-85863de11cd6
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 71a4be4ebf6029d0573aee71d74bf9faa241319f
ms.sourcegitcommit: 9a0a287d6940591523af959ebdac5affa36220da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/25/2018
---
# <a name="comraiseerror"></a>_com_raise_error
**Microsoft 固有の仕様**  
  
 スロー、 [_com_error](../cpp/com-error-class.md)エラーに応答します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      void __stdcall _com_raise_error(  
   HRESULT hr,  
   IErrorInfo* perrinfo = 0  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `hr`  
 `HRESULT` 情報。  
  
 `perrinfo`  
 **IErrorInfo**オブジェクト。  
  
## <a name="remarks"></a>コメント  
 `_com_raise_error`、で定義されている\<comdef.h >、同じ名前とプロトタイプのユーザーが記述したバージョンで置き換えることができます。 `#import` を使用し、C++ 例外処理を使用しない場合は、こうすることができます。 その場合、ユーザーのバージョンで**_com_raise_error**を行うことができます、`longjmp`またはメッセージ ボックスを表示および停止します。 ユーザー バージョンで返すことはできません。コンパイラ COM サポート コードがそれを予期していないためです。  
  
 使用することも[_set_com_error_handler](../cpp/set-com-error-handler.md)を既定のエラー処理関数を置き換えます。  
  
 既定では、`_com_raise_error` は次のように定義されています。  
  
```  
void __stdcall _com_raise_error(HRESULT hr, IErrorInfo* perrinfo) {  
   throw _com_error(hr, perrinfo);  
}  
```  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<comdef.h >  
  
 **Lib:**場合、 **wchar_t をネイティブ型**コンパイラ オプションは、comsuppw.lib または comsuppwd.lib を使用します。 場合**wchar_t をネイティブ型**オフ、comsupp.lib を使用します。 「[/Zc:wchar_t (wchar_t をネイティブ型として認識)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [コンパイラ COM グローバル関数](../cpp/compiler-com-global-functions.md)   
 [_set_com_error_handler](../cpp/set-com-error-handler.md)