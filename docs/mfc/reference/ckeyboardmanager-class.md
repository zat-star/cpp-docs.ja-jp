---
title: "CKeyboardManager クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CKeyboardManager
dev_langs:
- C++
helpviewer_keywords:
- CKeyboardManager class
ms.assetid: 4809ece6-89df-4479-8b53-9bf476ee107b
caps.latest.revision: 33
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: bbe12d2bf4af0008233df25e09f09008c402ee7f
ms.lasthandoff: 02/24/2017

---
# <a name="ckeyboardmanager-class"></a>CKeyboardManager クラス
メイン フレーム ウィンドウおよび子フレーム ウィンドウのショートカット キーのテーブルを管理します。  
  
## <a name="syntax"></a>構文  
  
```  
class CKeyboardManager : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|||  
|-|-|  
|名前|説明|  
|[CKeyboardManager::CKeyboardManager](#ckeyboardmanager)|`CKeyboardManager` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|||  
|-|-|  
|名前|説明|  
|[CKeyboardManager::CleanUp](#cleanup)|ショートカット キーのテーブルを消去します。|  
|[CKeyboardManager::FindDefaultAccelerator](#finddefaultaccelerator)|指定されたコマンドおよびウィンドウの既定のショートカット キーを取得します。|  
|[CKeyboardManager::IsKeyHandled](#iskeyhandled)|アクセラレータ テーブルで、キーが処理されるかどうかを決定します。|  
|[CKeyboardManager::IsKeyPrintable](#iskeyprintable)|文字が印刷可能かどうかを示します。|  
|[CKeyboardManager::IsShowAllAccelerators](#isshowallaccelerators)|メニューには、コマンドのすべてのショートカット キー、または既定のショートカット キーのみが表示されるかどうかを示します。|  
|[CKeyboardManager::LoadState](#loadstate)|Windows レジストリからショートカット キーのテーブルを読み込みます。|  
|[CKeyboardManager::ResetAll](#resetall)|アプリケーション リソースからショートカット キーのテーブルを再読み込みします。|  
|[CKeyboardManager::SaveState](#savestate)|ショートカット キーのテーブルを Windows レジストリに保存します。|  
|[CKeyboardManager::ShowAllAccelerators](#showallaccelerators)|フレームワークは、すべてのコマンドのショートカット キーのすべてまたはコマンドごとに&1; つのショートカット キーを表示するかどうかを指定します。 このメソッドは、関連付けられているショートカット キーは&1; つのコマンドには影響しません。|  
|[CKeyboardManager::TranslateCharToUpper](#translatechartoupper)|文字を大文字レジスタに変換します。|  
|[CKeyboardManager::UpdateAccelTable](#updateacceltable)|新しいショートカット キー テーブルでは、ショートカット キーのテーブルを更新します。|  
  
## <a name="remarks"></a>コメント  
 このクラスのメンバーを使用すると、保存、Windows レジストリにショートカット キーのテーブルを読み込むと、テンプレートを使用して、ショートカット キーのテーブルを更新し、フレーム ウィンドウで、コマンドの既定のショートカット キーを検索します。 さらに、`CKeyboardManager`オブジェクトでは、ユーザーのショートカット キーの表示方法を制御することができます。  
  
 作成しないで、`CKeyboardManager`手動でのオブジェクトします。 アプリケーションのフレームワークによって自動的に作成されます。 ただし、呼び出す必要があります[CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager)アプリケーションの初期化プロセス中にします。 アプリケーションのキーボード マネージャーへのポインターを取得する[CWinAppEx::GetKeyboardManager](../../mfc/reference/cwinappex-class.md#getkeyboardmanager)します。  
  
## <a name="example"></a>例  
 次の例へのポインターを取得する方法、`CKeyboardManager`オブジェクトから、`CWinAppEx`クラス、およびメニュー コマンドに関連付けられているすべてのショートカット キーを表示する方法です。 このコード スニペットの一部である、[カスタム ページ サンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_CustomPages&#5;](../../mfc/reference/codesnippet/cpp/ckeyboardmanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxkeyboardmanager.h  
  
##  <a name="a-nameckeyboardmanagera--ckeyboardmanagerckeyboardmanager"></a><a name="ckeyboardmanager"></a>CKeyboardManager::CKeyboardManager  
 `CKeyboardManager` オブジェクトを構築します。  
  
```  
CKeyboardManager();
```  
  
### <a name="remarks"></a>コメント  
 ほとんどの場合は作成する必要はありません、`CKeyboardManager`直接します。 既定では、フレームワークは自動的に作成します。 ポインターを取得する、 `CKeyboardManager`、呼び出す[CWinAppEx::GetKeyboardManager](../../mfc/reference/cwinappex-class.md#getkeyboardmanager)します。 作成する場合は&1; つ手動で、メソッドを使用して初期化する必要があります[CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager)します。  
  
##  <a name="a-namecleanupa--ckeyboardmanagercleanup"></a><a name="cleanup"></a>CKeyboardManager::CleanUp  
 解放、`CKeyboardManager`リソースおよびすべてのショートカット キーのマッピングをクリアします。  
  
```  
static void CleanUp();
```  
  
### <a name="remarks"></a>コメント  
 ショートカット キーの詳細については、次を参照してください。[キーボードとマウスのカスタマイズ](../../mfc/keyboard-and-mouse-customization.md)します。  
  
 フレームワークとアプリケーションの終了時に自動的に記述しているため、アプリケーションが終了したときに、この関数を呼び出す必要はありません。  
  
##  <a name="a-namefinddefaultacceleratora--ckeyboardmanagerfinddefaultaccelerator"></a><a name="finddefaultaccelerator"></a>CKeyboardManager::FindDefaultAccelerator  
 指定されたコマンドおよびウィンドウの既定のショートカット キーを取得します。  
  
```  
static BOOL FindDefaultAccelerator(
    UINT uiCmd,  
    CString& str,  
    CFrameWnd* pWndFrame,  
    BOOL bIsDefaultFrame);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiCmd`  
 コマンド ID。  
  
 [出力] `str`  
 `CString` オブジェクトへの参照。  
  
 [入力] `pWndFrame`  
 フレーム ウィンドウへのポインター。  
  
 [入力] `bIsDefaultFrame`  
 フレーム ウィンドウが既定のフレーム ウィンドウであるかどうかを指定します。  
  
### <a name="return-value"></a>戻り値  
 ショートカットが見つかった場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドで指定されたコマンドを検索`uiCmd`し、既定のショートカット キーを取得します。 メソッドは、このショートカット キーに関連付けられている文字列を取得しに値を書き込み、`str`パラメーター。  
  
##  <a name="a-nameiskeyhandleda--ckeyboardmanageriskeyhandled"></a><a name="iskeyhandled"></a>CKeyboardManager::IsKeyHandled  
 指定したキーを処理するかどうかを決定、 [CKeyboardManager クラス](../../mfc/reference/ckeyboardmanager-class.md)します。  
  
```  
static BOOL __stdcall IsKeyHandled(
    WORD nKey,  
    BYTE fVirt,  
    CFrameWnd* pWndFrame,  
    BOOL bIsDefaultFrame);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `nKey`|チェックするキー。|  
|[入力] `fVirt`|ショートカット キーの動作を指定します。 使用可能な値の一覧は、次を参照してください。 [ACCEL 構造体](http://msdn.microsoft.com/library/windows/desktop/ms646340)します。|  
|[入力] `pWndFrame`|フレーム ウィンドウです。 このメソッドは、このフレーム内のショートカット キーを処理するかどうかを判断します。|  
|[入力] `bIsDefaultFrame`|示すブール値パラメーターかどうか`pWndFrame`は既定のフレーム ウィンドウです。|  
  
### <a name="return-value"></a>戻り値  
 `TRUE`場合は、ショートカット キーを処理するとします。 `FALSE`キーが処理されない場合、または`pWndFrame`は`NULL`です。  
  
### <a name="remarks"></a>コメント  
 入力パラメーターは、アクセラレータ テーブルで両方のエントリと一致する必要があります`nKey`と`fVirt`のショートカット キーを処理するかどうかを確認する`pWndFrame`です。  
  
##  <a name="a-nameiskeyprintablea--ckeyboardmanageriskeyprintable"></a><a name="iskeyprintable"></a>CKeyboardManager::IsKeyPrintable  
 文字が印刷可能かどうかを示します。  
  
```  
static BOOL __stdcall IsKeyPrintable(const UINT nChar);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `nChar`|このメソッドをチェックする文字。|  
  
### <a name="return-value"></a>戻り値  
 0 以外の値がない場合は、文字が印刷可能な場合は、0 です。  
  
### <a name="remarks"></a>コメント  
 このメソッドへの呼び出しは失敗[GetKeyboardState](http://msdn.microsoft.com/library/windows/desktop/ms646299)は失敗します。  
  
##  <a name="a-nameisshowallacceleratorsa--ckeyboardmanagerisshowallaccelerators"></a><a name="isshowallaccelerators"></a>CKeyboardManager::IsShowAllAccelerators  
 メニューにメニュー コマンドに関連付けられているすべてのショートカット キー、または既定のショートカット キーのみが表示されるかどうかを示します。  
  
```  
static BOOL IsShowAllAccelerators();
```  
  
### <a name="return-value"></a>戻り値  
 アプリケーションにメニュー コマンドのショートカット キーのすべてが表示されている場合は 0 以外。アプリケーションは、既定のショートカット キーのみを表示する場合は 0。  
  
### <a name="remarks"></a>コメント  
 アプリケーションでは、メニュー バーでメニュー コマンドのショートカット キーを示します。 関数を使用して[CKeyboardManager::ShowAllAccelerators](#showallaccelerators)リストを制御するかどうか、アプリケーション ショートカット キーのすべてまたは既定のショートカット キーを持つユーザーだけです。  
  
##  <a name="a-nameloadstatea--ckeyboardmanagerloadstate"></a><a name="loadstate"></a>CKeyboardManager::LoadState  
 Windows レジストリからショートカット キーのテーブルを読み込みます。  
  
```  
BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,  
    CFrameWnd* pDefaultFrame = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszProfileName`  
 レジストリ パス、`CKeyboardManager`データを保存します。  
  
 [入力] `pDefaultFrame`  
 既定のウィンドウとして使用するフレーム ウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、状態が正常に読み込まれた、または 0 それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 場合、`lpszProfileName`パラメーターは`NULL`、このメソッドの既定のレジストリの場所をチェックする`CKeyboardManager`データ。 既定のレジストリの場所が指定された、 [CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)します。 メソッドを使用して、データを以前記述する必要があります[CKeyboardManager::SaveState](#savestate)します。  
  
 既定のウィンドウを指定しない場合は、アプリケーションのメイン フレーム ウィンドウが使用されます。  
  
##  <a name="a-nameresetalla--ckeyboardmanagerresetall"></a><a name="resetall"></a>CKeyboardManager::ResetAll  
 アプリケーション リソースからショートカット キーのテーブルを再読み込みします。  
  
```  
void ResetAll();
```  
  
### <a name="remarks"></a>コメント  
 この関数に格納されているショートカットのクリア、`CKeyboardManager`インスタンス。 アプリケーション リソースからキーボード マネージャーの状態が 再読み込みします。  
  
##  <a name="a-namesavestatea--ckeyboardmanagersavestate"></a><a name="savestate"></a>CKeyboardManager::SaveState  
 ショートカット キーのテーブルを Windows レジストリに保存します。  
  
```  
BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,  
    CFrameWnd* pDefaultFrame = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszProfileName`  
 保存するためのレジストリ パス、`CKeyboardManager`状態です。  
  
 [入力] `pDefaultFrame`  
 既定のウィンドウになったフレーム ウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 キーボードのマネージャーの状態が正常に保存されている場合は 0 以外。 それ以外の場合は 0 です。  
  
### <a name="remarks"></a>コメント  
 場合、`lpszProfileName`パラメーターは`NULL`、このメソッドは、書き込み、`CKeyboardManager`で指定された既定の場所に状態、 [CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)します。 場所を指定すると、後で、メソッドを使用してデータを読み込むことができます[CKeyboardManager::LoadState](#loadstate)します。  
  
 既定のウィンドウを指定しない場合、メイン フレーム ウィンドウが既定のウィンドウとして使用されます。  
  
##  <a name="a-nameshowallacceleratorsa--ckeyboardmanagershowallaccelerators"></a><a name="showallaccelerators"></a>CKeyboardManager::ShowAllAccelerators  
 メニュー コマンドに関連付けられているすべてのショートカット キーを示します。  
  
```  
static void ShowAllAccelerators(
    BOOL bShowAll = TRUE,  
    LPCTSTR lpszDelimiter = _afxDefaultAcceleratorDelimiter);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bShowAll`  
 場合`true`、ショートカット キーのすべてが表示されます。 場合`false`、最初のショートカット キーのみが表示されます。  
  
 [入力] `lpszDelimiter`  
 ショートカット キーの間に挿入する文字列。 1 つのショートカット キーが表示されるだけの場合は、この区切り記号を指定しても効果はありません。  
  
### <a name="remarks"></a>コメント  
 既定では、コマンドに複数のショートカット キーが、それに関連付けられている場合、最初のショートカット キーのみ表示されます。 この関数では、すべてのコマンドに関連付けられているショートカット キーをすべて表示することができます。  
  
 ショートカット キーは、メニュー バーで、コマンドの横に表示されます。 ショートカット キーのすべてが表示され、文字列がによって提供される`lpszDelimiter`個々 のショートカット キーを分離します。  
  
##  <a name="a-nametranslatechartouppera--ckeyboardmanagertranslatechartoupper"></a><a name="translatechartoupper"></a>CKeyboardManager::TranslateCharToUpper  
 文字を大文字レジスタに変換します。  
  
```  
static UINT TranslateCharToUpper(const UINT nChar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nChar`  
 変換する文字。  
  
### <a name="return-value"></a>戻り値  
 入力パラメーターの大文字のレジスタは、文字です。  
  
##  <a name="a-nameupdateacceltablea--ckeyboardmanagerupdateacceltable"></a><a name="updateacceltable"></a>CKeyboardManager::UpdateAccelTable  
 新しいショートカット キー テーブルでは、ショートカット キーのテーブルを更新します。  
  
```  
BOOL UpdateAccelTable(
    CMultiDocTemplate* pTemplate,  
    LPACCEL lpAccel,  
    int nSize,  
    CFrameWnd* pDefaultFrame = NULL);

 
BOOL UpdateAccelTable(
    CMultiDocTemplate* pTemplate,  
    HACCEL hAccelNew,  
    CFrameWnd* pDefaultFrame = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pTemplate`  
 ドキュメント テンプレートへのポインター。  
  
 [入力] `lpAccel`  
 新しいショートカット キーへのポインター。  
  
 [入力] `nSize`  
 新しいショートカット テーブルのサイズ。  
  
 [入力] `pDefaultFrame`  
 既定のフレーム ウィンドウへのポインター。  
  
 [入力] `hAccelNew`  
 新しいショートカット テーブルへのハンドル。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数を使用して、既存のショートカットの表をいくつかのフレーム ウィンドウ オブジェクトの新しいショートカット キーに置き換えます。 関数は、ドキュメント テンプレートを特定のドキュメント テンプレートに接続されているすべてのフレーム ウィンドウ オブジェクトへのアクセスを取得するパラメーターとして受け取ります。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)   
 [CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager)   
 [キーボードとマウスのカスタマイズ](../../mfc/keyboard-and-mouse-customization.md)




