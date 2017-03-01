---
title: "CAtlFileMappingBase クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CAtlFileMappingBase
- ATL::CAtlFileMappingBase
- CAtlFileMappingBase
dev_langs:
- C++
helpviewer_keywords:
- CAtlFileMappingBase class
ms.assetid: be555723-2790-4f57-a8fb-be4d68460775
caps.latest.revision: 20
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 439f123bc0addbbec2a26102d0197d0a1f14a8d5
ms.lasthandoff: 02/24/2017

---
# <a name="catlfilemappingbase-class"></a>CAtlFileMappingBase クラス
このクラスは、メモリ マップト ファイルを表します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class CAtlFileMappingBase
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlFileMappingBase::CAtlFileMappingBase](#catlfilemappingbase)|コンストラクターです。|  
|[CAtlFileMappingBase:: ~ CAtlFileMappingBase](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlFileMappingBase::CopyFrom](#copyfrom)|ファイル マッピング オブジェクトからコピーするには、このメソッドを呼び出します。|  
|[CAtlFileMappingBase::GetData](#getdata)|ファイル マッピング オブジェクトからデータを取得するには、このメソッドを呼び出します。|  
|[CAtlFileMappingBase::GetHandle](#gethandle)|このメソッドを呼び出してファイル ハンドルを返します。|  
|[CAtlFileMappingBase::GetMappingSize](#getmappingsize)|ファイル マッピング オブジェクトからマップのサイズを取得するには、このメソッドを呼び出します。|  
|[CAtlFileMappingBase::MapFile](#mapfile)|ファイル マッピング オブジェクトを作成するには、このメソッドを呼び出します。|  
|[CAtlFileMappingBase::MapSharedMem](#mapsharedmem)|すべてのプロセスへのフル アクセスを許可するファイル マッピング オブジェクトを作成するには、このメソッドを呼び出します。|  
|[CAtlFileMappingBase::OpenMapping](#openmapping)|ファイル マッピング オブジェクトにハンドルを返すには、このメソッドを呼び出します。|  
|[CAtlFileMappingBase::Unmap](#unmap)|ファイル マッピング オブジェクトをマップ解除するには、このメソッドを呼び出します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlFileMappingBase::operator =](#operator_eq)|現在のファイル マッピング オブジェクトを別のファイル マッピング オブジェクトに設定します。|  
  
## <a name="remarks"></a>コメント  
 ファイルのマッピングは、プロセスの仮想アドレス空間の一部で、ファイルの内容の関連付けです。 このクラスは、簡単にアクセスしてデータを共有するプログラムが使用できるファイル マッピング オブジェクトを作成するためのメソッドを提供します。  
  
 詳細については、次を参照してください。[ファイル マッピング](http://msdn.microsoft.com/library/windows/desktop/aa366556)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlfile.h  
  
##  <a name="a-namecatlfilemappingbasea--catlfilemappingbasecatlfilemappingbase"></a><a name="catlfilemappingbase"></a>CAtlFileMappingBase::CAtlFileMappingBase  
 コンストラクターです。  
  
```
CAtlFileMappingBase(CAtlFileMappingBase& orig);  
CAtlFileMappingBase() throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `orig`  
 新しいオブジェクトを作成するコピー元のファイル マッピング オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 必要に応じて、既存のオブジェクトを使用して、新しいファイル マッピング オブジェクトを作成します。 呼び出す必要が[CAtlFileMappingBase::MapFile](#mapfile)を開くか、特定のファイルのファイル マッピング オブジェクトを作成します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities #&71;](../../atl/codesnippet/cpp/catlfilemappingbase-class_1.cpp)]  
  
##  <a name="a-namedtora--catlfilemappingbasecatlfilemappingbase"></a><a name="dtor"></a>CAtlFileMappingBase:: ~ CAtlFileMappingBase  
 デストラクターです。  
  
```
~CAtlFileMappingBase() throw();
```  
  
### <a name="remarks"></a>コメント  
 クラスとの呼び出しによって割り当てられているリソースを解放、 [CAtlFileMappingBase::Unmap](#unmap)メソッドです。  
  
##  <a name="a-namecopyfroma--catlfilemappingbasecopyfrom"></a><a name="copyfrom"></a>CAtlFileMappingBase::CopyFrom  
 ファイル マッピング オブジェクトからコピーするには、このメソッドを呼び出します。  
  
```
HRESULT CopyFrom(CAtlFileMappingBase& orig) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `orig`  
 コピーする元のファイル マッピング オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 返します。`S_OK`に成功した場合、またはエラー`HRESULT`失敗します。  
  
##  <a name="a-namegetdataa--catlfilemappingbasegetdata"></a><a name="getdata"></a>CAtlFileMappingBase::GetData  
 ファイル マッピング オブジェクトからデータを取得するには、このメソッドを呼び出します。  
  
```
void* GetData() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 データへのポインターを返します。  
  
##  <a name="a-namegethandlea--catlfilemappingbasegethandle"></a><a name="gethandle"></a>CAtlFileMappingBase::GetHandle  
 ファイル マッピング オブジェクトにハンドルを返すには、このメソッドを呼び出します。  
  
```
HANDLE GetHandle() throw ();
```  
  
### <a name="return-value"></a>戻り値  
 ファイル マッピング オブジェクトへのハンドルを返します。  
  
##  <a name="a-namegetmappingsizea--catlfilemappingbasegetmappingsize"></a><a name="getmappingsize"></a>CAtlFileMappingBase::GetMappingSize  
 ファイル マッピング オブジェクトからマップのサイズを取得するには、このメソッドを呼び出します。  
  
```
SIZE_T GetMappingSize() throw();
```  
  
### <a name="return-value"></a>戻り値  
 マップのサイズを返します。  
  
### <a name="example"></a>例  
 例を参照してください[CAtlFileMappingBase::CAtlFileMappingBase](#catlfilemappingbase)します。  
  
##  <a name="a-namemapfilea--catlfilemappingbasemapfile"></a><a name="mapfile"></a>CAtlFileMappingBase::MapFile  
 開くか、指定したファイルのファイル マッピング オブジェクトを作成するには、このメソッドを呼び出します。  
  
```
HRESULT MapFile(
    HANDLE hFile,
    SIZE_T nMappingSize = 0,
    ULONGLONG nOffset = 0,
    DWORD dwMappingProtection = PAGE_READONLY,
    DWORD dwViewDesiredAccess = FILE_MAP_READ) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `hFile`  
 マッピング オブジェクトを作成するためのファイルへのハンドルします。 `hFile`有効である必要があるあり、INVALID_HANDLE_VALUE に設定することはできません。  
  
 `nMappingSize`  
 マップのサイズ。 指定されたファイルの現在のサイズにファイル マッピング オブジェクトの最大サイズは 0 の場合、 *hFile します。*  
  
 `nOffset`  
 ファイル オフセットは、マッピングの開始位置。 オフセットの値は、システムのメモリ割り当ての粒度の倍数である必要があります。  
  
 `dwMappingProtection`  
 ファイルがマップされている場合は、ファイルのビューに必要な保護します。 参照してください`flProtect`で[CreateFileMapping](http://msdn.microsoft.com/library/windows/desktop/aa366537)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `dwViewDesiredAccess`  
 ファイルのビューと、ファイルによってマップされるページの保護へのアクセスの種類を指定します。 参照してください`dwDesiredAccess`で[MapViewOfFileEx](http://msdn.microsoft.com/library/windows/desktop/aa366763)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="return-value"></a>戻り値  
 返します。`S_OK`に成功した場合、またはエラー`HRESULT`失敗します。  
  
### <a name="remarks"></a>コメント  
 ファイルのサイズがファイル マッピング オブジェクトのサイズを超えないファイル マッピング オブジェクトが作成されたら、場合は、一部のファイルの内容は使用できない場合を共有するためです。 詳細については、次を参照してください。 [CreateFileMapping](http://msdn.microsoft.com/library/windows/desktop/aa366537)と[MapViewOfFileEx](http://msdn.microsoft.com/library/windows/desktop/aa366763)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 例を参照してください[CAtlFileMappingBase::CAtlFileMappingBase](#catlfilemappingbase)します。  
  
##  <a name="a-namemapsharedmema--catlfilemappingbasemapsharedmem"></a><a name="mapsharedmem"></a>CAtlFileMappingBase::MapSharedMem  
 すべてのプロセスへのフル アクセスを許可するファイル マッピング オブジェクトを作成するには、このメソッドを呼び出します。  
  
```
HRESULT MapSharedMem(
    SIZE_T nMappingSize,
    LPCTSTR szName,
    BOOL* pbAlreadyExisted = NULL,
    LPSECURITY_ATTRIBUTES lpsa = NULL,
    DWORD dwMappingProtection = PAGE_READWRITE,
    DWORD dwViewDesiredAccess = FILE_MAP_ALL_ACCESS) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nMappingSize`  
 マップのサイズ。 識別されるファイル マッピング オブジェクトの現在のサイズにファイル マッピング オブジェクトの最大サイズは 0 の場合、`szName.`  
  
 `szName`  
 マップ オブジェクトの名前。  
  
 *pbAlreadyExisted*  
 設定されている場合は TRUE、マップ オブジェクト既に BOOL 値へのポインターが存在しています。  
  
 `lpsa`  
 ポインター、 **SECURITY_ATTRIBUTES**返されたハンドルを子プロセスが継承できるかどうかを決定する構造体。 参照してください*lpAttributes*で[CreateFileMapping](http://msdn.microsoft.com/library/windows/desktop/aa366537)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `dwMappingProtection`  
 ファイルがマップされている場合は、ファイルの表示に必要な保護します。 参照してください`flProtect`で**CreateFileMapping**で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `dwViewDesiredAccess`  
 ファイルのビューと、ファイルによってマップされるページの保護へのアクセスの種類を指定します。 参照してください`dwDesiredAccess`で[MapViewOfFileEx](http://msdn.microsoft.com/library/windows/desktop/aa366763)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="return-value"></a>戻り値  
 返します。`S_OK`に成功した場合、またはエラー`HRESULT`失敗します。  
  
### <a name="remarks"></a>コメント  
 **MapShareMem**によって作成された既存のファイル マッピング オブジェクトは、 [CreateFileMapping](http://msdn.microsoft.com/library/windows/desktop/aa366537)プロセス間で共有します。  
  
##  <a name="a-nameopenmappinga--catlfilemappingbaseopenmapping"></a><a name="openmapping"></a>CAtlFileMappingBase::OpenMapping  
 指定したファイルの名前付きファイル マッピング オブジェクトを開くには、このメソッドを呼び出します。  
  
```
HRESULT OpenMapping(
    LPCTSTR szName,
    SIZE_T nMappingSize,
    ULONGLONG nOffset = 0,
    DWORD dwViewDesiredAccess = FILE_MAP_ALL_ACCESS) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `szName`  
 マップ オブジェクトの名前。 この名前のファイル マッピング オブジェクトへの開いているハンドルが存在し、マップ オブジェクトのセキュリティ記述子と競合していない場合、`dwViewDesiredAccess`パラメーター、オープン操作が成功します。  
  
 `nMappingSize`  
 マップのサイズ。 識別されるファイル マッピング オブジェクトの現在のサイズにファイル マッピング オブジェクトの最大サイズは 0 の場合、`szName.`  
  
 `nOffset`  
 ファイル オフセットは、マッピングの開始位置。 オフセットの値は、システムのメモリ割り当ての粒度の倍数である必要があります。  
  
 `dwViewDesiredAccess`  
 ファイルのビューと、ファイルによってマップされるページの保護へのアクセスの種類を指定します。 参照してください`dwDesiredAccess`で[MapViewOfFileEx](http://msdn.microsoft.com/library/windows/desktop/aa366763)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="return-value"></a>戻り値  
 返します。`S_OK`に成功した場合、またはエラー`HRESULT`失敗します。  
  
### <a name="remarks"></a>コメント  
 デバッグ ビルドでは、入力パラメーターが無効な場合に、アサーション エラーが発生します。  
  
##  <a name="a-nameoperatoreqa--catlfilemappingbaseoperator-"></a><a name="operator_eq"></a>CAtlFileMappingBase::operator =  
 現在のファイル マッピング オブジェクトを別のファイル マッピング オブジェクトに設定します。  
  
```
CAtlFileMappingBase& operator=(CAtlFileMappingBase& orig);
```  
  
### <a name="parameters"></a>パラメーター  
 `orig`  
 現在のファイル マッピング オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 現在のオブジェクトへの参照を返します。  
  
##  <a name="a-nameunmapa--catlfilemappingbaseunmap"></a><a name="unmap"></a>CAtlFileMappingBase::Unmap  
 ファイル マッピング オブジェクトをマップ解除するには、このメソッドを呼び出します。  
  
```
HRESULT Unmap() throw();
```  
  
### <a name="return-value"></a>戻り値  
 返します。`S_OK`に成功した場合、またはエラー`HRESULT`失敗します。  
  
### <a name="remarks"></a>コメント  
 参照してください[UnmapViewOfFile](http://msdn.microsoft.com/library/windows/desktop/aa366882)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]詳細です。  
  
## <a name="see-also"></a>関連項目  
 [CAtlFileMapping クラス](../../atl/reference/catlfilemapping-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

