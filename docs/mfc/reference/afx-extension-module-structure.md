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
ms.sourcegitcommit: bb94e24657d16b2a3eda3a770c2b6ae734c6006f
ms.openlocfilehash: 4bc0dafbc4d09f5c53ff502876da2e250d537882
ms.lasthandoff: 04/12/2017

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
 **TRUE**で DLL モジュールが初期化されている場合`AfxInitExtensionModule`です。  
  
 `hModule`  
 DLL のモジュールのハンドルを指定します。  
  
 *hResource*  
 DLL のカスタム リソース モジュールのハンドルを指定します。  
  
 *pFirstSharedClass*  
 情報へのポインター (、`CRuntimeClass`構造) は、DLL モジュールの最初のランタイム クラスです。 ランタイム クラスの一覧の先頭を指定するために使用します。  
  
 *pFirstSharedFactory*  
 DLL モジュールの最初のオブジェクト ファクトリへのポインター (、`COleObjectFactory`オブジェクト)。 クラス ファクトリの一覧の先頭を指定するために使用します。  
  
## <a name="remarks"></a>コメント  
 MFC 拡張 Dll で次の 2 つを行う必要性、`DllMain`関数。  
  
-   呼び出す[AfxInitExtensionModule](extension-dll-macros.md#afxinitextensionmodule)戻り値を確認します。  
  
-   作成、 **CDynLinkLibrary**オブジェクトの DLL をエクスポートするかどうかは[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)独自のカスタム リソースまたはオブジェクトします。  
  
 `AFX_EXTENSION_MODULE`構造を使用して拡張機能の拡張 DLL で通常の静的オブジェクトの構築の前に実行の一部として初期化されているランタイム クラスのオブジェクトのコピーを含む、DLL のモジュール状態のコピーを保持する`DllMain`を入力します。 例:  
  
 [!code-cpp[NVC_MFC_DLL 2](../../atl-mfc-shared/codesnippet/cpp/afx-extension-module-structure_1.cpp)]  
  
 格納されているモジュールの情報、`AFX_EXTENSION_MODULE`に構造をコピーすることができます、 **CDynLinkLibrary**オブジェクト。 例:  
  
 [!code-cpp[NVC_MFC_DLL #5](../../atl-mfc-shared/codesnippet/cpp/afx-extension-module-structure_2.cpp)]  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afx.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [AfxInitExtensionModule](extension-dll-macros.md#afxinitextensionmodule)   
 [AfxTermExtensionModule](extension-dll-macros.md#afxtermextensionmodule)


