---
title: "クラスの関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleStreamFile
- AFXOLE/COleStreamFile
- AFXOLE/COleStreamFile::COleStreamFile
- AFXOLE/COleStreamFile::Attach
- AFXOLE/COleStreamFile::CreateMemoryStream
- AFXOLE/COleStreamFile::CreateStream
- AFXOLE/COleStreamFile::Detach
- AFXOLE/COleStreamFile::GetStream
- AFXOLE/COleStreamFile::OpenStream
dev_langs:
- C++
helpviewer_keywords:
- data streams [C++]
- streams [C++], OLE
- data streams [C++], OLE
- structured storage in OLE
- OLE structured storage [C++]
- OLE [C++], streams of data
- COleStreamFile class
ms.assetid: e4f93698-e17c-4a18-a7c0-4b4df8eb4d93
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 0840d365f4179da0ad680256688eaf9484cb3cd8
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="colestreamfile-class"></a>関数のクラス
データのストリームを表します ( `IStream`) OLE 構造化記憶の一部として、複合ファイルにします。  
  
## <a name="syntax"></a>構文  
  
```  
class COleStreamFile : public CFile  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleStreamFile::COleStreamFile](#colestreamfile)|`COleStreamFile` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleStreamFile::Attach](#attach)|ストリームをオブジェクトに関連付けます。|  
|[COleStreamFile::CreateMemoryStream](#creatememorystream)|グローバル メモリからストリームを作成し、オブジェクトに関連付けます。|  
|[COleStreamFile::CreateStream](#createstream)|ストリームを作成し、オブジェクトに関連付けます。|  
|[COleStreamFile::Detach](#detach)|オブジェクトからストリームの関連付けを解除します。|  
|[COleStreamFile::GetStream](#getstream)|現在のストリームを返します。|  
|[COleStreamFile::OpenStream](#openstream)|安全なストリームを開きをオブジェクトに関連付けます。|  
  
## <a name="remarks"></a>コメント  
 `IStorage`ストリームを開くか、メモリ ストリームがある場合を除きを作成する前にオブジェクトが存在する必要があります。  
  
 `COleStreamFile`オブジェクトとまったく同じように操作する[CFile](../../mfc/reference/cfile-class.md)オブジェクトです。  
  
 ストリームとストレージ操作の詳細については、記事を参照してください[コンテナー: 複合ファイル](../../mfc/containers-compound-files.md).。  
  
 詳細については、次を参照してください。 [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034)と[IStorage](http://msdn.microsoft.com/library/windows/desktop/aa380015)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 `COleStreamFile`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxole.h  
  
##  <a name="attach"></a>COleStreamFile::Attach  
 指定された OLE ストリームを関連付ける、`COleStreamFile`オブジェクトです。  
  
```  
void Attach(LPSTREAM lpStream);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpStream`  
 OLE ストリームを指す ( `IStream`) オブジェクトに関連付ける。 ことはできません**NULL**します。  
  
### <a name="remarks"></a>コメント  
 オブジェクトおく必要がありますしない OLE ストリームに関連付けられています。  
  
 詳細については、次を参照してください。 [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="colestreamfile"></a>COleStreamFile::COleStreamFile  
 
          `COleStreamFile` オブジェクトを作成します。  
  
```  
COleStreamFile(LPSTREAM lpStream = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpStream`  
 オブジェクトに関連付けられている OLE ストリームへのポインター。  
  
### <a name="remarks"></a>コメント  
 場合`lpStream`は**NULL**、OLE ストリームに関連付けられているオブジェクトは、それ以外の場合、オブジェクトは、指定された OLE ストリームに関連付けられています。  
  
 詳細については、次を参照してください。 [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="creatememorystream"></a>COleStreamFile::CreateMemoryStream  
 安全に、通常は失敗、グローバル共有メモリが不足して新しいストリームを作成します。  
  
```  
BOOL CreateMemoryStream(CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pError`  
 指す、 [CFileException](../../mfc/reference/cfileexception-class.md)オブジェクトまたは**NULL**作成操作の完了状態を示します。 ストリームを作成しようとして生成される可能性のある例外を監視する場合は、このパラメーターを指定します。  
  
### <a name="return-value"></a>戻り値  
 ストリームが正常に作成された場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 OLE のサブシステムによって、メモリが割り当てられます。  
  
 詳細については、次を参照してください。 [CreateStreamOnHGlobal](http://msdn.microsoft.com/library/windows/desktop/aa378980)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="createstream"></a>COleStreamFile::CreateStream  
 指定されたストレージ オブジェクトが、通常は失敗で、新しいストリームを安全に作成します。  
  
```  
BOOL CreateStream(
    LPSTORAGE lpStorage,  
    LPCTSTR lpszStreamName,  
    DWORD nOpenFlags = modeReadWrite|shareExclusive|modeCreate,  
    CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpStorage`  
 作成するストリームを含む OLE ストレージ オブジェクトへのポインター。 ことはできません**NULL**します。  
  
 `lpszStreamName`  
 作成されるストリームの名前です。 ことはできません**NULL**します。  
  
 `nOpenFlags`  
 ストリームを開くときに使用するアクセス モード。 排他、読み取り/書き込み、および作成モードが既定で使用します。 使用可能なモードの一覧については、次を参照してください。[ほか](../../mfc/reference/cfile-class.md#cfile)します。  
  
 `pError`  
 指す、 [CFileException](../../mfc/reference/cfileexception-class.md)オブジェクトまたは**NULL**します。 ストリームを作成しようとして生成される可能性のある例外を監視する場合は、このパラメーターを指定します。  
  
### <a name="return-value"></a>戻り値  
 ストリームが正常に作成された場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 オープンに失敗した場合、ファイルの例外がスローされると`pError`は**NULL**します。  
  
 詳細については、次を参照してください。 [IStorage::CreateStream](http://msdn.microsoft.com/library/windows/desktop/aa380020)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="detach"></a>COleStreamFile::Detach  
 ストリームを閉じずに、オブジェクトからのストリームの関連付けを解除します。  
  
```  
LPSTREAM Detach();
```  
  
### <a name="return-value"></a>戻り値  
 ストリームへのポインター ( `IStream`) をオブジェクトに関連付けられていました。  
  
### <a name="remarks"></a>コメント  
 プログラムが終了する前に、その他のなんらかの方法でストリームを閉じる必要があります。  
  
 詳細については、次を参照してください。 [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="getstream"></a>COleStreamFile::GetStream  
 この関数では、現在のストリームへのポインターを返します。  
  
```  
IStream* GetStream() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在のストリーム インターフェイスへのポインター ( [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034))。  
  
##  <a name="openstream"></a>COleStreamFile::OpenStream  
 既存のストリームを開きます。  
  
```  
BOOL OpenStream(
    LPSTORAGE lpStorage,  
    LPCTSTR lpszStreamName,  
    DWORD nOpenFlags = modeReadWrite|shareExclusive,  
    CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpStorage`  
 開かれるストリームを含む OLE ストレージ オブジェクトへのポインター。 ことはできません**NULL**します。  
  
 `lpszStreamName`  
 開かれるストリームの名前です。 ことはできません**NULL**します。  
  
 `nOpenFlags`  
 ストリームを開くときに使用するアクセス モード。 排他および読み取り/書き込みモードは既定で使用します。 使用可能なモードの完全な一覧については[ほか](../../mfc/reference/cfile-class.md#cfile)します。  
  
 `pError`  
 指す、 [CFileException](../../mfc/reference/cfileexception-class.md)オブジェクトまたは**NULL**します。 ストリームを開こうとしたによって生成される可能性のある例外を監視する場合は、このパラメーターを指定します。  
  
### <a name="return-value"></a>戻り値  
 ストリームが正常に開かれている場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 オープンに失敗した場合、ファイルの例外がスローされると`pError`は**NULL**します。  
  
 詳細については、次を参照してください。 [IStorage::OpenStream](http://msdn.microsoft.com/library/windows/desktop/aa380025)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="see-also"></a>関連項目  
 [CFile クラス](../../mfc/reference/cfile-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)




