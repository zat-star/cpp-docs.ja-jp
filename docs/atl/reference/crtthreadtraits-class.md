---
title: "CRTThreadTraits クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CRTThreadTraits
- ATL.CRTThreadTraits
- CRTThreadTraits
dev_langs:
- C++
helpviewer_keywords:
- CRTThreadTraits class
- threading [ATL], creation functions
- threading [ATL], CRT threads
ms.assetid: eb6e20b0-c2aa-4170-8e34-aaeeacc86343
caps.latest.revision: 21
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
ms.openlocfilehash: 24cee5c74819d9a880bedbcebcce4dabfabae960
ms.lasthandoff: 02/24/2017

---
# <a name="crtthreadtraits-class"></a>CRTThreadTraits クラス
このクラスは、CRT のスレッドの作成機能を提供します。 スレッドが CRT 関数を使用する場合は、このクラスを使用します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class CRTThreadTraits
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CRTThreadTraits::CreateThread](#createthread)|(静的)CRT 関数を使用してスレッドを作成するには、この関数を呼び出します。|  
  
## <a name="remarks"></a>コメント  
 スレッドの特徴 (traits) は、特定の種類のスレッドの作成機能を提供するクラスです。 作成関数が、Windows と同じシグネチャとセマンティクスが[CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453)関数です。  
  
 スレッドの特徴 (traits) は、次のクラスによって使用されます。  
  
- [CThreadPool](../../atl/reference/cthreadpool-class.md)  
  
- [使用](../../atl/reference/cworkerthread-class.md)  
  
 場合は、スレッドがあるを使用していない CRT 関数を使用して[Win32ThreadTraits](../../atl/reference/win32threadtraits-class.md)代わりにします。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
##  <a name="a-namecreatethreada--crtthreadtraitscreatethread"></a><a name="createthread"></a>CRTThreadTraits::CreateThread  
 CRT 関数を使用してスレッドを作成するには、この関数を呼び出します。  
  
```
static HANDLE CreateThread(
    LPSECURITY_ATTRIBUTES lpsa,
    DWORD dwStackSize,
    LPTHREAD_START_ROUTINE pfnThreadProc,
    void* pvParam,
    DWORD dwCreationFlags,
    DWORD* pdwThreadId) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lpsa`  
 新しいスレッドのセキュリティ属性。  
  
 `dwStackSize`  
 新しいスレッドのスタック サイズ。  
  
 `pfnThreadProc`  
 新しいスレッドのスレッドのプロシージャです。  
  
 `pvParam`  
 スレッドのプロシージャに渡されるパラメーター。  
  
 `dwCreationFlags`  
 フラグ (0 または CREATE_SUSPENDED) を作成します。  
  
 `pdwThreadId`  
 [out]成功した場合、新しく作成されたスレッドのスレッド ID を受け取る DWORD 変数のアドレスです。  
  
### <a name="return-value"></a>戻り値  
 失敗した場合、新しく作成されたスレッドにハンドルを返します。 呼び出す[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)拡張エラー情報を取得します。  
  
### <a name="remarks"></a>コメント  
 参照してください[CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453)についてさらにこの関数のパラメーターです。  
  
 この関数は[_beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md)スレッドを作成します。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)

