---
title: "_com_error クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_error
dev_langs:
- C++
helpviewer_keywords:
- _com_error class
ms.assetid: 70dafa69-b1fb-4a5c-9249-e857e0793d42
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
ms.openlocfilehash: 670be1988adb3ef5afa9113b9988ceafb249801f
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="comerror-class"></a>_com_error クラス
**Microsoft 固有の仕様**  
  
 `_com_error` オブジェクトは、タイプ ライブラリから生成されるヘッダー ファイル内のエラー処理ラッパー関数によって、またはいずれかの COM サポート クラスによって検出される例外条件を表します。 `_com_error` クラスは、`HRESULT` エラー コードと、関連する任意の `IErrorInfo Interface` オブジェクトをカプセル化します。  
  
### <a name="construction"></a>構築  
  
|||  
|-|-|  
|[_com_error](../cpp/com-error-com-error.md)|`_com_error` オブジェクトを構築します。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[演算子 =](../cpp/com-error-operator-equal.md)|既存の `_com_error` オブジェクトを別のオブジェクトに割り当てます。|  
  
### <a name="extractor-functions"></a>抽出関数  
  
|||  
|-|-|  
|[エラー](../cpp/com-error-error.md)|コンストラクターに渡された `HRESULT` を取得します。|  
|[ErrorInfo](../cpp/com-error-errorinfo.md)|コンストラクターに渡された `IErrorInfo` オブジェクトを取得します。|  
|[WCode](../cpp/com-error-wcode.md)|カプセル化された `HRESULT` にマップされた 16 ビット エラー コードを取得します。|  
  
### <a name="ierrorinfo-functions"></a>IErrorInfo の関数  
  
|||  
|-|-|  
|[説明](../cpp/com-error-description.md)|`IErrorInfo::GetDescription` 関数を呼び出します。|  
|[HelpContext](../cpp/com-error-helpcontext.md)|`IErrorInfo::GetHelpContext` 関数を呼び出します。|  
|[ヘルプ ファイル](../cpp/com-error-helpfile.md)|`IErrorInfo::GetHelpFile` 関数を呼び出します。|  
|[Source](../cpp/com-error-source.md)|`IErrorInfo::GetSource` 関数を呼び出します。|  
|[GUID](../cpp/com-error-guid.md)|`IErrorInfo::GetGUID` 関数を呼び出します。|  
  
### <a name="format-message-extractor"></a>書式メッセージの抽出  
  
|||  
|-|-|  
|[エラー メッセージ](../cpp/com-error-errormessage.md)|`_com_error` オブジェクトに格納された HRESULT の文字列メッセージを取得します。|  
  
### <a name="exepinfowcode-to-hresult-mappers"></a>ExepInfo.wCode と HRESULT のマッパー  
  
|||  
|-|-|  
|[HRESULTToWCode](../cpp/com-error-hresulttowcode.md)|32 ビットの `HRESULT` を 16 ビットの `wCode` にマップします。|  
|[WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)|16 ビットをマップ`wCode`32 ビット`HRESULT`です。|  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** comdef.h  
  
 `Lib:`comsuppw.lib または comsuppwd.lib (を参照してください[/Zc:wchar_t (wchar_t をネイティブ型)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)詳細)  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ COM サポート クラス](../cpp/compiler-com-support-classes.md)   
 [IErrorInfo インターフェイス](http://msdn.microsoft.com/en-us/4dda6909-2d9a-4727-ae0c-b5f90dcfa447)
