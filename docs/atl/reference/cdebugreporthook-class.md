---
title: "CDebugReportHook クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDebugReportHook
- ATLUTIL/ATL::CDebugReportHook
- ATLUTIL/ATL::CDebugReportHook::CDebugReportHook
- ATLUTIL/ATL::CDebugReportHook::CDebugReportHookProc
- ATLUTIL/ATL::CDebugReportHook::RemoveHook
- ATLUTIL/ATL::CDebugReportHook::SetHook
- ATLUTIL/ATL::CDebugReportHook::SetPipeName
- ATLUTIL/ATL::CDebugReportHook::SetTimeout
dev_langs:
- C++
helpviewer_keywords:
- CDebugReportHook class
ms.assetid: 798076c3-6e63-4286-83b8-aa1bbcd0c20c
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
ms.openlocfilehash: 632167d4f78ef930673450d6d087f32e91b6541f
ms.lasthandoff: 02/24/2017

---
# <a name="cdebugreporthook-class"></a>CDebugReportHook クラス
このクラスを使用して、名前付きパイプにデバッグ レポートを送信します。  
  
## <a name="syntax"></a>構文  
  
```
class CDebugReportHook
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CDebugReportHook::CDebugReportHook](#cdebugreporthook)|呼び出し[SetPipeName](#setpipename)、 [SetTimeout](#settimeout)、および[SetHook](#sethook)します。|  
|[CDebugReportHook:: ~ CDebugReportHook](#dtor)|呼び出し[CDebugReportHook::RemoveHook](#removehook)します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDebugReportHook::CDebugReportHookProc](#cdebugreporthookproc)|(静的)C ランタイム デバッグ レポート プロセスにフックするカスタム レポート関数。|  
|[CDebugReportHook::RemoveHook](#removehook)|名前付きパイプへのデバッグ レポートの送信を停止するには、このメソッドを呼び出すし、以前のレポート用のフックを復元します。|  
|[CDebugReportHook::SetHook](#sethook)|名前付きパイプへのデバッグ レポートの送信を開始するには、このメソッドを呼び出します。|  
|[CDebugReportHook::SetPipeName](#setpipename)|コンピューターとデバッグ レポートを送信するパイプの名前を設定するには、このメソッドを呼び出します。|  
|[CDebugReportHook::SetTimeout](#settimeout)|このクラスが使用可能になる名前付きパイプの待機するミリ秒単位で時間を設定するには、このメソッドを呼び出します。|  
  
## <a name="remarks"></a>コメント  
 サービスまたは名前付きパイプへデバッグ レポートを送信するアプリケーションのデバッグ ビルドでは、このクラスのインスタンスを作成します。 デバッグ レポートの呼び出しによって生成された[_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)など、この関数のラッパーの使用や、 [ATLTRACE](http://msdn.microsoft.com/library/c796baa5-e2b9-4814-a27d-d800590b102e)と[ATLASSERT](http://msdn.microsoft.com/library/98e3e0fc-77e2-499b-a6f6-b17a21c6fbd3)マクロです。  
  
 このクラスを使用すると、非対話型で実行されるコンポーネントを対話的にデバッグすることができます[ウィンドウ ステーション](http://msdn.microsoft.com/library/windows/desktop/ms687096)します。  
  
 スレッドの基になるセキュリティ コンテキストを使用してデバッグ レポートを送信することに注意してください。 低い特権のユーザーの権限の借用が行われているなどの web アプリケーションでの状況でデバッグ レポートを表示するように、権限借用が一時的に無効にします。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlutil.h  
  
##  <a name="cdebugreporthook"></a>CDebugReportHook::CDebugReportHook  
 呼び出し[SetPipeName](#setpipename)、 [SetTimeout](#settimeout)、および[SetHook](#sethook)します。  
  
```
CDebugReportHook(
    LPCSTR szMachineName = ".",
    LPCSTR szPipeName = "AtlsDbgPipe",
    DWORD dwTimeout = 20000) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `szMachineName`  
 デバッグ出力の送信先となるコンピューターの名前。 既定値は、ローカル コンピューターです。  
  
 `szPipeName`  
 デバッグ出力の送信先となる名前付きパイプの名前。  
  
 `dwTimeout`  
 このクラスが使用可能になる名前付きパイプの待機するミリ秒単位の時間。  
  
##  <a name="dtor"></a>CDebugReportHook:: ~ CDebugReportHook  
 呼び出し[CDebugReportHook::RemoveHook](#removehook)します。  
  
```
~CDebugReportHook() throw();
```  
  
##  <a name="cdebugreporthookproc"></a>CDebugReportHook::CDebugReportHookProc  
 C ランタイム デバッグ レポート プロセスにフックするカスタム レポート関数。  
  
```
static int __cdecl CDebugReportHookProc(
    int reportType,
    char* message,
    int* returnValue) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `reportType`  
 (_CRT_ASSERT や前述などの)、レポートの種類。  
  
 `message`  
 メッセージ文字列。  
  
 *戻り値*  
 によって返される値[_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)します。  
  
### <a name="return-value"></a>戻り値  
 かどうか、フックでメッセージを完全に処理できるように、それ以上レポートは必要ありません、FALSE を返します。 True の場合`_CrtDbgReport`通常どおりにメッセージを報告する必要があります。  
  
### <a name="remarks"></a>コメント  
 レポートの関数は、名前付きパイプを開き、もう一方の end プロセスと通信を試みます。 パイプがビジー状態の場合、レポートの関数はパイプが無料か、タイムアウトになるまで待機します。 コンス トラクターまたはへの呼び出しによって、タイムアウトを設定できる[CDebugReportHook::SetTimeout](#settimeout)します。  
  
 この関数のコードが呼び出し元のスレッドの基になるセキュリティ コンテキストで実行される、この関数の実行中、権限借用は、無効になっています。  
  
##  <a name="removehook"></a>CDebugReportHook::RemoveHook  
 名前付きパイプへのデバッグ レポートの送信を停止するには、このメソッドを呼び出すし、以前のレポート用のフックを復元します。  
  
```
void RemoveHook() throw();
```  
  
### <a name="remarks"></a>コメント  
 呼び出し[_CrtSetReportHook2](../../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md)を以前のレポート用のフックを復元します。  
  
##  <a name="sethook"></a>CDebugReportHook::SetHook  
 名前付きパイプへのデバッグ レポートの送信を開始するには、このメソッドを呼び出します。  
  
```
void SetHook() throw();
```  
  
### <a name="remarks"></a>コメント  
 呼び出し[_CrtSetReportHook2](../../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md)デバッグ レポートを経由してルーティング[CDebugReportHookProc](#cdebugreporthookproc)名前付きパイプです。 このクラスは追跡の前のレポート用のフックできるように復元するときに[RemoveHook](#removehook)が呼び出されます。  
  
##  <a name="setpipename"></a>CDebugReportHook::SetPipeName  
 コンピューターとデバッグ レポートを送信するパイプの名前を設定するには、このメソッドを呼び出します。  
  
```
BOOL SetPipeName(
    LPCSTR szMachineName = ".",
    LPCSTR szPipeName = "AtlsDbgPipe") throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `szMachineName`  
 デバッグ出力の送信先となるコンピューターの名前。  
  
 `szPipeName`  
 デバッグ出力の送信先となる名前付きパイプの名前。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、TRUE を返しますを返します。  
  
##  <a name="settimeout"></a>CDebugReportHook::SetTimeout  
 このクラスが使用可能になる名前付きパイプの待機するミリ秒単位で時間を設定するには、このメソッドを呼び出します。  
  
```
void SetTimeout(DWORD dwTimeout);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwTimeout`  
 このクラスが使用可能になる名前付きパイプの待機するミリ秒単位の時間。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../atl/reference/atl-classes.md)

