---
title: "CWinAppEx クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWinAppEx
dev_langs:
- C++
helpviewer_keywords:
- CWinAppEx class
ms.assetid: a3d3e053-3e22-463f-9444-c73abb1bb9d7
caps.latest.revision: 37
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
ms.openlocfilehash: 6931f1e794116882722e402c9cb95acec1ebdfd5
ms.lasthandoff: 02/24/2017

---
# <a name="cwinappex-class"></a>CWinAppEx クラス
`CWinAppEx`アプリケーション状態の処理、レジストリに状態を保存、レジストリから状態を読み込みます、アプリケーション マネージャーの初期化、および同じアプリケーション マネージャーへのリンクを提供します。  
  
## <a name="syntax"></a>構文  
  
```  
class CWinAppEx : public CWinApp  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CWinAppEx::CWinAppEx](#cwinappex)|`CWinAppEx` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CWinAppEx::CleanState](#cleanstate)|Windows レジストリからアプリケーションに関する情報を削除します。|  
|[CWinAppEx::EnableLoadWindowPlacement](#enableloadwindowplacement)|アプリケーションは、レジストリからメイン フレーム ウィンドウの場所と初期サイズを読み込むかどうかを指定します。|  
|[CWinAppEx::EnableTearOffMenus](#enabletearoffmenus)|アプリケーションのメニュー ティアオフ有効です。|  
|[CWinAppEx::EnableUserTools](#enableusertools)|アプリケーションでカスタム メニュー コマンドを作成することができます。|  
|[CWinAppEx::ExitInstance](#exitinstance)|内から、フレームワークによって呼び出され、`Run`アプリケーションのこのインスタンスを終了するメンバー関数。 (上書き[し](../../mfc/reference/cwinapp-class.md#exitinstance))。|  
|[CWinAppEx::GetBinary](#getbinary)|指定されたレジストリ値に関連付けられているバイナリ データを読み取ります。|  
|[CWinAppEx::GetContextMenuManager](#getcontextmenumanager)|グローバルにポインターを返す[CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md)オブジェクトです。|  
|[CWinAppEx::GetDataVersion](#getdataversion)||  
|[CWinAppEx::GetDataVersionMajor](#getdataversionmajor)|Windows レジストリに保存されているアプリケーションの主要なバージョンを返します。|  
|[CWinAppEx::GetDataVersionMinor](#getdataversionminor)|Windows レジストリに保存されているアプリケーションのマイナー バージョンを返します。|  
|[CWinAppEx::GetInt](#getint)|レジストリから指定した値に関連付けられている数値のデータを読み取ります。|  
|[CWinAppEx::GetKeyboardManager](#getkeyboardmanager)|グローバルにポインターを返す[CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md)オブジェクトです。|  
|[CWinAppEx::GetMouseManager](#getmousemanager)|グローバルにポインターを返す[CMouseManager](../../mfc/reference/cmousemanager-class.md)オブジェクトです。|  
|[CWinAppEx::GetObject](#getobject)|読み取り`CObject`-レジストリから指定した値に関連付けられているデータを派生します。|  
|[CWinAppEx::GetRegSectionPath](#getregsectionpath)|レジストリ キーのパスを表す文字列を返します。 このパスは、アプリケーション パスで指定された相対パスを連結します。|  
|[CWinAppEx::GetRegistryBase](#getregistrybase)|アプリケーションのレジストリ パスを返します。|  
|[CWinAppEx::GetSectionBinary](#getsectionbinary)|指定したキーとレジストリからの値に関連付けられているバイナリ データを読み取ります。|  
|[CWinAppEx::GetSectionInt](#getsectionint)|指定したキーと値に関連付けられているレジストリから数値データを読み込みます。|  
|[CWinAppEx::GetSectionObject](#getsectionobject)|読み取り`CObject`指定したキーとレジストリからの値に関連付けられているデータ。|  
|[CWinAppEx::GetSectionString](#getsectionstring)|指定したキーとレジストリからの値に関連付けられている文字列データを読み取ります。|  
|[CWinAppEx::GetShellManager](#getshellmanager)|グローバルにポインターを返す[CShellManager](../../mfc/reference/cshellmanager-class.md)オブジェクトです。|  
|[CWinAppEx::GetString](#getstring)|レジストリから指定した値に関連付けられている文字列データを読み取ります。|  
|[CWinAppEx::GetTooltipManager](#gettooltipmanager)|グローバルにポインターを返す[CTooltipManager](../../mfc/reference/ctooltipmanager-class.md)オブジェクトです。|  
|[CWinAppEx::GetUserToolsManager](#getusertoolsmanager)|グローバルにポインターを返す[CUserToolsManager](../../mfc/reference/cusertoolsmanager-class.md)オブジェクトです。|  
|[CWinAppEx::InitContextMenuManager](#initcontextmenumanager)|初期化、`CContextMenuManager`オブジェクトです。|  
|[CWinAppEx::InitKeyboardManager](#initkeyboardmanager)|初期化、`CKeyboardManager`オブジェクトです。|  
|[CWinAppEx::InitMouseManager](#initmousemanager)|初期化、`CMouseManager`オブジェクトです。|  
|[CWinAppEx::InitShellManager](#initshellmanager)|初期化、`CShellManager`クラス|  
|[CWinAppEx::InitTooltipManager](#inittooltipmanager)|初期化、`CTooltipManager`クラスです。|  
|[CWinAppEx::IsResourceSmartUpdate](#isresourcesmartupdate)||  
|[CWinAppEx::IsStateExists](#isstateexists)|指定したキーがレジストリにするかどうかを示します。|  
|[CWinAppEx::LoadState](#loadstate)|レジストリからアプリケーションの状態を読み込みます。|  
|[CWinAppEx::OnAppContextHelp](#onappcontexthelp)|ユーザーのコンテキスト ヘルプを要求時にフレームワークによって呼び出さ、**カスタマイズ** ダイアログ ボックス。|  
|[CWinAppEx::OnViewDoubleClick](#onviewdoubleclick)|ユーザーがアプリケーションの任意の場所をダブルクリックしたときに、ユーザー定義のコマンドを呼び出します。|  
|[CWinAppEx::OnWorkspaceIdle](#onworkspaceidle)||  
|[CWinAppEx::SaveState](#savestate)|アプリケーション フレームワークの状態を Windows レジストリに書き込みます。|  
|[CWinAppEx::SetRegistryBase](#setregistrybase)|既定のレジストリ キーのパスを設定します。 このキーは、後続のレジストリのすべての呼び出しをルートとして使用されます。|  
|[CWinAppEx::ShowPopupMenu](#showpopupmenu)|ポップアップ メニューを表示します。|  
|[CWinAppEx::WriteBinary](#writebinary)|指定されたレジストリ値をバイナリ データを書き込みます。|  
|[CWinAppEx::WriteInt](#writeint)|指定されたレジストリ値を数値データを書き込みます。|  
|[CWinAppEx::WriteObject](#writeobject)|派生したデータを書き込む、 [CObject クラス](../../mfc/reference/cobject-class.md)指定されたレジストリ値にします。|  
|[CWinAppEx::WriteSectionBinary](#writesectionbinary)|指定されたレジストリ キーの値をバイナリ データを書き込みます。|  
|[CWinAppEx::WriteSectionInt](#writesectionint)|指定されたレジストリ キーの値を数値データを書き込みます。|  
|[CWinAppEx::WriteSectionObject](#writesectionobject)|派生したデータを書き込み、`CObject`指定されたレジストリ キーの値にクラスです。|  
|[CWinAppEx::WriteSectionString](#writesectionstring)|指定されたレジストリ キーの値を文字列データを書き込みます。|  
|[CWinAppEx::WriteString](#writestring)|指定されたレジストリ値を文字列データを書き込みます。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CWinAppEx::LoadCustomState](#loadcustomstate)|アプリケーションの状態が読み込まれたときに、フレームワークによって呼び出されます。|  
|[CWinAppEx::LoadWindowPlacement](#loadwindowplacement)|サイズと、アプリケーションの場所をレジストリから読み込むときに、フレームワークによって呼び出されます。 読み込まれたデータには、アプリケーションが最後に閉じられた時点でのメイン フレームの場所とサイズが含まれています。|  
|[CWinAppEx::OnClosingMainFrame](#onclosingmainframe)|メイン フレーム ウィンドウを処理するときに、フレームワークによって呼び出されます`WM_CLOSE`します。|  
|[CWinAppEx::PreLoadState](#preloadstate)|直前に、フレームワークによって呼び出され、アプリケーションの状態が読み込まれます。|  
|[CWinAppEx::PreSaveState](#presavestate)|直前に、フレームワークによって呼び出され、アプリケーションの状態が保存されます。|  
|[CWinAppEx::ReloadWindowPlacement](#reloadwindowplacement)|レジストリから指定されたウィンドウの場所とサイズを再読み込み|  
|[CWinAppEx::SaveCustomState](#savecustomstate)|アプリケーションの状態をレジストリに保存した後に、フレームワークによって呼び出されます。|  
|[CWinAppEx::StoreWindowPlacement](#storewindowplacement)|メイン フレームの場所とサイズをレジストリに書き込むために、フレームワークによって呼び出されます。|  
  
### <a name="data-members"></a>データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CWinAppEx::m_bForceImageReset](#m_bforceimagereset)|ツールバーを含むフレーム ウィンドウが読み込まれるときに、フレームワークがすべてのツール バー イメージをリセットするかどうかを指定します。|  
  
## <a name="remarks"></a>コメント  
 MFC フレームワークによって提供される機能のほとんどは、`CWinAppEx`クラスです。 組み込むことができます、`CWinAppEx`を&2; つの方法のいずれかでアプリケーションにクラス。  
  
-   構築、`CWinAppEx`メイン スレッドでのクラスです。  
  
-   アプリケーションのメイン クラスから派生させます`CWinAppEx`します。  
  
 組み込む`CWinAppEx`アプリケーションには、アプリケーション マネージャーのいずれかを初期化できます。 アプリケーション マネージャーを使用する前に、適切な初期化メソッドを呼び出して初期化する必要があります。 特定のマネージャーへのポインターを取得するには、関連付けられている get メソッドを呼び出します。 `CWinAppEx`クラスを次のアプリケーション管理者を管理する: [CMouseManager クラス](../../mfc/reference/cmousemanager-class.md)、 [CContextMenuManager クラス](../../mfc/reference/ccontextmenumanager-class.md)、 [CKeyboardManager クラス](../../mfc/reference/ckeyboardmanager-class.md)、 [CUserToolsManager クラス](../../mfc/reference/cusertoolsmanager-class.md)、および[CMenuTearOffManager クラス](../../mfc/reference/cmenutearoffmanager-class.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWinThread](../../mfc/reference/cwinthread-class.md)  
  
 [CWinApp](../../mfc/reference/cwinapp-class.md)  
  
 [CWinAppEx](../../mfc/reference/cwinappex-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwinappex.h  
  
##  <a name="a-namecleanstatea--cwinappexcleanstate"></a><a name="cleanstate"></a>CWinAppEx::CleanState  
 Windows レジストリからアプリケーションに関するすべての情報を削除します。  
  
```  
virtual BOOL CleanState(LPCTSTR lpszSectionName=NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszSectionName`  
 レジストリ キーのパスを含む文字列です。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、レジストリの特定のセクションからアプリケーション データを消去します。 パラメーターを使用してクリアするセクションを指定する`lpszSectionName`です。 場合`lpszSectionName`は`NULL`、このメソッドに格納されている既定のレジストリ パスを使用して、`CWinAppEx`オブジェクトです。 既定のレジストリ パスを取得する[CWinAppEx::GetRegistryBase](#getregistrybase)します。  
  
##  <a name="a-namecwinappexa--cwinappexcwinappex"></a><a name="cwinappex"></a>CWinAppEx::CWinAppEx  
 `CWinAppEx` オブジェクトを構築します。  
  
```  
CWinAppEx(BOOL bResourceSmartUpdate = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bResourceSmartUpdate`  
 Workspace オブジェクトが検出され、リソースの更新を処理するかどうかを示すブール値パラメーターです。  
  
### <a name="remarks"></a>コメント  
 `CWinAppEx`クラスは、初期化メソッドが、保存と読み込みをレジストリに情報をアプリケーションの機能を提供し、アプリケーションのグローバル設定を制御します。 などのグローバル管理者を使用することもできます、 [CKeyboardManager クラス](../../mfc/reference/ckeyboardmanager-class.md)と[CUserToolsManager クラス](../../mfc/reference/cusertoolsmanager-class.md)します。 各アプリケーションが&1; つだけを持つ、`CWinAppEx`クラスです。  
  
##  <a name="a-nameenableloadwindowplacementa--cwinappexenableloadwindowplacement"></a><a name="enableloadwindowplacement"></a>CWinAppEx::EnableLoadWindowPlacement  
 アプリケーションは、レジストリからメイン フレーム ウィンドウの場所と初期サイズを読み込むかどうかを指定します。  
  
```  
void EnableLoadWindowPlacement(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 アプリケーションがレジストリから、メイン フレーム ウィンドウの場所と初期サイズをロードするかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
 既定では、メインフレームの場所とサイズが、その他のアプリケーション設定とレジストリから読み込まれます。 これは、現象が発生[CWinAppEx::LoadState](#loadstate)します。 レジストリから最初のウィンドウの場所をロードしたくない場合に、このメソッドを呼び出す`bEnable`設定`false`します。  
  
##  <a name="a-nameenabletearoffmenusa--cwinappexenabletearoffmenus"></a><a name="enabletearoffmenus"></a>CWinAppEx::EnableTearOffMenus  
 作成して初期化、 [CMenuTearOffManager](../../mfc/reference/cmenutearoffmanager-class.md)オブジェクトです。  
  
```  
BOOL EnableTearOffMenus(
    LPCTSTR lpszRegEntry,  
    const UINT uiCmdFirst,  
    const UINT uiCmdLast);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszRegEntry`  
 レジストリ キーのパスを含む文字列です。 アプリケーションでは、このレジストリ キーを使用して、ティアオフ メニューの情報を格納します。  
  
 [入力] `uiCmdFirst`  
 最初のティアオフ メニュー id。  
  
 [入力] `uiCmdLast`  
 最後にティアオフ メニュー id。  
  
### <a name="return-value"></a>戻り値  
 `True`場合、`CMenuTearOffManager`が作成され、初期化に成功しました。`false`エラーが発生した場合や、`CMenuTearOffManager`は既に存在します。  
  
### <a name="remarks"></a>コメント  
 アプリケーションでは、ティアオフ メニューを有効にするのにには、この関数を使用します。 この関数を呼び出す必要があります`InitInstance`します。  
  
##  <a name="a-nameenableusertoolsa--cwinappexenableusertools"></a><a name="enableusertools"></a>CWinAppEx::EnableUserTools  
 アプリケーションでキーボード操作を減らすカスタム メニュー コマンドを作成することができます。 このメソッドは、作成、 [CUserToolsManager](../../mfc/reference/cusertoolsmanager-class.md)オブジェクトです。  
  
```  
BOOL EnableUserTools(
    const UINT uiCmdToolsDummy,  
    const UINT uiCmdFirst,  
    const UINT uiCmdLast,  
    CRuntimeClass* pToolRTC = RUNTIME_CLASS(CUserTool),  
    UINT uArgMenuID = 0,  
    UINT uInitDirMenuID = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiCmdToolsDummy`  
 フレームワークがユーザーの [ツール] メニューのコマンド ID のプレース ホルダーとして使用する符号なし整数。  
  
 [入力] `uiCmdFirst`  
 最初のユーザー ツールのコマンドのコマンド ID。  
  
 [入力] `uiCmdLast`  
 最後のユーザー ツールのコマンドのコマンド ID。  
  
 [入力] `pToolRTC`  
 クラスの A、`CUserToolsManager`オブジェクトを使用して新しいユーザー ツールを作成します。  
  
 [入力] `uArgMenuID`  
 引数のメニューの id。  
  
 [入力] `uInitDirMenuID`  
 初期ツール ディレクトリのメニューの ID。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`メソッドを作成して初期化する場合、`CUserToolsManager`オブジェクトです。`FALSE`メソッドが失敗するか、`CUserToolsManager`オブジェクトが既に存在します。  
  
### <a name="remarks"></a>コメント  
 ユーザー定義のツールを有効にすると、フレームワークは自動的にカスタマイズするときに拡張可能な動的メニューをサポートします。 フレームワークは、外部コマンドを使用して、新しい各項目を関連付けます。 フレームワークがから、適切な項目を選択すると、これらのコマンドを呼び出す、**ツール**メニュー。  
  
 ユーザーは、新しい項目を追加するたびに、フレームワークは、新しいオブジェクトを作成します。 新しいオブジェクトのクラス型が定義されている`pToolRTC`します。 `pToolRTC`クラス型の派生元は、 [CUserTool クラス](../../mfc/reference/cusertool-class.md)します。  
  
 ユーザー ツールと、アプリケーションに組み込む方法の詳細については、次を参照してください。[ユーザー定義のツール](../../mfc/user-defined-tools.md)します。  
  
##  <a name="a-nameexitinstancea--cwinappexexitinstance"></a><a name="exitinstance"></a>CWinAppEx::ExitInstance  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int ExitInstance();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namegetbinarya--cwinappexgetbinary"></a><a name="getbinary"></a>CWinAppEx::GetBinary  
 指定されたレジストリ キーからバイナリ データを読み取ります。  
  
```  
BOOL GetBinary(
    LPCTSTR lpszEntry,  
    LPBYTE* ppData,  
    UINT* pBytes);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszEntry`  
 レジストリ キーの名前を表す文字列。  
  
 [出力] `ppData`  
 メソッドがバイナリ データを格納するバッファーへのポインター。  
  
 [出力] `pBytes`  
 読み取ったバイト数を記述するメソッドを使用する符号なし整数へのポインター。  
  
### <a name="return-value"></a>戻り値  
 `True`成功した場合`false`それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、レジストリに書き込まれたバイナリ データを読み込みます。 レジストリにデータを書き込む方法を使用[CWinAppEx::WriteBinary](#writebinary)と[CWinAppEx::WriteSectionBinary](#writesectionbinary)します。  
  
 `lpszEntry`パラメーターは、アプリケーションの既定のレジストリ キーの下にあるレジストリ エントリの名前。 を取得または既定のレジストリ キーを設定するには、メソッドを使用して[CWinAppEx::GetRegistryBase](#getregistrybase)と[CWinAppEx::SetRegistryBase](#setregistrybase)それぞれします。  
  
##  <a name="a-namegetcontextmenumanagera--cwinappexgetcontextmenumanager"></a><a name="getcontextmenumanager"></a>CWinAppEx::GetContextMenuManager  
 グローバルにポインターを返す[CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md)オブジェクトです。  
  
```  
CContextMenuManager* GetContextMenuManager();
```  
  
### <a name="return-value"></a>戻り値  
 グローバルへのポインター`CContextMenuManager`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 この関数を呼び出す CContextMenuManager オブジェクトが初期化されていない場合[CWinAppEx::InitContextMenuManager](#initcontextmenumanager)へのポインターを返す前にします。  
  
##  <a name="a-namegetdataversiona--cwinappexgetdataversion"></a><a name="getdataversion"></a>CWinAppEx::GetDataVersion  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
int GetDataVersion() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namegetdataversionmajora--cwinappexgetdataversionmajor"></a><a name="getdataversionmajor"></a>CWinAppEx::GetDataVersionMajor  
 呼び出すときに、Windows レジストリに保存されているアプリケーションのメジャー バージョンを返します[CWinAppEx::SaveState](#savestate)します。  
  
```  
int GetDataVersionMajor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 メジャー バージョン番号を含む整数値。  
  
##  <a name="a-namegetdataversionminora--cwinappexgetdataversionminor"></a><a name="getdataversionminor"></a>CWinAppEx::GetDataVersionMinor  
 呼び出すときに、Windows レジストリに保存されているアプリケーションのマイナー バージョンを返す[CWinAppEx::SaveState](#savestate)します。  
  
```  
int GetDataVersionMinor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 マイナー バージョン番号を含む整数値。  
  
##  <a name="a-namegetinta--cwinappexgetint"></a><a name="getint"></a>CWinAppEx::GetInt  
 指定されたレジストリ キーから整数型のデータを読み取ります。  
  
```  
int GetInt(
    LPCTSTR lpszEntry,  
    int nDefault = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszEntry`  
 レジストリ エントリの名前を表す文字列。  
  
 [入力] `nDefault`  
 指定したレジストリ エントリが存在しないかどうか、メソッドで返される既定値です。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は、レジストリ データそれ以外の場合`nDefault`します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、レジストリから整数型のデータを読み込みます。 示されたレジストリ キーに関連付けられた整数データがないかどうか`lpszEntry`、このメソッドが戻る`nDefault`します。 レジストリにデータを書き込むには、メソッドを使用[CWinAppEx::WriteSectionInt](#writesectionint)と[CWinAppEx::WriteInt](#writeint)します。  
  
 `lpszEntry`パラメーターは、アプリケーションの既定のレジストリ キーの下にあるレジストリ エントリの名前。 を取得または既定のレジストリ キーを設定するには、メソッドを使用して[CWinAppEx::GetRegistryBase](#getregistrybase)と[CWinAppEx::SetRegistryBase](#setregistrybase)それぞれします。  
  
##  <a name="a-namegetkeyboardmanagera--cwinappexgetkeyboardmanager"></a><a name="getkeyboardmanager"></a>CWinAppEx::GetKeyboardManager  
 グローバルにポインターを返す[CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md)オブジェクトです。  
  
```  
CKeyboardManager* GetKeyboardManager();
```  
  
### <a name="return-value"></a>戻り値  
 グローバルへのポインター`CKeyboardManager`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 キーボード マネージャーが初期化されていない場合はこの関数呼び出し[CWinAppEx::InitKeyboardManager](#initkeyboardmanager)へのポインターを返す前にします。  
  
##  <a name="a-namegetmousemanagera--cwinappexgetmousemanager"></a><a name="getmousemanager"></a>CWinAppEx::GetMouseManager  
 グローバルにポインターを返す[CMouseManager](../../mfc/reference/cmousemanager-class.md)オブジェクトです。  
  
```  
CMouseManager* GetMouseManager();
```  
  
### <a name="return-value"></a>戻り値  
 グローバルへのポインター`CMouseManager`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 この関数を呼び出す場合は、マウス マネージャーが初期化されていない、および[CWinAppEx::InitMouseManager](#initmousemanager)へのポインターを返す前にします。  
  
##  <a name="a-namegetobjecta--cwinappexgetobject"></a><a name="getobject"></a>CWinAppEx::GetObject  
 読み取り[CObject](../../mfc/reference/cobject-class.md)レジストリから - dervied データ。  
  
```  
BOOL GetObject(
    LPCTSTR lpszEntry,  
    CObject& obj);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszEntry`  
 レジストリ エントリの相対パスを含む文字列です。  
  
 [出力] `obj`  
 参照、`CObject`です。 メソッドでは、この参照を使用して、レジストリ データを格納します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドから派生したレジストリからデータを読み取ります`CObject`します。 書き込む`CObject`をレジストリにデータを使用するか[CWinAppEx::WriteObject](#writeobject)または[CWinAppEx::WriteSectionObject](#writesectionobject)します。  
  
 `lpszEntry`パラメーターは、アプリケーションの既定のレジストリ キーの下にあるレジストリ エントリの名前。 を取得または既定のレジストリ キーを設定するには、メソッドを使用して[CWinAppEx::GetRegistryBase](#getregistrybase)と[CWinAppEx::SetRegistryBase](#setregistrybase)それぞれします。  
  
##  <a name="a-namegetregistrybasea--cwinappexgetregistrybase"></a><a name="getregistrybase"></a>CWinAppEx::GetRegistryBase  
 アプリケーションの既定のレジストリ パスを取得します。  
  
```  
LPCTSTR GetRegistryBase();
```  
  
### <a name="return-value"></a>戻り値  
 既定のレジストリの場所のパスを含む文字列です。  
  
### <a name="remarks"></a>コメント  
 すべてのメソッド、 [CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)既定の場所にレジストリの開始にアクセスします。 このメソッドを使用すると、既定のレジストリの場所のパスを取得できます。 使用[CWinAppEx::SetRegistryBase](#setregistrybase)既定レジストリの場所を変更します。  
  
##  <a name="a-namegetregsectionpatha--cwinappexgetregsectionpath"></a><a name="getregsectionpath"></a>CWinAppEx::GetRegSectionPath  
 作成して、レジストリ キーの絶対パスを返します。  
  
```  
CString GetRegSectionPath(LPCTSTR szSectionAdd = _T(""));
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `szSectionAdd`  
 レジストリ キーの相対パスを含む文字列です。  
  
### <a name="return-value"></a>戻り値  
 A`CString`レジストリ キーの絶対パスを格納しています。  
  
### <a name="remarks"></a>コメント  
 このメソッドでは、レジストリ キーの絶対パスを定義での相対パスを追加することによって`szSectionAdd`アプリケーションの既定のレジストリの場所。 既定のレジストリ キーを取得するには、このメソッドを使用[CWinAppEx::GetRegistryBase](#getregistrybase)します。  
  
##  <a name="a-namegetsectionbinarya--cwinappexgetsectionbinary"></a><a name="getsectionbinary"></a>CWinAppEx::GetSectionBinary  
 レジストリからバイナリ データを読み取ります。  
  
```  
BOOL GetSectionBinary(
    LPCTSTR lpszSubSection,  
    LPCTSTR lpszEntry,  
    LPBYTE* ppData,  
    UINT* pBytes);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszSubSection`  
 レジストリ キーの相対パスを含む文字列です。  
  
 [入力] `lpszEntry`  
 読み取る値を含む文字列です。  
  
 [出力] `ppData`  
 メソッドがデータを格納するバッファーへのポインター。  
  
 [出力] `pBytes`  
 符号なし整数へのポインター。 メソッドのサイズが書き込む`ppData`このパラメーターにします。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は `True`。それ以外の場合は `false`。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、メソッドを使用して、レジストリに書き込まれるバイナリ データを読み取ります[CWinAppEx::WriteBinary](#writebinary)と[CWinAppEx::WriteSectionBinary](#writesectionbinary)します。  
  
 `lpszSubSection`パラメーターは、レジストリ エントリの絶対パスではありません。 相対パス、アプリケーションの既定のレジストリ キーの末尾に追加することをお勧めします。 を取得または既定のレジストリ キーを設定するには、メソッドを使用して[CWinAppEx::GetRegistryBase](#getregistrybase)と[CWinAppEx::SetRegistryBase](#setregistrybase)それぞれします。  
  
##  <a name="a-namegetsectioninta--cwinappexgetsectionint"></a><a name="getsectionint"></a>CWinAppEx::GetSectionInt  
 レジストリから整数型のデータを読み取ります。  
  
```  
int GetSectionInt(
    LPCTSTR lpszSubSection,  
    LPCTSTR lpszEntry,  
    int nDefault = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszSubSection`  
 レジストリ キーの相対パスを含む文字列です。  
  
 [入力] `lpszEntry`  
 読み取る値を含む文字列です。  
  
 [入力] `nDefault`  
 指定した値が存在しないかどうかに返される既定値です。  
  
### <a name="return-value"></a>戻り値  
 指定されたレジストリの値で格納されている整数データ`nDefault`データが存在しない場合。  
  
### <a name="remarks"></a>コメント  
 メソッドを使用して[CWinAppEx::WriteInt](#writeint)と[CWinAppEx::WriteSectionInt](#writesectionint)に整数型のデータをレジストリに書き込めません。  
  
 `lpszSubSection`パラメーターは、レジストリ エントリの絶対パスではありません。 相対パスをアプリケーションの既定のレジストリ キーの末尾に追加することをお勧めします。 を取得または既定のレジストリ キーを設定するには、メソッドを使用して[CWinAppEx::GetRegistryBase](#getregistrybase)と[CWinAppEx::SetRegistryBase](#setregistrybase)それぞれします。  
  
##  <a name="a-namegetsectionobjecta--cwinappexgetsectionobject"></a><a name="getsectionobject"></a>CWinAppEx::GetSectionObject  
 読み取り[CObject](../../mfc/reference/cobject-class.md)レジストリからレジストリ データ。  
  
```  
BOOL GetSectionObject(
    LPCTSTR lpszSubSection,  
    LPCTSTR lpszEntry,  
    CObject& obj);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszSubSection`  
 レジストリ キーの相対パスを含む文字列です。  
  
 [入力] `lpszEntry`  
 読み取る値を含む文字列です。  
  
 [出力] `obj`  
 参照、`CObject`です。 メソッドがこれを使用して`CObject`レジストリ データを格納します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、レジストリからデータを読み取ります。 データの読み取りが`CObject`データ、またはデータから派生するクラスを`CObject`します。 書き込む`CObject`をレジストリにデータを使用するか[CWinAppEx::WriteObject](#writeobject)または[CWinAppEx::WriteSectionObject](#writesectionobject)します。  
  
 `lpszSubSection`パラメーターは、レジストリ エントリの絶対パスではありません。 相対パス、アプリケーションの既定のレジストリ キーの末尾に追加することをお勧めします。 を取得または既定のレジストリ キーを設定するには、メソッドを使用して[CWinAppEx::GetRegistryBase](#getregistrybase)と[CWinAppEx::SetRegistryBase](#setregistrybase)それぞれします。  
  
##  <a name="a-namegetsectionstringa--cwinappexgetsectionstring"></a><a name="getsectionstring"></a>CWinAppEx::GetSectionString  
 文字列のレジストリからデータを読み取ります。  
  
```  
CString GetSectionString(
    LPCTSTR lpszSubSection,  
    LPCTSTR lpszEntry,  
    LPCTSTR lpszDefault = _T(""));
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszSubSection`  
 レジストリ キーの相対パスを含む文字列です。  
  
 [入力] `lpszEntry`  
 読み取る値を含む文字列です。  
  
 [入力] `lpszDefault`  
 指定した値が存在しないかどうかに返される既定値です。  
  
### <a name="return-value"></a>戻り値  
 データが存在する場合は、指定されたレジストリ値に格納されている文字列データそれ以外の場合`lpszDefault`します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、レジストリに書き込まれた文字列データを読み込みます。 使用[CWinAppEx::WriteString](#writestring)と[CWinAppEx::WriteSectionString](#writesectionstring)に文字列データをレジストリに書き込めません。  
  
 `lpszSubSection`パラメーターは、レジストリ エントリの絶対パスではありません。 相対パス、アプリケーションの既定のレジストリ キーの末尾に追加することをお勧めします。 を取得または既定のレジストリ キーを設定するには、メソッドを使用して[CWinAppEx::GetRegistryBase](#getregistrybase)と[CWinAppEx::SetRegistryBase](#setregistrybase)それぞれします。  
  
##  <a name="a-namegetshellmanagera--cwinappexgetshellmanager"></a><a name="getshellmanager"></a>CWinAppEx::GetShellManager  
 グローバルにポインターを返す[CShellManager](../../mfc/reference/cshellmanager-class.md)オブジェクトです。  
  
```  
CShellManager* GetShellManager();
```  
  
### <a name="return-value"></a>戻り値  
 グローバルへのポインター`CShellManager`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 場合、`CShellManager`オブジェクトが初期化されていませんが、この関数は[CWinAppEx::InitShellManager](#initshellmanager)へのポインターを返す前にします。  
  
##  <a name="a-namegetstringa--cwinappexgetstring"></a><a name="getstring"></a>CWinAppEx::GetString  
 文字列の指定されたレジストリ キーからデータを読み取ります。  
  
```  
CString GetString(
    LPCTSTR lpszEntry,  
    LPCTSTR lpzDefault= _T(""));
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszEntry`  
 レジストリ キーの名前を表す文字列  
  
 [入力] `lpzDefault`  
 指定したレジストリ エントリが存在しないかどうか、メソッドで返される既定値です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は、レジストリに格納された文字列データ`lpszDefault`それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、レジストリに書き込まれた文字列データを読み込みます。 レジストリにデータを書き込むには、メソッドを使用[CWinAppEx::WriteString](#writestring)または[CWinAppEx::WriteSectionString](#writesectionstring)します。  
  
 `lpszEntry`パラメーターは、アプリケーションの既定のレジストリ キーの下にあるレジストリ エントリの名前。 を取得または既定のレジストリ キーを設定するには、メソッドを使用して[CWinAppEx::GetRegistryBase](#getregistrybase)と[CWinAppEx::SetRegistryBase](#setregistrybase)それぞれします。  
  
##  <a name="a-namegettooltipmanagera--cwinappexgettooltipmanager"></a><a name="gettooltipmanager"></a>CWinAppEx::GetTooltipManager  
 グローバルにポインターを返す[CTooltipManager](../../mfc/reference/ctooltipmanager-class.md)オブジェクトです。  
  
```  
CTooltipManager* GetTooltipManager();
```  
  
### <a name="return-value"></a>戻り値  
 グローバルへのポインター`CTooltipManager`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 場合、`CTooltipManager`オブジェクトが初期化されていませんが、この関数は[CWinAppEx::InitTooltipManager](#inittooltipmanager)へのポインターを返す前にします。  
  
##  <a name="a-namegetusertoolsmanagera--cwinappexgetusertoolsmanager"></a><a name="getusertoolsmanager"></a>CWinAppEx::GetUserToolsManager  
 グローバルにポインターを返す[CUserToolsManager](../../mfc/reference/cusertoolsmanager-class.md)オブジェクトです。  
  
```  
CUserToolsManager* GetUserToolsManager();
```  
  
### <a name="return-value"></a>戻り値  
 グローバルへのポインター`CUserToolsManager`オブジェクトです。`NULL`アプリケーションのユーザー ツールの管理が有効でない場合。  
  
### <a name="remarks"></a>コメント  
 ポインターを取得する前に、`CUserToolsManager`オブジェクトを呼び出すことによって、マネージャを初期化する必要があります[CWinAppEx::EnableUserTools](#enableusertools)します。  
  
##  <a name="a-nameinitcontextmenumanagera--cwinappexinitcontextmenumanager"></a><a name="initcontextmenumanager"></a>CWinAppEx::InitContextMenuManager  
 初期化、 [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md)オブジェクトです。  
  
```  
BOOL InitContextMenuManager();
```  
  
### <a name="return-value"></a>戻り値  
 メソッドは、CContextMenuManager オブジェクトを作成する場合は 0 以外。場合は 0、`CContextMenuManager`オブジェクトが既に存在します。  
  
### <a name="remarks"></a>コメント  
 呼び出した場合[CWinAppEx::GetContextMenuManager](#getcontextmenumanager)、そのメソッドの既定の実装を呼び出す`InitContextMenuManager`します。  
  
 呼び出すし、アプリケーションで既にがコンテキスト メニュー マネージャー `InitContextMenuManager`、アプリケーションが、 [ASSERT](http://msdn.microsoft.com/library/1e70902d-d58c-4e7b-9f69-2aeb6cbe476c)失敗します。 そのため、呼び出す必要はありません`InitContextMenuManager`を作成する場合、`CContextMenuManager`オブジェクトに直接します。 カスタムを使用していない場合`CContextMenuManager`、使用する必要があります`GetContextMenuManager`を作成する、`CContextMenuManager`オブジェクトです。  
  
##  <a name="a-nameinitkeyboardmanagera--cwinappexinitkeyboardmanager"></a><a name="initkeyboardmanager"></a>CWinAppEx::InitKeyboardManager  
 初期化、 [CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md)オブジェクトです。  
  
```  
BOOL InitKeyboardManager();
```  
  
### <a name="return-value"></a>戻り値  
 このメソッドを作成する場合は 0 以外、 `CKeyboardManager` 。 オブジェクトの場合は 0、`CKeyboardManager`オブジェクトが既に存在します。  
  
### <a name="remarks"></a>コメント  
 呼び出した場合[CWinAppEx::GetKeyboardManager](#getkeyboardmanager)、そのメソッドの既定の実装を呼び出す`InitKeyboardManager`します。  
  
 呼び出すし、アプリケーションで既にがキーボード マネージャー `InitKeyboardManager`、アプリケーションが、 [ASSERT](http://msdn.microsoft.com/library/1e70902d-d58c-4e7b-9f69-2aeb6cbe476c)失敗します。 そのため、呼び出す必要はありません`InitKeyboardManager`を作成する場合、`CKeyboardManager`オブジェクトに直接します。 カスタムを使用していない場合`CKeyboardManager`、使用する必要があります`GetKeyboardManager`を作成する、`CKeyboardManager`オブジェクトです。  
  
##  <a name="a-nameinitmousemanagera--cwinappexinitmousemanager"></a><a name="initmousemanager"></a>CWinAppEx::InitMouseManager  
 初期化、 [CMouseManager](../../mfc/reference/cmousemanager-class.md)オブジェクトです。  
  
```  
BOOL InitMouseManager();
```  
  
### <a name="return-value"></a>戻り値  
 このメソッドを作成する場合は 0 以外、 `CMouseManager` 。 オブジェクトの場合は 0、`CMouseManager`オブジェクトが既に存在します。  
  
### <a name="remarks"></a>コメント  
 呼び出した場合[CWinAppEx::GetMouseManager](#getmousemanager)、そのメソッドの既定の実装を呼び出す`InitMouseManager`します。  
  
 呼び出すし、アプリケーションで既にがマウス マネージャー `InitMouseManager`、アプリケーションが、 [ASSERT](http://msdn.microsoft.com/library/1e70902d-d58c-4e7b-9f69-2aeb6cbe476c)失敗します。 そのため呼び出す必要はありません`InitMouseManager`を作成する場合、`CMouseManager`オブジェクトに直接します。 カスタムを使用していない場合`CMouseManager`、使用する必要があります`GetMouseManager`を作成する、`CMouseManager`オブジェクトです。  
  
##  <a name="a-nameinitshellmanagera--cwinappexinitshellmanager"></a><a name="initshellmanager"></a>CWinAppEx::InitShellManager  
 初期化、 [CShellManager](../../mfc/reference/cshellmanager-class.md)オブジェクトです。  
  
```  
BOOL InitShellManager();
```  
  
### <a name="return-value"></a>戻り値  
 このメソッドを作成する場合は 0 以外、 `CShellManager` 。 オブジェクトの場合は 0、`CShellManager`オブジェクトが既に存在します。  
  
### <a name="remarks"></a>コメント  
 呼び出した場合[CWinAppEx::GetShellManager](#getshellmanager)、そのメソッドの既定の実装を呼び出す`InitShellManager`します。  
  
 呼び出すし、アプリケーションで既にがシェル マネージャー `InitShellManager`、アプリケーションが、 [ASSERT](http://msdn.microsoft.com/library/1e70902d-d58c-4e7b-9f69-2aeb6cbe476c)失敗します。 そのため、呼び出す必要はありません`InitShellManager`を作成する場合、`CShellManager`直接オブジェクトです。 カスタムを使用していない場合`CShellManager`を使用して`GetShellManager`を作成する、`CShellManager`オブジェクトです。  
  
##  <a name="a-nameinittooltipmanagera--cwinappexinittooltipmanager"></a><a name="inittooltipmanager"></a>CWinAppEx::InitTooltipManager  
 初期化、 [CTooltipManager](../../mfc/reference/ctooltipmanager-class.md)オブジェクトです。  
  
```  
BOOL InitTooltipManager();
```  
  
### <a name="return-value"></a>戻り値  
 このメソッドを作成する場合は 0 以外、 `CTooltipManager` 。 オブジェクトの場合は 0、`CTooltipManager`オブジェクトが既に存在します。  
  
### <a name="remarks"></a>コメント  
 呼び出した場合[CWinAppEx::GetTooltipManager](#gettooltipmanager)、そのメソッドの既定の実装を呼び出す`InitTooltipManager`します。  
  
 呼び出すし、アプリケーションで既にがツールヒント マネージャー `InitTooltipManager`、アプリケーションが、 [ASSERT](http://msdn.microsoft.com/library/1e70902d-d58c-4e7b-9f69-2aeb6cbe476c)失敗します。 そのため、呼び出す必要はありません`InitTooltipManager`を作成する場合、`CTooltipManager`オブジェクトに直接します。 カスタムを使用していない場合`CTooltipManager`、使用する必要があります`GetTooltipManager`を作成する、`CTooltipManager`オブジェクトです。  
  
##  <a name="a-nameisresourcesmartupdatea--cwinappexisresourcesmartupdate"></a><a name="isresourcesmartupdate"></a>CWinAppEx::IsResourceSmartUpdate  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsResourceSmartUpdate() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameisstateexistsa--cwinappexisstateexists"></a><a name="isstateexists"></a>CWinAppEx::IsStateExists  
 指定したキーがレジストリにするかどうかを示します。  
  
```  
BOOL IsStateExists(LPCTSTR lpszSectionName);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszSectionName`  
 レジストリ キーのパスを含む文字列です。  
  
### <a name="return-value"></a>戻り値  
 キーがレジストリにある場合は 0 以外。それ以外の場合 0 を返します。  
  
##  <a name="a-nameloadcustomstatea--cwinappexloadcustomstate"></a><a name="loadcustomstate"></a>CWinAppEx::LoadCustomState  
 フレームワークは、レジストリから、アプリケーションの状態を読み込んだ後に、このメソッドを呼び出します。  
  
```  
virtual void LoadCustomState();
```  
  
### <a name="remarks"></a>コメント  
 アプリケーションがレジストリから状態を読み込んだ後、処理を実行する場合は、このメソッドをオーバーライドします。 既定では、このメソッドは何もしません。  
  
 レジストリからカスタム状態情報を読み込むために情報は、最初に保存する必要を使用して[CWinAppEx::SaveCustomState](#savecustomstate)します。  
  
##  <a name="a-nameloadstatea--cwinappexloadstate"></a><a name="loadstate"></a>CWinAppEx::LoadState  
 アプリケーションの状態は、Windows レジストリから読み取ります。  
  
```  
BOOL LoadState(
    CMDIFrameWndEx* pFrame,  
    LPCTSTR lpszSectionName = NULL);

 
BOOL LoadState(
    CFrameWndEx* pFrame,  
    LPCTSTR lpszSectionName = NULL);

 
BOOL LoadState(
    COleIPFrameWndEx* pFrame,  
    LPCTSTR lpszSectionName = NULL);

 
virtual BOOL LoadState(
    LPCTSTR lpszSectionName = NULL,  
    CFrameImpl* pFrameImpl = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pFrame`  
 フレーム ウィンドウ オブジェクトへのポインター。 メソッドでは、このフレーム ウィンドウに、レジストリ内の状態情報が適用されます。  
  
 [入力] `lpszSectionName`  
 レジストリ キーの相対パスを含む文字列です。  
  
 [入力] `pFrameImpl`  
 ポインター、`CFrameImpl`オブジェクトです。 メソッドでは、このフレーム ウィンドウに、レジストリ内の状態情報が適用されます。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外。それ以外の場合は 0 です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、アプリケーションと、フレーム ウィンドウの状態情報の状態を読み込みます。 フレーム ウィンドウの読み込まれた情報は、指定されたフレーム ウィンドウに適用されます。 フレーム ウィンドウを指定しない場合は、アプリケーションの状態情報のみが読み込まれます。 アプリケーション情報の状態を含む、 [CMouseManager クラス](../../mfc/reference/cmousemanager-class.md)、 [CContextMenuManager クラス](../../mfc/reference/ccontextmenumanager-class.md)、 [CKeyboardManager クラス](../../mfc/reference/ckeyboardmanager-class.md)、および[CUserToolsManager クラス](../../mfc/reference/cusertoolsmanager-class.md)します。  
  
 既定の実装`CFrameImpl::OnLoadFrame`呼び出し`LoadState`します。  
  
 `lpszSectionName`パラメーターは、レジストリ エントリの絶対パスではありません。 相対パスをアプリケーションの既定のレジストリ キーの末尾に追加することをお勧めします。 を取得または既定のレジストリ キーを設定するには、メソッドを使用して[CWinAppEx::GetRegistryBase](#getregistrybase)と[CWinAppEx::SetRegistryBase](#setregistrybase)それぞれします。  
  
##  <a name="a-nameloadwindowplacementa--cwinappexloadwindowplacement"></a><a name="loadwindowplacement"></a>CWinAppEx::LoadWindowPlacement  
 メイン フレーム ウィンドウの場所とサイズをレジストリから読み込むときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL LoadWindowPlacement(
    CRect& rectNormalPosition,  
    int& nFlags,  
    int& nShowCmd);
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `rectNormalPosition`  
 元の位置にあるときに、メイン フレーム ウィンドウの座標を保持する四角形。  
  
 [出力] `nFlags`  
 最小化されたウィンドウや最小化されたウィンドウと、復元されたウィンドウの間でのオペレーティング システムのスイッチの位置を制御するフラグ。  
  
 [出力] `nShowCmd`  
 ウィンドウの表示状態を指定する整数。 使用可能な値の詳細については、次を参照してください。[また](../../mfc/reference/cwnd-class.md#showwindow)します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外。それ以外の場合は 0 です。  
  
### <a name="remarks"></a>コメント  
 既定では、MFC を自動的に読み込みます直前の位置と、メイン フレーム ウィンドウの状態、アプリケーションの起動時にします。 この情報をレジストリに格納する方法の詳細については、次を参照してください。 [CWinAppEx::StoreWindowPlacement](#storewindowplacement)します。  
  
 メイン フレーム ウィンドウに関する追加情報をロードする場合は、このメソッドをオーバーライドします。  
  
##  <a name="a-namembforceimagereseta--cwinappexmbforceimagereset"></a><a name="m_bforceimagereset"></a>CWinAppEx::m_bForceImageReset  
 フレーム ウィンドウ、ツールバーを含むプロジェクトを再読み込み、フレームワークがすべてのツール バー イメージをリセットするかどうかを指定します。  
  
```  
BOOL m_bForceImageReset;  
```  
  
### <a name="remarks"></a>コメント  
 `m_bForceImageReset`データ メンバーは保護されている変数。  
  
##  <a name="a-nameonappcontexthelpa--cwinappexonappcontexthelp"></a><a name="onappcontexthelp"></a>CWinAppEx::OnAppContextHelp  
 コンテキスト ヘルプを要求すると、フレームワークはこのメソッドを呼び出して、**カスタマイズ** ダイアログ ボックス。  
  
```  
virtual void OnAppContextHelp(
    CWnd* pWndControl,  
    const DWORD dwHelpIDArray[]);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWndControl`  
 ユーザーがコンテキスト ヘルプを呼び出したウィンドウ オブジェクトへのポインター。  
  
 [入力] `dwHelpIDArray[]`  
 予約済みの値。  
  
### <a name="remarks"></a>コメント  
 将来使用するには、このメソッドは予約されています。 既定の実装は何もしませんし、フレームワークからいない呼び出される現在です。  
  
##  <a name="a-nameonclosingmainframea--cwinappexonclosingmainframe"></a><a name="onclosingmainframe"></a>CWinAppEx::OnClosingMainFrame  
 フレーム ウィンドウを処理するときに、フレームワークはこのメソッドを呼び出して`WM_CLOSE`します。  
  
```  
virtual void OnClosingMainFrame(CFrameImpl* pFrameImpl);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pFrameImpl`  
 ポインター、`CFrameImpl`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 このメソッドの既定の実装の状態を保存する`pFrameImpl`です。  
  
##  <a name="a-nameonviewdoubleclicka--cwinappexonviewdoubleclick"></a><a name="onviewdoubleclick"></a>CWinAppEx::OnViewDoubleClick  
 ユーザーがビュー内の任意の場所をダブルクリックしたときに、ビューに関連付けられているユーザー定義のコマンドを呼び出します。  
  
```  
virtual BOOL OnViewDoubleClick(
    CWnd* pWnd,  
    int iViewId);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWnd`  
 派生したオブジェクトへのポインター、 [CView クラス](../../mfc/reference/cview-class.md)します。  
  
 [入力] `iViewId`  
 ビューの id です。  
  
### <a name="return-value"></a>戻り値  
 `True`フレームワークには、コマンドが検出された場合それ以外の場合は false。  
  
### <a name="remarks"></a>コメント  
 カスタムのマウスの動作をサポートするために処理すると、この関数を呼び出す必要があります、`WM_LBUTTONDBLCLK`メッセージです。 このメソッドは指定されたビューの ID に関連付けられているコマンドを実行`iViewId`します。 カスタムのマウスの動作の詳細については、次を参照してください。[キーボードとマウスのカスタマイズ](../../mfc/keyboard-and-mouse-customization.md)します。  
  
##  <a name="a-nameonworkspaceidlea--cwinappexonworkspaceidle"></a><a name="onworkspaceidle"></a>CWinAppEx::OnWorkspaceIdle  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnWorkspaceIdle(CWnd*);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `CWnd*`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namepreloadstatea--cwinappexpreloadstate"></a><a name="preloadstate"></a>CWinAppEx::PreLoadState  
 フレームワークは、レジストリから、アプリケーションの状態を読み込む直前に、このメソッドを呼び出します。  
  
```  
virtual void PreLoadState();
```  
  
### <a name="remarks"></a>コメント  
 フレームワークには、アプリケーションの状態が読み込まれる前にすぐに処理を実行する場合は、このメソッドをオーバーライドします。  
  
##  <a name="a-namepresavestatea--cwinappexpresavestate"></a><a name="presavestate"></a>CWinAppEx::PreSaveState  
 フレームワークは、アプリケーションの状態を保存する直前に、このメソッドを呼び出します。  
  
```  
virtual void PreSaveState();
```  
  
### <a name="remarks"></a>コメント  
 フレームワークは、アプリケーションの状態を保存する直前にどのような処理の操作を実行する場合は、このメソッドをオーバーライドします。  
  
##  <a name="a-namereloadwindowplacementa--cwinappexreloadwindowplacement"></a><a name="reloadwindowplacement"></a>CWinAppEx::ReloadWindowPlacement  
 レジストリからウィンドウの場所とサイズを再読み込みします。  
  
```  
virtual BOOL ReloadWindowPlacement(CFrameWnd* pFrame);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pFrame`  
 フレーム ウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は 0 以外。失敗した場合または負荷に読み込むデータがない場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 関数を使用して[CWinAppEx::StoreWindowPlacement](#storewindowplacement)サイズとウィンドウの場所をレジストリに書き込むためです。  
  
##  <a name="a-namesavecustomstatea--cwinappexsavecustomstate"></a><a name="savecustomstate"></a>CWinAppEx::SaveCustomState  
 フレームワークは、レジストリをアプリケーションの状態を保存した後に、このメソッドを呼び出します。  
  
```  
virtual void SaveCustomState();
```  
  
### <a name="remarks"></a>コメント  
 アプリケーションがレジストリに状態を保存した後に処理を実行する場合は、このメソッドをオーバーライドします。 既定では、このメソッドは何もしません。  
  
##  <a name="a-namesavestatea--cwinappexsavestate"></a><a name="savestate"></a>CWinAppEx::SaveState  
 アプリケーションの状態を Windows レジストリに書き込みます。  
  
```  
virtual BOOL SaveState(
    LPCTSTR lpszSectionName = NULL,  
    CFrameImpl* pFrameImpl = NULL);

 
BOOL SaveState(
    CMDIFrameWndEx* pFrame,  
    LPCTSTR lpszSectionName = NULL);

 
BOOL SaveState(
    CFrameWndEx* pFrame,  
    LPCTSTR lpszSectionName = NULL);

 
BOOL SaveState(
    COleIPFrameWndEx* pFrame,  
    LPCTSTR lpszSectionName = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszSectionName`  
 レジストリ キーの相対パスを含む文字列です。  
  
 [入力] `pFrameImpl`  
 ポインター、`CFrameImpl`オブジェクトです。 このフレームは、Windows レジストリに保存されます。  
  
 [入力] `pFrame`  
 フレーム ウィンドウ オブジェクトへのポインター。 このフレームは、Windows レジストリに保存されます。  
  
### <a name="return-value"></a>戻り値  
 `True`成功した場合`false`それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、アプリケーションおよび指定したフレーム ウィンドウの状態情報の状態を保存します。 フレーム ウィンドウを指定しないと、メソッドは、アプリケーションの状態を保存します。 アプリケーション情報の状態を含む、 [CMouseManager クラス](../../mfc/reference/cmousemanager-class.md)、 [CContextMenuManager クラス](../../mfc/reference/ccontextmenumanager-class.md)、 [CKeyboardManager クラス](../../mfc/reference/ckeyboardmanager-class.md)、および[CUserToolsManager クラス](../../mfc/reference/cusertoolsmanager-class.md)します。  
  
 `lpszSectionName`パラメーターは、レジストリ エントリの絶対パスではありません。 相対パス、アプリケーションの既定のレジストリ キーの末尾に追加することをお勧めします。 を取得または既定のレジストリ キーを設定するには、メソッドを使用して[CWinAppEx::GetRegistryBase](#getregistrybase)と[CWinAppEx::SetRegistryBase](#setregistrybase)それぞれします。  
  
##  <a name="a-namesetregistrybasea--cwinappexsetregistrybase"></a><a name="setregistrybase"></a>CWinAppEx::SetRegistryBase  
 アプリケーションの既定のレジストリ パスを設定します。  
  
```  
LPCTSTR SetRegistryBase(LPCTSTR lpszSectionName = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszSectionName`  
 レジストリ キーのパスを含む文字列です。  
  
### <a name="return-value"></a>戻り値  
 既定のレジストリの場所のパスを含む文字列です。  
  
### <a name="remarks"></a>コメント  
 すべてのメソッド、 [CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)既定の場所にレジストリの開始にアクセスします。 このメソッドを使用すると、その既定のレジストリの場所を変更できます。 使用[CWinAppEx::GetRegistryBase](#getregistrybase)を既定のレジストリの場所を取得します。  
  
##  <a name="a-nameshowpopupmenua--cwinappexshowpopupmenu"></a><a name="showpopupmenu"></a>CWinAppEx::ShowPopupMenu  
 ポップアップ メニューを表示します。  
  
```  
virtual BOOL ShowPopupMenu(
    UINT uiMenuResId,  
    const CPoint& point,  
    CWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiMenuResId`  
 メニュー リソースの id。  
  
 [入力] `point`  
 A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md)画面座標で、メニューの位置を指定します。  
  
 [入力] `pWnd`  
 ポップアップ メニューを所有するウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 ポップアップ メニューが正常に表示されている場合は 0 以外。それ以外の場合は 0 です。  
  
### <a name="remarks"></a>コメント  
 このメソッドに関連付けられているメニューを表示`uiMenuResId`します。  
  
 ポップアップ メニューをサポートするために必要な[CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md)オブジェクトです。 初期化していない場合、`CContextMenuManager`オブジェクト、`ShowPopupMenu`は失敗します。  
  
##  <a name="a-namestorewindowplacementa--cwinappexstorewindowplacement"></a><a name="storewindowplacement"></a>CWinAppEx::StoreWindowPlacement  
 メイン フレーム ウィンドウの場所とサイズをレジストリに書き込むために、フレームワークによって呼び出されます。  
  
```  
virtual BOOL StoreWindowPlacement(
    const CRect& rectNormalPosition,  
    int nFlags,  
    int nShowCmd);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nFlags`  
 最小化されたウィンドウや最小化されたウィンドウと、復元されたウィンドウの間でのオペレーティング システムのスイッチの位置を制御するフラグ。  
  
 [入力] `nShowCmd`  
 ウィンドウの表示状態を指定する整数。 使用可能な値の詳細については、次を参照してください。[また](../../mfc/reference/cwnd-class.md#showwindow)します。  
  
 [入力] `rectNormalPosition`  
 復元された状態にあるときは、メイン フレーム ウィンドウの座標を格納する四角形。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外。それ以外の場合は 0 です。  
  
### <a name="remarks"></a>コメント  
 MFC 既定では、位置と、アプリケーションが終了する前に、メイン フレーム ウィンドウの状態が自動的に保存します。 この情報は、アプリケーションの既定のレジストリの場所で WindowPlacement キーの下で、Windows レジストリに格納されます。 アプリケーションの既定のレジストリの場所の詳細については、次を参照してください。 [CWinAppEx::GetRegistryBase](#getregistrybase)します。  
  
 メイン フレーム ウィンドウに関する追加情報を格納する場合は、このメソッドをオーバーライドします。  
  
##  <a name="a-namewritebinarya--cwinappexwritebinary"></a><a name="writebinary"></a>CWinAppEx::WriteBinary  
 バイナリ データをレジストリに書き込みます。  
  
```  
BOOL WriteBinary(
    LPCTSTR lpszEntry,  
    LPBYTE pData,  
    UINT nBytes);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszEntry`  
 レジストリ キーの名前を表す文字列。  
  
 [入力] `pData`  
 格納するデータ。  
  
 [入力] `nBytes`  
 サイズ`pData`(バイト単位)。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`このメソッドが成功した場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 `lpszEntry`パラメーターは、アプリケーションの既定のレジストリ キーの下にあるレジストリ エントリの名前。 を取得または既定のレジストリ キーを設定するには、メソッドを使用して[CWinAppEx::GetRegistryBase](#getregistrybase)と[CWinAppEx::SetRegistryBase](#setregistrybase)それぞれします。  
  
 キーが指定された場合`lpszEntry`が存在しないこのメソッドによって作成されます。  
  
##  <a name="a-namewriteinta--cwinappexwriteint"></a><a name="writeint"></a>CWinAppEx::WriteInt  
 数値データをレジストリに書き込みます。  
  
```  
BOOL WriteInt(
    LPCTSTR lpszEntry,  
    int nValue);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszEntry`  
 レジストリ キーの名前を表す文字列。  
  
 [入力] `nValue`  
 格納するデータ。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`このメソッドが成功した場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 `lpszEntry`パラメーターは、アプリケーションの既定のレジストリ キーの下にあるレジストリ エントリの名前。 を取得または既定のレジストリ キーを設定するには、メソッドを使用して[CWinAppEx::GetRegistryBase](#getregistrybase)と[CWinAppEx::SetRegistryBase](#setregistrybase)それぞれします。  
  
 キーが指定された場合`lpszEntry`が存在しないこのメソッドによって作成されます。  
  
##  <a name="a-namewriteobjecta--cwinappexwriteobject"></a><a name="writeobject"></a>CWinAppEx::WriteObject  
 派生したデータを書き込み、 [CObject クラス](../../mfc/reference/cobject-class.md)をレジストリにします。  
  
```  
BOOL WriteObject(
    LPCTSTR lpszEntry,  
    CObject& obj);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszEntry`  
 設定する値を含む文字列です。  
  
 [入力] `obj`  
 参照を`CObject`メソッドを格納するデータ。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`このメソッドが成功した場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは書き込みます、`obj`にデータを既定のレジストリ キーに指定された値。 使用[CWinAppEx::GetRegistryBase](#getregistrybase)を現在のレジストリ キーを確認します。  
  
##  <a name="a-namewritesectionbinarya--cwinappexwritesectionbinary"></a><a name="writesectionbinary"></a>CWinAppEx::WriteSectionBinary  
 レジストリの値をバイナリ データを書き込みます。  
  
```  
BOOL WriteSectionBinary(
    LPCTSTR lpszSubSection,  
    LPCTSTR lpszEntry,  
    LPBYTE pData,  
    UINT nBytes);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszSubSection`  
 レジストリ キーの名前を表す文字列  
  
 [入力] `lpszEntry`  
 設定する値を含む文字列です。  
  
 [入力] `pData`  
 レジストリに書き込むデータ。  
  
 [入力] `nBytes`  
 サイズ`pData`(バイト単位)。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`このメソッドが成功した場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 `lpszSubSection`パラメーターは、レジストリ エントリの絶対パスではありません。 相対パス、アプリケーションの既定のレジストリ キーの末尾に追加することをお勧めします。 を取得または既定のレジストリ キーを設定するには、メソッドを使用して[CWinAppEx::GetRegistryBase](#getregistrybase)と[CWinAppEx::SetRegistryBase](#setregistrybase)それぞれします。  
  
 キーが指定された場合`lpszEntry`が存在しないこのメソッドによって作成されます。  
  
##  <a name="a-namewritesectioninta--cwinappexwritesectionint"></a><a name="writesectionint"></a>CWinAppEx::WriteSectionInt  
 数値データをレジストリに書き込みます。  
  
```  
BOOL WriteSectionInt(
    LPCTSTR lpszSubSection,  
    LPCTSTR lpszEntry,  
    int nValue);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszSubSection`  
 レジストリ キーの相対パスを含む文字列です。  
  
 [入力] `lpszEntry`  
 設定する値を含む文字列です。  
  
 [入力] `nValue`  
 レジストリに書き込むデータ。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`このメソッドが成功した場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 `lpszSubSection`パラメーターは、レジストリ エントリの絶対パスではありません。 相対パス、アプリケーションの既定のレジストリ キーに追加することをお勧めします。 を取得または既定のレジストリ キーを設定するには、メソッドを使用して[CWinAppEx::GetRegistryBase](#getregistrybase)と[CWinAppEx::SetRegistryBase](#setregistrybase)それぞれします。  
  
 キーが指定された場合`lpszEntry`が存在しないこのメソッドによって作成されます。  
  
##  <a name="a-namewritesectionobjecta--cwinappexwritesectionobject"></a><a name="writesectionobject"></a>CWinAppEx::WriteSectionObject  
 派生したデータを書き込み、 [CObject クラス](../../mfc/reference/cobject-class.md)特定のレジストリ値にします。  
  
```  
BOOL WriteSectionObject(
    LPCTSTR lpszSubSection,  
    LPCTSTR lpszEntry,  
    CObject& obj);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszSubSection`  
 レジストリ キーの名前を表す文字列。  
  
 [入力] `lpszEntry`  
 設定する値の名前を表す文字列。  
  
 [入力] `obj`  
 格納するデータ。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`このメソッドが成功した場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 `lpszSubSection`パラメーターは、レジストリ エントリの絶対パスではありません。 相対パス、アプリケーションの既定のレジストリ キーの末尾に追加することをお勧めします。 を取得または既定のレジストリ キーを設定するには、メソッドを使用して[CWinAppEx::GetRegistryBase](#getregistrybase)と[CWinAppEx::SetRegistryBase](#setregistrybase)、それぞれします。  
  
 値が指定された場合`lpszEntry`で指定されたレジストリ キーが存在しない`lpszSubSection`、このメソッドはその値を作成します。  
  
##  <a name="a-namewritesectionstringa--cwinappexwritesectionstring"></a><a name="writesectionstring"></a>CWinAppEx::WriteSectionString  
 レジストリの値を文字列データを書き込みます。  
  
```  
BOOL WriteSectionString(
    LPCTSTR lpszSubSection,  
    LPCTSTR lpszEntry,  
    LPCTSTR lpszValue);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszSubSection`  
 レジストリ キーの名前を表す文字列。  
  
 [入力] `lpszEntry`  
 設定する値を含む文字列です。  
  
 [入力] `lpszValue`  
 レジストリに書き込む文字列データです。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`このメソッドが成功した場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 `lpszSubSection`パラメーターは、レジストリ エントリの絶対パスではありません。 相対パス、アプリケーションの既定のレジストリ キーの末尾に追加することをお勧めします。 を取得または既定のレジストリ キーを設定するには、メソッドを使用して[CWinAppEx::GetRegistryBase](#getregistrybase)と[CWinAppEx::SetRegistryBase](#setregistrybase)、それぞれします。  
  
 値が指定された場合`lpszEntry`が存在しない`lpszSubSection`、このメソッドによって作成されます。  
  
##  <a name="a-namewritestringa--cwinappexwritestring"></a><a name="writestring"></a>CWinAppEx::WriteString  
 文字列データをレジストリに書き込みます。  
  
```  
BOOL WriteString(
    LPCTSTR lpszEntry,  
    LPCTSTR lpszValue);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszEntry`  
 レジストリ キーの名前を表す文字列。  
  
 [入力] `lpszValue`  
 格納するデータ。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`このメソッドが成功した場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 `lpszEntry`パラメーターは、アプリケーションの既定のレジストリ キーの下にあるレジストリ エントリの名前。 を取得または既定のレジストリ キーを設定するには、メソッドを使用して[CWinAppEx::GetRegistryBase](#getregistrybase)と[CWinAppEx::SetRegistryBase](#setregistrybase)それぞれします。  
  
 キーが指定された場合`lspzEntry`が存在しないこのメソッドによって作成されます。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CWinApp クラス](../../mfc/reference/cwinapp-class.md)   
 [CMouseManager クラス](../../mfc/reference/cmousemanager-class.md)   
 [CContextMenuManager クラス](../../mfc/reference/ccontextmenumanager-class.md)   
 [CKeyboardManager クラス](../../mfc/reference/ckeyboardmanager-class.md)   
 [CUserToolsManager クラス](../../mfc/reference/cusertoolsmanager-class.md)

