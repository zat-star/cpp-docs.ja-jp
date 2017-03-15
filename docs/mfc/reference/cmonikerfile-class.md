---
title: "CMonikerFile クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMonikerFile
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 4668672af1b33170ece1cb4d449ed5a20f6040e7
ms.lasthandoff: 02/24/2017

---
# <a name="cmonikerfile-class"></a>CMonikerFile クラス
データのストリームを表します ( [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034)) を付けた、 [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705)します。  
  
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
|[CMonikerFile::Detach](#detach)|デタッチ、`IMoniker`これから`CMonikerFile`オブジェクトです。|  
|[CMonikerFile::GetMoniker](#getmoniker)|現在のモニカーを取得します。|  
|[CMonikerFile::Open](#open)|ストリームを取得する指定されたファイルを開きます。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMonikerFile::CreateBindContext](#createbindcontext)|バインド コンテキストを取得するか、既定で初期化されたバインド コンテキストを作成します。|  
  
## <a name="remarks"></a>コメント  
 モニカーには、ファイルのパス名のような情報が含まれています。 モニカー オブジェクトへのポインターがあるかどうかは`IMoniker`インターフェイスをファイルが実際にある場所に関するその他の特定の情報をしなくても、指定したファイルへのアクセスを取得できます。  
  
 派生した`COleStreamFile`、`CMonikerFile`モニカーまたはモニカーに文字列の形式は、モニカーは名前のストリームにバインドします。 読み取るし、そのストリームに書き込むことができます。 本来の目的`CMonikerFile`は簡単なアクセスを提供する`IStream`s が付けた`IMoniker`s 自分でストリームにバインドする必要はありませんようにまだが`CFile`ストリームに機能します。  
  
 `CMonikerFile`ストリーム以外の値にバインドを使用できません。 ストレージまたはオブジェクトにバインドする場合は、使用する必要があります、`IMoniker`インターフェイスを直接します。  
  
 ストリームとモニカーの詳細については、次を参照してください。[関数](../../mfc/reference/colestreamfile-class.md)で、 *『 MFC リファレンス*と[IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034)と[IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [関数](../../mfc/reference/colestreamfile-class.md)  
  
 `CMonikerFile`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxole.h  
  
##  <a name="a-nameclosea--cmonikerfileclose"></a><a name="close"></a>CMonikerFile::Close  
 この関数をデタッチし、ストリームを解放し、モニカーを解放します。  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>コメント  
 開かれていないか、既に解決済みのストリームで呼び出すことができます。  
  
##  <a name="a-namecmonikerfilea--cmonikerfilecmonikerfile"></a><a name="cmonikerfile"></a>CMonikerFile::CMonikerFile  
 `CMonikerFile` オブジェクトを構築します。  
  
```  
CMonikerFile();
```  
  
##  <a name="a-namecreatebindcontexta--cmonikerfilecreatebindcontext"></a><a name="createbindcontext"></a>CMonikerFile::CreateBindContext  
 既定で初期化されたバインド コンテキストを作成するには、この関数を呼び出します。  
  
```  
IBindCtx* CreateBindContext(CFileException* pError);
```  
  
### <a name="parameters"></a>パラメーター  
 `pError`  
 ファイルの例外へのポインター。 エラーが発生した場合、原因に設定されます。  
  
### <a name="return-value"></a>戻り値  
 バインド コンテキストへのポインター [IBindCtx](http://msdn.microsoft.com/library/windows/desktop/ms693755)成功以外の場合は、バインドを**NULL**します。 インスタンスが開かれた場合、`IBindHost`インターフェイス、バインド コンテキストはから取得した、`IBindHost`です。 ある場合ない`IBindHost`インターフェイスまたはインターフェイスは、バインド コンテキストに失敗した場合は、バインド コンテキストを作成します。 詳細については、 [IBindHost](http://msdn.microsoft.com/library/ie/ms775076)インターフェイスを参照してください、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="remarks"></a>コメント  
 バインド コンテキストは、特定のモニカー バインド操作に関する情報を格納するオブジェクトです。 独自のバインド コンテキストを提供するには、この関数をオーバーライドすることができます。  
  
##  <a name="a-namedetacha--cmonikerfiledetach"></a><a name="detach"></a>CMonikerFile::Detach  
 この関数を呼び出してストリームを閉じます。  
  
```  
BOOL Detach(CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pError`  
 ファイルの例外へのポインター。 エラーが発生した場合、原因に設定されます。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
##  <a name="a-namegetmonikera--cmonikerfilegetmoniker"></a><a name="getmoniker"></a>CMonikerFile::GetMoniker  
 現在のモニカーへのポインターを取得するには、この関数を呼び出します。  
  
```  
IMoniker* GetMoniker() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在のモニカー インターフェイスへのポインター ( [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705))。  
  
### <a name="remarks"></a>コメント  
 `CMonikerFile` 、インターフェイスではない返されるポインターは参照カウントをインクリメントしていない (を通じて[AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379))、モニカーが離されたときに、`CMonikerFile`オブジェクトを解放します。 モニカーの保持またはそれを解放するには、まず`AddRef`ことです。  
  
##  <a name="a-nameopena--cmonikerfileopen"></a><a name="open"></a>CMonikerFile::Open  
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
 モニカー インターフェイスへのポインター`IMoniker`ストリームを取得するためです。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 `lpszURL`パラメーターは、Macintosh で使用することはできません。 のみ、`pMoniker`形式の**開く**Macintosh で使用できます。  
  
 URL またはファイルの名前を使用する、`lpszURL`パラメーター。 例:  
  
 [!code-cpp[NVC_MFCWinInet&6;](../../mfc/codesnippet/cpp/cmonikerfile-class_1.cpp)]  
  
 または  
  
 [!code-cpp[NVC_MFCWinInet&#7;](../../mfc/codesnippet/cpp/cmonikerfile-class_2.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [関数のクラス](../../mfc/reference/colestreamfile-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CAsyncMonikerFile クラス](../../mfc/reference/casyncmonikerfile-class.md)

