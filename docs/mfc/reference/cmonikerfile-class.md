---
title: "CMonikerFile クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMonikerFile
- AFXOLE/CMonikerFile
- AFXOLE/CMonikerFile::CMonikerFile
- AFXOLE/CMonikerFile::Close
- AFXOLE/CMonikerFile::Detach
- AFXOLE/CMonikerFile::GetMoniker
- AFXOLE/CMonikerFile::Open
- AFXOLE/CMonikerFile::CreateBindContext
dev_langs:
- C++
helpviewer_keywords:
- CMonikerFile class
- monikers, MFC
- IMoniker interface, binding
- IMoniker interface
ms.assetid: 87be5966-f4f7-4235-bce2-1fa39e9417de
caps.latest.revision: 22
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 0f348328a4be4b934e00acdb43ba47fa919bac75
ms.contentlocale: ja-jp
ms.lasthandoff: 04/01/2017

---
# <a name="cmonikerfile-class"></a>CMonikerFile クラス
データのストリームを表します ( [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034)) によって指定された、 [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705)です。  
  
## <a name="syntax"></a>構文  
  
```  
class CMonikerFile : public COleStreamFile  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMonikerFile::CMonikerFile](#cmonikerfile)|`CMonikerFile` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMonikerFile::Close](#close)|関連付けを解除し、ストリームを解放し、モニカーを解放します。|  
|[CMonikerFile::Detach](#detach)|デタッチ、`IMoniker`これから`CMonikerFile`オブジェクト。|  
|[CMonikerFile::GetMoniker](#getmoniker)|現在のモニカーを取得します。|  
|[CMonikerFile::Open](#open)|ストリームを取得する指定されたファイルを開きます。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMonikerFile::CreateBindContext](#createbindcontext)|バインド コンテキストを取得するか、既定値に初期化バインド コンテキストを作成します。|  
  
## <a name="remarks"></a>コメント  
 モニカーには、ファイルへのパス名のような情報が含まれています。 モニカー オブジェクトへのポインターがあるかどうかは`IMoniker`インターフェイス、ファイルが実際に配置されているに関するその他の特定の情報をしなくても、特定のファイルへのアクセスを取得できます。  
  
 派生`COleStreamFile`、`CMonikerFile`モニカーまたはモニカーに文字列の形式は、モニカーは名前のストリームにバインドします。 読み取るし、そのストリームに書き込むことができます。 本来の目的`CMonikerFile`に簡単にアクセスを提供することです`IStream`s が付けた`IMoniker`s ので、自分でストリームにバインドする必要はありませんまだある`CFile`ストリームに機能します。  
  
 `CMonikerFile`ストリーム以外のすべてにバインドを使用できません。 記憶域またはオブジェクトにバインドする場合は、行う必要があります、`IMoniker`インターフェイスを直接です。  
  
 ストリームとモニカーの詳細については、次を参照してください。[関数](../../mfc/reference/colestreamfile-class.md)で、 *『 MFC リファレンス*と[IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034)と[IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [関数](../../mfc/reference/colestreamfile-class.md)  
  
 `CMonikerFile`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxole.h  
  
##  <a name="close"></a>CMonikerFile::Close  
 この関数をデタッチし、ストリームを解放し、モニカーを解放します。  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>コメント  
 開かれていないか、既に閉じられているストリームに対して呼び出すことができます。  
  
##  <a name="cmonikerfile"></a>CMonikerFile::CMonikerFile  
 `CMonikerFile` オブジェクトを構築します。  
  
```  
CMonikerFile();
```  
  
##  <a name="createbindcontext"></a>CMonikerFile::CreateBindContext  
 既定値に初期化バインド コンテキストを作成するには、この関数を呼び出します。  
  
```  
IBindCtx* CreateBindContext(CFileException* pError);
```  
  
### <a name="parameters"></a>パラメーター  
 `pError`  
 ファイルの例外へのポインター。 エラーが発生した場合、原因に設定されます。  
  
### <a name="return-value"></a>戻り値  
 バインド コンテキストへのポインター [IBindCtx](http://msdn.microsoft.com/library/windows/desktop/ms693755)それ以外の成功した場合は、バインドを**NULL**です。 インスタンスが開かれた場合、`IBindHost`インターフェイス、バインド コンテキストからを取得、`IBindHost`です。 ある場合ありません`IBindHost`インターフェイスまたはインターフェイスは、バインド コンテキストに失敗した場合は、バインド コンテキストを作成します。 詳細については、 [IBindHost](http://msdn.microsoft.com/library/ie/ms775076)インターフェイスを参照してください、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="remarks"></a>コメント  
 バインド コンテキストは、特定のモニカー バインド操作に関する情報を格納するオブジェクトです。 カスタム バインドのコンテキストを提供するには、この関数をオーバーライドすることができます。  
  
##  <a name="detach"></a>CMonikerFile::Detach  
 この関数では、ストリームを閉じます。  
  
```  
BOOL Detach(CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pError`  
 ファイルの例外へのポインター。 エラーが発生した場合、原因に設定されます。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
##  <a name="getmoniker"></a>CMonikerFile::GetMoniker  
 現在のモニカーを指すポインターを取得するには、この関数を呼び出します。  
  
```  
IMoniker* GetMoniker() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在のモニカー インターフェイスへのポインター ( [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705))。  
  
### <a name="remarks"></a>コメント  
 `CMonikerFile` 、インターフェイスではない返されるポインターは、参照カウントをインクリメントしない (を通じて[AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379))、モニカーがリリースされるとときに、`CMonikerFile`オブジェクトを解放します。 モニカーの保持またはそれを解放する場合は、する必要があります`AddRef`ことです。  
  
##  <a name="open"></a>CMonikerFile::Open  
 ファイルまたはモニカー オブジェクトを開くには、このメンバー関数を呼び出します。  
  
```  
virtual BOOL Open(
    LPCTSTR lpszURL,  
    CFileException* pError = NULL);

 
virtual BOOL Open(
    IMoniker* pMoniker,  
    CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszURL`  
 URL またはに開かれるファイルのファイル名。  
  
 `pError`  
 ファイルの例外へのポインター。 エラーが発生した場合、原因に設定されます。  
  
 `pMoniker`  
 モニカー インターフェイスへのポインター`IMoniker`ストリームを取得するために使用されます。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 `lpszURL` Macintosh でパラメーターを使用することはできません。 のみ、`pMoniker`形式の**開く**Macintosh で使用できます。  
  
 URL またはのファイル名を使用することができます、`lpszURL`パラメーター。 例:  
  
 [!code-cpp[NVC_MFCWinInet #6](../../mfc/codesnippet/cpp/cmonikerfile-class_1.cpp)]  
  
 - または  
  
 [!code-cpp[NVC_MFCWinInet #7](../../mfc/codesnippet/cpp/cmonikerfile-class_2.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [関数クラス](../../mfc/reference/colestreamfile-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CAsyncMonikerFile クラス](../../mfc/reference/casyncmonikerfile-class.md)

