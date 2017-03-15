---
title: "CAtlExeModuleT クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CAtlExeModuleT<T>
- CAtlExeModuleT
- ATL.CAtlExeModuleT<T>
- ATL::CAtlExeModuleT
- ATL.CAtlExeModuleT
dev_langs:
- C++
helpviewer_keywords:
- CAtlExeModuleT class
ms.assetid: 82245f3d-91d4-44fa-aa86-7cc7fbd758d9
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
ms.openlocfilehash: 24ee6c4dfb13c31377bdd7d4f57a92d4f11ad4b8
ms.lasthandoff: 02/24/2017

---
# <a name="catlexemodulet-class"></a>CAtlExeModuleT クラス
このクラスは、アプリケーションのモジュールを表します。  
  
## <a name="syntax"></a>構文  
  
```
template <class T>  
class ATL_NO_VTABLE CAtlExeModuleT : public CAtlModuleT<T>
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラス`CAtlExeModuleT`します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlExeModuleT::CAtlExeModuleT](#catlexemodulet)|コンストラクターです。|  
|[CAtlExeModuleT:: ~ CAtlExeModuleT](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[する](#initializecom)|COM を初期化します。|  
|[CAtlExeModuleT::ParseCommandLine](#parsecommandline)|コマンドラインを解析し、必要な場合は、登録を実行します。|  
|[CAtlExeModuleT::PostMessageLoop](#postmessageloop)|このメソッドは、メッセージ ループの終了直後後に呼び出されます。|  
|[CAtlExeModuleT::PreMessageLoop](#premessageloop)|このメソッドは、メッセージ ループに入る前にすぐに呼び出されます。|  
|[CAtlExeModuleT::RegisterClassObjects](#registerclassobjects)|クラスのオブジェクトを登録します。|  
|[で](#revokeclassobjects)|クラス オブジェクトを削除します。|  
|[CAtlExeModuleT::Run](#run)|このメソッドは、初期化は、メッセージ ループを実行するには、EXE モジュールのコードを実行してクリーンアップします。|  
|[CAtlExeModuleT::RunMessageLoop](#runmessageloop)|このメソッドは、メッセージ ループを実行します。|  
|[CAtlExeModuleT::UninitializeCom](#uninitializecom)|COM. を非初期化します。|  
|[CAtlExeModuleT::Unlock](#unlock)|モジュールのロック カウントをデクリメントします。|  
|[CAtlExeModuleT::WinMain](#winmain)|このメソッドでは、EXE の実行に必要なコードを実装します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlExeModuleT::m_bDelayShutdown](#m_bdelayshutdown)|モジュールをシャット ダウンの遅延が存在できるかを示すフラグです。|  
|[CAtlExeModuleT::m_dwPause](#m_dwpause)|シャット ダウンする前にすべてのオブジェクトが解放されることを確認するために使用する一時停止の値です。|  
|[CAtlExeModuleT::m_dwTimeOut](#m_dwtimeout)|モジュールのアンロードを遅延させるためのタイムアウト値。|  
  
## <a name="remarks"></a>コメント  
 `CAtlExeModuleT`アプリケーション (EXE) については、モジュールを表し、終了時に、EXE を作成する、コマンドラインの処理、クラス オブジェクトの登録、メッセージ ループの実行およびクリーンアップをサポートするコードが含まれています。  
  
 このクラスは、EXE サーバーの COM オブジェクトの継続的に作成および破棄される場合は、パフォーマンスを向上させるために設計されています。 指定した期間の exe ファイルが待機する最後の COM オブジェクトが解放された後、 [CAtlExeModuleT::m_dwTimeOut](#m_dwtimeout)データ メンバーです。 この期間中にアクティビティがない場合 (つまり、COM オブジェクトは作成されません)、シャット ダウン プロセスが開始します。  
  
 [CAtlExeModuleT::m_bDelayShutdown](#m_bdelayshutdown)データ メンバーは、exe ファイルが上記で定義されたメカニズムを使用する必要があるかどうかを決定するのに使用するフラグ。 False に設定されている場合、モジュールはすぐに終了します。  
  
 ATL でのモジュールの詳細については、次を参照してください。 [ATL モジュール クラス](../../atl/atl-module-classes.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  

  
 [不要](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 `CAtlExeModuleT`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
##  <a name="a-namecatlexemoduleta--catlexemoduletcatlexemodulet"></a><a name="catlexemodulet"></a>CAtlExeModuleT::CAtlExeModuleT  
 コンストラクターです。  
  
```
CAtlExeModuleT() throw();
```  
  
### <a name="remarks"></a>コメント  
 EXE モジュールが初期化いない場合は WinMain がさらに処理することがなくすぐに戻ります。  
  
##  <a name="a-namedtora--catlexemoduletcatlexemodulet"></a><a name="dtor"></a>CAtlExeModuleT:: ~ CAtlExeModuleT  
 デストラクターです。  
  
```
~CAtlExeModuleT() throw();
```  
  
### <a name="remarks"></a>コメント  
 割り当てられているすべてのリソースを解放します。  
  
##  <a name="a-nameinitializecoma--catlexemoduletinitializecom"></a><a name="initializecom"></a>する  
 COM を初期化します。  
  
```
static HRESULT InitializeCom() throw();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、コンス トラクターから呼び出され、既定の実装とは異なる形式で COM を初期化するためにオーバーライドできます。 既定の実装を呼び出すか、 **CoInitializeEx (NULL、COINIT_MULTITHREADED)**または**CoInitialize(NULL)**プロジェクト構成によって異なります。  
  
 通常、このメソッドをオーバーライドするには、オーバーライドする必要があります[CAtlExeModuleT::UninitializeCom](#uninitializecom)します。  
  
##  <a name="a-namembdelayshutdowna--catlexemoduletmbdelayshutdown"></a><a name="m_bdelayshutdown"></a>CAtlExeModuleT::m_bDelayShutdown  
 モジュールをシャット ダウンの遅延が存在できるかを示すフラグです。  
  
```
bool m_bDelayShutdown;
```  
  
### <a name="remarks"></a>コメント  
 参照してください、 [CAtlExeModuleT 概要](../../atl/reference/catlexemodulet-class.md)詳細です。  
  
##  <a name="a-namemdwpausea--catlexemoduletmdwpause"></a><a name="m_dwpause"></a>CAtlExeModuleT::m_dwPause  
 シャット ダウンする前にすべてのオブジェクトを削除することを確認するために使用する一時停止の値です。  
  
```
DWORD m_dwPause;
```  
  
### <a name="remarks"></a>コメント  
 呼び出した後にこの値は変更[する](#initializecom)サーバーをシャット ダウンの一時停止の値として使用されるミリ秒単位の数を設定します。 既定値は、1000 ミリ秒です。  
  
##  <a name="a-namemdwtimeouta--catlexemoduletmdwtimeout"></a><a name="m_dwtimeout"></a>CAtlExeModuleT::m_dwTimeOut  
 モジュールのアンロードを遅延させるためのタイムアウト値。  
  
```
DWORD m_dwTimeOut;
```  
  
### <a name="remarks"></a>コメント  
 呼び出した後にこの値は変更[する](#initializecom)サーバーをシャット ダウンのタイムアウト値として使用されるミリ秒単位の数を定義します。 既定値は 5000 ミリ秒です。 参照してください、 [CAtlExeModuleT 概要](../../atl/reference/catlexemodulet-class.md)詳細です。  
  
##  <a name="a-nameparsecommandlinea--catlexemoduletparsecommandline"></a><a name="parsecommandline"></a>CAtlExeModuleT::ParseCommandLine  
 コマンドラインを解析し、必要な場合は、登録を実行します。  
  
```
bool ParseCommandLine(LPCTSTR lpCmdLine, HRESULT* pnRetCode) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lpCmdLine`  
 コマンド ラインは、アプリケーションに渡されます。  
  
 `pnRetCode`  
 (場所がかかりました) の場合は、登録に対応する HRESULT。  
  
### <a name="return-value"></a>戻り値  
 True の場合は、アプリケーション実行を継続する、それ以外の場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドが呼び出される[CAtlExeModuleT::WinMain](#winmain)し、コマンド ライン スイッチを処理するためにオーバーライドできます。 既定の実装**/RegServer**と**/UnRegServer**コマンドライン引数し、登録または登録解除を実行します。  
  
##  <a name="a-namepostmessageloopa--catlexemoduletpostmessageloop"></a><a name="postmessageloop"></a>CAtlExeModuleT::PostMessageLoop  
 このメソッドは、メッセージ ループの終了直後後に呼び出されます。  
  
```
HRESULT PostMessageLoop() throw();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 カスタム アプリケーションのクリーンアップを実行するには、このメソッドをオーバーライドします。 既定の実装[で](#revokeclassobjects)します。  
  
##  <a name="a-namepremessageloopa--catlexemoduletpremessageloop"></a><a name="premessageloop"></a>CAtlExeModuleT::PreMessageLoop  
 このメソッドは、メッセージ ループに入る前にすぐに呼び出されます。  
  
```
HRESULT PreMessageLoop(int nShowCmd) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nShowCmd`  
 渡された値、 `nShowCmd` WinMain 内のパラメーターです。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 アプリケーションのカスタムの初期化コードを追加するには、このメソッドをオーバーライドします。 既定の実装では、クラス オブジェクトを登録します。  
  
##  <a name="a-nameregisterclassobjectsa--catlexemoduletregisterclassobjects"></a><a name="registerclassobjects"></a>CAtlExeModuleT::RegisterClassObjects  
 その他のアプリケーションが接続できるように、クラス オブジェクトを OLE に登録します。  
  
```
HRESULT RegisterClassObjects(DWORD dwClsContext, DWORD dwFlags) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *dwClsContext*  
 クラスのオブジェクトが実行されるコンテキストを指定します。 使用可能な値は CLSCTX_INPROC_SERVER、CLSCTX_INPROC_HANDLER、または CLSCTX_LOCAL_SERVER です。  
  
 `dwFlags`  
 クラス オブジェクトへの接続の種類を決定します。 使用可能な値は REGCLS_SINGLEUSE、REGCLS_MULTIPLEUSE、または REGCLS_MULTI_SEPARATE です。  
  
### <a name="return-value"></a>戻り値  
 成功、S_FALSE を登録するクラスが存在しなかった場合、または失敗に関するエラーの hresult 値は S_OK を返します。  
  
##  <a name="a-namerevokeclassobjectsa--catlexemoduletrevokeclassobjects"></a><a name="revokeclassobjects"></a>で  
 クラスのオブジェクトを削除します。  
  
```
HRESULT RevokeClassObjects() throw();
```  
  
### <a name="return-value"></a>戻り値  
 成功、S_FALSE を登録するクラスが存在しなかった場合、または失敗に関するエラーの hresult 値は S_OK を返します。  
  
##  <a name="a-nameruna--catlexemoduletrun"></a><a name="run"></a>CAtlExeModuleT::Run  
 このメソッドは、初期化は、メッセージ ループを実行するには、EXE モジュールのコードを実行してクリーンアップします。  
  
```
HRESULT Run(int nShowCmd = SW_HIDE) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nShowCmd`  
 ウィンドウの表示方法を指定します。 このパラメーターには、「値のいずれかを指定できます、 [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559)セクションです。 既定値は SW_HIDE です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドをオーバーライドできます。 ただし、実際にする方法がオーバーライド[CAtlExeModuleT::PreMessageLoop](#premessageloop)、 [CAtlExeModuleT::RunMessageLoop](#runmessageloop)、または[CAtlExeModuleT::PostMessageLoop](#postmessageloop)代わりにします。  
  
##  <a name="a-namerunmessageloopa--catlexemoduletrunmessageloop"></a><a name="runmessageloop"></a>CAtlExeModuleT::RunMessageLoop  
 このメソッドは、メッセージ ループを実行します。  
  
```
void RunMessageLoop() throw();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドをオーバーライドして、メッセージ ループの動作を変更します。  
  
##  <a name="a-nameuninitializecoma--catlexemoduletuninitializecom"></a><a name="uninitializecom"></a>CAtlExeModuleT::UninitializeCom  
 COM. を非初期化します。  
  
```
static void UninitializeCom() throw();
```  
  
### <a name="remarks"></a>コメント  
 既定ではこのメソッドを呼び出すだけ[CoUninitialize](http://msdn.microsoft.com/library/windows/desktop/ms688715)され、そのデストラクターから呼び出されます。 オーバーライドする場合は、このメソッドをオーバーライド[する](#initializecom)です。  
  
##  <a name="a-nameunlocka--catlexemoduletunlock"></a><a name="unlock"></a>CAtlExeModuleT::Unlock  
 モジュールのロック カウントをデクリメントします。  
  
```
LONG Unlock() throw();
```  
  
### <a name="return-value"></a>戻り値  
 診断に役に立たないかテスト可能性のある値を返します。  
  
##  <a name="a-namewinmaina--catlexemoduletwinmain"></a><a name="winmain"></a>CAtlExeModuleT::WinMain  
 このメソッドでは、EXE の実行に必要なコードを実装します。  
  
```
int WinMain(int nShowCmd) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nShowCmd`  
 ウィンドウの表示方法を指定します。 このパラメーターには、「値のいずれかを指定できます、 [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559)セクションです。  
  
### <a name="return-value"></a>戻り値  
 実行可能ファイルの戻り値を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドをオーバーライドできます。 オーバーライドする場合は、 [CAtlExeModuleT::PreMessageLoop](#premessageloop)、 [CAtlExeModuleT::PostMessageLoop](#postmessageloop)、または[CAtlExeModuleT::RunMessageLoop](#runmessageloop)十分な柔軟性を提供しませんをオーバーライドすることは、`WinMain`このメソッドを使用して機能します。  
  
## <a name="see-also"></a>関連項目  
 [ATLDuck サンプル](../../visual-cpp-samples.md)   
 [CAtlModuleT クラス](../../atl/reference/catlmodulet-class.md)   
 [CAtlDllModuleT クラス](../../atl/reference/catldllmodulet-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

