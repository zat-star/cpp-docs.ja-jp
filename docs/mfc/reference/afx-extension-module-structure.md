---
title: "AFX_EXTENSION_MODULE 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AFX_EXTENSION_MODULE
dev_langs:
- C++
helpviewer_keywords:
- AFX_EXTENSION_MODULE structure
ms.assetid: b85a989c-d0c5-4b28-b53c-dad45b75704e
caps.latest.revision: 11
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
translationtype: Machine Translation
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: f2699316266e9cc061fa898c4176e36ae8323b33
ms.lasthandoff: 02/24/2017

---
# <a name="afxextensionmodule-structure"></a>AFX_EXTENSION_MODULE 構造体
`AFX_EXTENSION_MODULE`拡張 DLL のモジュールの状態を保持する MFC 拡張 Dll の初期化中に使用されます。  
  
## <a name="syntax"></a>構文  
  
```  
struct AFX_EXTENSION_MODULE  
{  
    BOOL bInitialized;  
    HMODULE hModule;  
    HMODULE hResource;  
    CRuntimeClass* pFirstSharedClass;  
    COleObjectFactory* pFirstSharedFactory;  
};  
```  
  
#### <a name="parameters"></a>パラメーター  
 *bInitialized*  
 **TRUE**で DLL モジュールが初期化されている場合`AfxInitExtensionModule`します。  
  
 `hModule`  
 DLL のモジュールのハンドルを指定します。  
  
 *hResource*  
 カスタム リソースの DLL のモジュールのハンドルを指定します。  
  
 *pFirstSharedClass*  
 情報へのポインター (、`CRuntimeClass`構造) DLL モジュールの最初のランタイム クラスの概要です。 ランタイム クラスの一覧の先頭を指定するために使用します。  
  
 *pFirstSharedFactory*  
 DLL モジュールの最初のオブジェクト ファクトリへのポインター (、`COleObjectFactory`オブジェクト)。 クラス ファクトリの一覧の先頭を指定するために使用します。  
  
## <a name="remarks"></a>コメント  
 MFC 拡張 Dll で&2; つの処理を行う必要性、`DllMain`関数。  
  
-   呼び出す[AfxInitExtensionModule](http://msdn.microsoft.com/library/15f0c820-ff34-4da6-8077-79afbbb8dac1)戻り値を確認します。  
  
-   作成、 **CDynLinkLibrary**オブジェクトの DLL をエクスポートするかどうかは[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)オブジェクトや、独自のカスタム リソースができます。  
  
 `AFX_EXTENSION_MODULE`拡張機能の拡張 DLL によって通常の静的オブジェクトの構築の前に実行の一部として初期化されたランタイム クラスのオブジェクトのコピーを含む、DLL のモジュール状態のコピーを保持する構造体を使用`DllMain`を入力します。 例:  
  
 [!code-cpp[NVC_MFC_DLL&2;](../../atl-mfc-shared/codesnippet/cpp/afx-extension-module-structure_1.cpp)]  
  
 格納されているモジュールの情報、`AFX_EXTENSION_MODULE`構造にコピーできる、 **CDynLinkLibrary**オブジェクトです。 例:  
  
 [!code-cpp[NVC_MFC_DLL&5;](../../atl-mfc-shared/codesnippet/cpp/afx-extension-module-structure_2.cpp)]  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afx.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [AfxInitExtensionModule](http://msdn.microsoft.com/library/15f0c820-ff34-4da6-8077-79afbbb8dac1)   
 [AfxTermExtensionModule](http://msdn.microsoft.com/library/b64de402-f1e3-4c26-9823-08c07876aaaa)


