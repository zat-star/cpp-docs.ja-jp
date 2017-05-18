---
title: "ISupportErrorInfoImpl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ISupportErrorInfoImpl
- ATLCOM/ATL::ISupportErrorInfoImpl
- ATLCOM/ATL::ISupportErrorInfoImpl::InterfaceSupportsErrorInfo
dev_langs:
- C++
helpviewer_keywords:
- ISupportErrorInfo ATL implementation
- ISupportErrorInfoImpl class
- error information, ATL
ms.assetid: e33a4b11-a123-41cf-bcea-7b19743902af
caps.latest.revision: 23
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 320cb27d1d22a5e4240861c934e9bcfabd731bad
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="isupporterrorinfoimpl-class"></a>ISupportErrorInfoImpl クラス
このクラスの既定の実装を提供する、 [ISupportErrorInfo インターフェイス](http://msdn.microsoft.com/en-us/42d33066-36b4-4a5b-aa5d-46682e560f32)1 つのインターフェイスのみがオブジェクト上のエラーを生成するときに使用できます。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template<const IID* piid>  
class ATL_NO_VTABLE ISupportErrorInfoImpl 
   : public ISupportErrorInfo
```  
  
#### <a name="parameters"></a>パラメーター  
 `piid`  
 サポートされるインターフェイスの IID へのポインター [IErrorInfo](http://msdn.microsoft.com/en-us/4dda6909-2d9a-4727-ae0c-b5f90dcfa447)します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[ISupportErrorInfoImpl::InterfaceSupportsErrorInfo](#interfacesupportserrorinfo)|インターフェイスがで識別されるかどうかを示す`riid`をサポートしています、 [IErrorInfo](http://msdn.microsoft.com/en-us/4dda6909-2d9a-4727-ae0c-b5f90dcfa447)インターフェイスです。|  
  
## <a name="remarks"></a>コメント  
 [ISupportErrorInfo インターフェイス](http://msdn.microsoft.com/en-us/42d33066-36b4-4a5b-aa5d-46682e560f32)エラー情報がクライアントに返されることを確認します。 使用するオブジェクト**IErrorInfo**を実装する必要があります**ISupportErrorInfo**します。  
  
 クラス`ISupportErrorInfoImpl`の既定の実装を提供**ISupportErrorInfo**&1; つのインターフェイスのみがオブジェクト上のエラーを生成するときに使用できます。 例:  
  
 [!code-cpp[NVC_ATL_COM&#48;](../../atl/codesnippet/cpp/isupporterrorinfoimpl-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `ISupportErrorInfo`  
  
 `ISupportErrorInfoImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="interfacesupportserrorinfo"></a>ISupportErrorInfoImpl::InterfaceSupportsErrorInfo  
 インターフェイスがで識別されるかどうかを示す`riid`をサポートしています、 [IErrorInfo](http://msdn.microsoft.com/en-us/4dda6909-2d9a-4727-ae0c-b5f90dcfa447)インターフェイスです。  
  
```
STDMETHOD(InterfaceSupportsErrorInfo)(REFIID riid);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[ISupportErrorInfo::InterfaceSupportsErrorInfo](http://msdn.microsoft.com/en-us/a54ef18d-ee3f-4483-ac4a-99d758f0960a)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="getsize"></a>IThreadPoolConfig::GetSize  
 プールのスレッドの数を取得するには、このメソッドを呼び出します。  
  
```
STDMETHOD(GetSize)(int* pnNumThreads);
```  
  
### <a name="parameters"></a>パラメーター  
 `pnNumThreads`  
 [out]成功した場合に、プールのスレッドの数を受け取る変数のアドレスです。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities #&134;](../../atl/codesnippet/cpp/isupporterrorinfoimpl-class_2.cpp)]  
  
##  <a name="gettimeout"></a>IThreadPoolConfig::GetTimeout  
 シャット ダウンするスレッドのスレッド プールが待機するミリ秒単位で最大の時刻を取得するには、このメソッドを呼び出します。  
  
```
STDMETHOD(GetTimeout)(DWORD* pdwMaxWait);
```  
  
### <a name="parameters"></a>パラメーター  
 `pdwMaxWait`  
 [out]成功した場合に、スレッド プールがシャット ダウンするスレッドを待機するミリ秒単位で時間の最大値を受け取る変数のアドレスです。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="example"></a>例  
 参照してください[IThreadPoolConfig::GetSize](#getsize)します。  
  
##  <a name="setsize"></a>IThreadPoolConfig::SetSize  
 プールのスレッドの数を設定するには、このメソッドを呼び出します。  
  
```
STDMETHOD(SetSize)int nNumThreads);
```  
  
### <a name="parameters"></a>パラメーター  
 `nNumThreads`  
 要求された、プール内のスレッド数。  
  
 場合`nNumThreads`は負の場合、その絶対値を掛けたスレッドの合計数を取得するマシンのプロセッサ数です。  
  
 場合`nNumThreads`0 の場合は、 [ATLS_DEFAULT_THREADSPERPROC](http://msdn.microsoft.com/library/e0dcf107-72a9-4122-abb4-83c63aa7d571)スレッドの合計数を取得するマシンのプロセッサ数で乗算されます。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="example"></a>例  
 参照してください[IThreadPoolConfig::GetSize](#getsize)します。  
  
##  <a name="settimeout"></a>IThreadPoolConfig::SetTimeout  
 シャット ダウンするスレッドのスレッド プールが待機するミリ秒単位で時間の最大値を設定するには、このメソッドを呼び出します。  
  
```
STDMETHOD(SetTimeout)(DWORD dwMaxWait);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwMaxWait`  
 シャット ダウンするスレッドのスレッド プールが待機するミリ秒単位で要求の最大時間。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="example"></a>例  
 参照してください[IThreadPoolConfig::GetSize](#getsize)します。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)

