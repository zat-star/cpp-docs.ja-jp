---
title: "メンバー クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCommandLineInfo
dev_langs:
- C++
helpviewer_keywords:
- CCommandLineInfo class
- command line, parsing
- parsing, command-line arguments
- argv argument
- startup code, parsing command-line arguments
- application flags [C++]
ms.assetid: 3e313ddb-0a82-4991-87ac-a27feff4668c
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: cb8cd58e4e7cf0318b8826cf473739e26e730273
ms.lasthandoff: 02/24/2017

---
# <a name="ccommandlineinfo-class"></a>メンバー クラス
アプリケーション起動時のコマンド ライン解析を補助します。  
  
## <a name="syntax"></a>構文  
  
```  
class CCommandLineInfo : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CCommandLineInfo::CCommandLineInfo](#ccommandlineinfo)|既定値を構築`CCommandLineInfo`オブジェクトです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[その](#parseparam)|個別のパラメーターを解析するには、このコールバックをオーバーライドします。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CCommandLineInfo::m_bRunAutomated](#m_brunautomated)|コマンドラインに示す**/Automation**オプションが見つかりました。|  
|[CCommandLineInfo::m_bRunEmbedded](#m_brunembedded)|コマンドラインに示す**埋め込み/**オプションが見つかりました。|  
|[CCommandLineInfo::m_bShowSplash](#m_bshowsplash)|スプラッシュ スクリーンを表示するかどうかを示します。|  
|[CCommandLineInfo::m_nShellCommand](#m_nshellcommand)|シェル コマンドを処理することを示します。|  
|[CCommandLineInfo::m_strDriverName](#m_strdrivername)|ドライバーを示す名前を印刷するには、シェル コマンドの場合それ以外の場合は空です。|  
|[CCommandLineInfo::m_strFileName](#m_strfilename)|開くファイルまたは印刷されるファイル名を示しますシェル コマンドは、新規または DDE 場合は空です。|  
|[CCommandLineInfo::m_strPortName](#m_strportname)|ポートを示す名前を印刷するには、シェル コマンドの場合それ以外の場合は空です。|  
|[CCommandLineInfo::m_strPrinterName](#m_strprintername)|プリンターを示す名前を印刷するには、シェル コマンドの場合それ以外の場合は空です。|  
|[CCommandLineInfo::m_strRestartIdentifier](#m_strrestartidentifier)|再起動マネージャーには、アプリケーションが再起動された場合は、再起動マネージャーの一意の再起動の識別子を示します。|  
  
## <a name="remarks"></a>コメント  
 MFC アプリケーションが通常では、このクラスのローカル インスタンスを作成、 [InitInstance](../../mfc/reference/cwinapp-class.md#initinstance)アプリケーション オブジェクトの関数です。 このオブジェクトが渡される、 [CWinApp::ParseCommandLine](../../mfc/reference/cwinapp-class.md#parsecommandline)、これを繰り返し呼び出す[ParseParam](#parseparam)入力、`CCommandLineInfo`オブジェクトです。 `CCommandLineInfo`オブジェクトに渡されます[CWinApp::ProcessShellCommand](../../mfc/reference/cwinapp-class.md#processshellcommand)コマンドライン引数とフラグを処理します。  
  
 このオブジェクトを使用すると、次のコマンド ライン オプションとパラメーターをカプセル化します。  
  
|コマンドライン引数|実行されたコマンド|  
|----------------------------|----------------------|  
|*app*|新しいファイル。|  
|*アプリ*ファイル名|ファイルを開く.|  
|*アプリ* **/p**ファイル名|既定のプリンターにファイルを印刷します。|  
|*アプリ* **/pt**ファイル名のプリンター ドライバーのポート|指定したプリンターにファイルを印刷します。|  
|*app* **/dde**|起動し、DDE コマンドを待機します。|  
|*アプリ* **/Automation**|OLE オートメーション サーバーとして起動します。|  
|*アプリ***埋め込み/**|OLE 埋め込みアイテムを編集するのを起動します。|  
|*アプリ* **/register**<br /><br /> *アプリ* **/Regserver**|登録タスクを実行するアプリケーションに通知します。|  
|*アプリ* **/登録解除**<br /><br /> *アプリ* **/Unregserver**|登録解除タスクを実行するアプリケーションに通知します。|  
  
 新しいクラスを派生`CCommandLineInfo`を他のフラグとパラメーター値を処理します。 オーバーライド[ParseParam](#parseparam)を新しいフラグを処理します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CCommandLineInfo`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="a-nameccommandlineinfoa--ccommandlineinfoccommandlineinfo"></a><a name="ccommandlineinfo"></a>CCommandLineInfo::CCommandLineInfo  
 このコンス トラクターを作成、`CCommandLineInfo`既定値を持つオブジェクト。  
  
```  
CCommandLineInfo();
```  
  
### <a name="remarks"></a>コメント  
 既定値は、スプラッシュ画面を表示するのには ( `m_bShowSplash` **= TRUE**) とコマンドを実行する、新しい [ファイル] メニュー ( `m_nShellCommand` **NewFile =**)。  
  
 アプリケーション フレームワーク[ParseParam](#parseparam)にこのオブジェクトのデータ メンバーを設定します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&54;](../../mfc/codesnippet/cpp/ccommandlineinfo-class_1.cpp)]  
  
##  <a name="a-namembrunautomateda--ccommandlineinfombrunautomated"></a><a name="m_brunautomated"></a>CCommandLineInfo::m_bRunAutomated  
 示して、 **/Automation**フラグは、コマンドラインで見つかりました。  
  
```  
BOOL m_bRunAutomated;  
```  
  
### <a name="remarks"></a>コメント  
 場合**TRUE**、つまり、OLE オートメーション サーバーとして起動します。  
  
##  <a name="a-namembrunembeddeda--ccommandlineinfombrunembedded"></a><a name="m_brunembedded"></a>CCommandLineInfo::m_bRunEmbedded  
 示します、 **埋め込み/**フラグは、コマンドラインで見つかりました。  
  
```  
BOOL m_bRunEmbedded;  
```  
  
### <a name="remarks"></a>コメント  
 場合**TRUE**、つまり OLE 埋め込みアイテムの編集開始します。  
  
##  <a name="a-namembshowsplasha--ccommandlineinfombshowsplash"></a><a name="m_bshowsplash"></a>CCommandLineInfo::m_bShowSplash  
 スプラッシュ スクリーンを表示することを示します。  
  
```  
BOOL m_bShowSplash;  
```  
  
### <a name="remarks"></a>コメント  
 場合**TRUE**、スプラッシュ スクリーンをつまり起動中にこのアプリケーションを表示する必要があります。 既定の実装[ParseParam](#parseparam)このデータ メンバーを設定**TRUE**場合[m_nShellCommand](#m_nshellcommand)に等しい**CCommandLineInfo::FileNew**します。  
  
##  <a name="a-namemnshellcommanda--ccommandlineinfomnshellcommand"></a><a name="m_nshellcommand"></a>CCommandLineInfo::m_nShellCommand  
 アプリケーションのこのインスタンスのシェル コマンドを示します。  
  
```  
m_nShellCommand;  
```  
  
### <a name="remarks"></a>コメント  
 このデータ メンバーの型は、次の列挙型で定義されている、`CCommandLineInfo`クラスです。  
  
 `enum{`  
  
 `FileNew,`  
  
 `FileOpen,`  
  
 `FilePrint,`  
  
 `FilePrintTo,`  
  
 `FileDDE,`  
  
 `AppRegister,`  
  
 `AppUnregister,`  
  
 `RestartByRestartManager,`  
  
 `FileNothing = -1`  
  
 `};`  
  
 これらの値の簡単な説明は、次の一覧を参照してください。  
  
- `CCommandLineInfo::FileNew`コマンドラインにファイル名が見つかりませんだったことを示します。  
  
- `CCommandLineInfo::FileOpen`コマンドラインでファイル名が見つからなかったこと、次のフラグの値は、コマンドラインで見つかりませんでした。 示し: `/p`、 `/pt`、`/dde`です。  
  
- `CCommandLineInfo::FilePrint`示して、`/p`フラグは、コマンドラインで見つかりました。  
  
- `CCommandLineInfo::FilePrintTo`示して、`/pt`フラグは、コマンドラインで見つかりました。  
  
- `CCommandLineInfo::FileDDE`示して、`/dde`フラグは、コマンドラインで見つかりました。  
  
- `CCommandLineInfo::AppRegister`示して、`/Register`または`/Regserver`フラグがコマンドラインで検出され、アプリケーションを登録するように要求されました。  
  
- `CCommandLineInfo::AppUnregister`示して、`/Unregister`または`/Unregserver`アプリケーションは、登録を解除するように要求されました。  
  
- `CCommandLineInfo::RestartByRestartManager`再起動マネージャーによって、アプリケーションが再起動されたことを示します。  
  
- `CCommandLineInfo::FileNothing`起動時に新しい MDI 子ウィンドウの表示を無効にします。 仕様では、アプリケーション ウィザードで生成された MDI アプリケーションは起動時に新しい子ウィンドウを表示します。 この機能を無効にするには、アプリケーションが使用できる`CCommandLineInfo::FileNothing`を呼び出すときに、シェル コマンドとして[によって](../../mfc/reference/cwinapp-class.md#processshellcommand)します。 `ProcessShellCommand`によって呼び出される、`InitInstance( )`すべて`CWinApp`クラスを派生します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&55;](../../mfc/codesnippet/cpp/ccommandlineinfo-class_2.cpp)]  
  
##  <a name="a-namemstrdrivernamea--ccommandlineinfomstrdrivername"></a><a name="m_strdrivername"></a>CCommandLineInfo::m_strDriverName  
 コマンドラインでは、3 番目のフラグでないパラメーターの値を格納します。  
  
```  
CString m_strDriverName;  
```  
  
### <a name="remarks"></a>コメント  
 このパラメーターは、通常、印刷シェル コマンドのプリンタ ドライバの名前です。 既定の実装[ParseParam](#parseparam)設定データ メンバー場合のみ、この、 **/pt**フラグは、コマンドラインで見つかりました。  
  
##  <a name="a-namemstrfilenamea--ccommandlineinfomstrfilename"></a><a name="m_strfilename"></a>CCommandLineInfo::m_strFileName  
 コマンドラインでは、最初のフラグでないパラメーターの値を格納します。  
  
```  
CString m_strFileName;  
```  
  
### <a name="remarks"></a>コメント  
 このパラメーターは、通常、開くファイルの名前です。  
  
##  <a name="a-namemstrportnamea--ccommandlineinfomstrportname"></a><a name="m_strportname"></a>CCommandLineInfo::m_strPortName  
 コマンドラインでは、4 番目のフラグでないパラメーターの値を格納します。  
  
```  
CString m_strPortName;  
```  
  
### <a name="remarks"></a>コメント  
 このパラメーターは、通常、印刷シェル コマンドのプリンター ポートの名前です。 既定の実装[ParseParam](#parseparam)設定データ メンバー場合のみ、この、 **/pt**フラグは、コマンドラインで見つかりました。  
  
##  <a name="a-namemstrprinternamea--ccommandlineinfomstrprintername"></a><a name="m_strprintername"></a>CCommandLineInfo::m_strPrinterName  
 コマンドラインでは、2 番目のフラグでないパラメーターの値を格納します。  
  
```  
CString m_strPrinterName;  
```  
  
### <a name="remarks"></a>コメント  
 このパラメーターは、通常、印刷シェル コマンドのプリンターの名前です。 既定の実装[ParseParam](#parseparam)設定データ メンバー場合のみ、この、 **/pt**フラグは、コマンドラインで見つかりました。  
  
##  <a name="a-namemstrrestartidentifiera--ccommandlineinfomstrrestartidentifier"></a><a name="m_strrestartidentifier"></a>CCommandLineInfo::m_strRestartIdentifier  
 コマンド ライン上の識別子を一意に再起動します。  
  
```  
CString m_strRestartIdentifier;  
```  
  
### <a name="remarks"></a>コメント  
 再起動識別子は、アプリケーションの各インスタンスに一意です。  
  
 再起動マネージャーは、アプリケーションを終了するし、再起動するように構成、再起動マネージャーは、省略可能なパラメーターとして再起動識別子を使用してコマンドラインからアプリケーションを実行します。 再起動マネージャーは、再起動の識別子を使用する場合、アプリケーションが開いていたドキュメントを再び開くしたり、自動保存されたファイルを回復します。  
  
##  <a name="a-nameparseparama--ccommandlineinfoparseparam"></a><a name="parseparam"></a>その  
 フレームワークでは、コマンドラインからの個々 のパラメーターの解析/解釈には、この関数を呼び出します。 最初の&2; つ目のバージョンと一致しない Unicode プロジェクトでのみです。  
  
```  
virtual void ParseParam(
    const char* pszParam,  
    BOOL bFlag,  
    BOOL bLast);

 
virtual void ParseParam(
    const TCHAR* pszParam,  
    BOOL bFlag,  
    BOOL bLast);
```  
  
### <a name="parameters"></a>パラメーター  
 `pszParam`  
 パラメーターまたはフラグ。  
  
 *bFlag*  
 示すかどうか`pszParam`パラメーターまたはフラグ。  
  
 `bLast`  
 これは最後のパラメーターまたはコマンドラインでフラグを示します。  
  
### <a name="remarks"></a>コメント  
 [CWinApp::ParseCommandLine](../../mfc/reference/cwinapp-class.md#parsecommandline)呼び出し`ParseParam`1 回ごとのパラメーターまたはコマンドラインでフラグを使用して、引数を渡す`pszParam`します。 パラメーターの最初の文字がある場合、' ** - **'または' ** / **' が削除および*bFlag*に設定されている**TRUE**します。 最後のパラメーターを解析するときに`bLast`に設定されている**TRUE**します。  
  
 この関数の既定の実装は、次のフラグを認識します。 **/p**、 **/pt**、 **/dde**、 **/Automation**、および**埋め込み/**次の表に示すように。  
  
|コマンドライン引数|実行されたコマンド|  
|----------------------------|----------------------|  
|*app*|新しいファイル。|  
|*アプリ*ファイル名|ファイルを開く.|  
|*アプリ* **/p**ファイル名|既定のプリンターにファイルを印刷します。|  
|*アプリ* **/pt**ファイル名のプリンター ドライバーのポート|指定したプリンターにファイルを印刷します。|  
|*app* **/dde**|起動し、DDE コマンドを待機します。|  
|*アプリ* **/Automation**|OLE オートメーション サーバーとして起動します。|  
|*アプリ***埋め込み/**|OLE 埋め込みアイテムを編集するのを起動します。|  
|*アプリ* **/register**<br /><br /> *アプリ* **/Regserver**|登録タスクを実行するアプリケーションに通知します。|  
|*アプリ* **/登録解除**<br /><br /> *アプリ* **/Unregserver**|登録解除タスクを実行するアプリケーションに通知します。|  
  
 この情報が格納されている[m_bRunAutomated](#m_brunautomated)、 [m_bRunEmbedded](#m_brunembedded)、および[m_nShellCommand](#m_nshellcommand)します。 フラグでマークされたいずれかのスラッシュ ' ** / **'またはハイフン' ** - **' です。  
  
 既定の実装で、最初のフラグでないパラメーターには、 [m_strFileName](#m_strfilename)します。 場合、 **/pt**フラグは、既定の実装は、2 番目の場合に、3 番目と&4; 番目のフラグでないパラメーター [m_strPrinterName](#m_strprintername)、 [m_strDriverName](#m_strdrivername)、および[m_strPortName](#m_strportname)、それぞれします。  
  
 既定の実装も設定[m_bShowSplash](#m_bshowsplash)に**TRUE**新しいファイルの場合にのみです。 新しいファイルの場合、ユーザーがアプリケーション自体に関連するアクションを取得します。 シェルを使用して既存のファイルを開くことを含め、他の場合は、ユーザーの操作は、ファイルを直接です。 スプラッシュ スクリーンは、ドキュメント中心の観点で、アプリケーションの起動を発表する必要はありません。  
  
 その他のフラグとパラメーターの値を処理する派生クラスでオーバーライドします。  
  
## <a name="see-also"></a>関連項目  
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CWinApp::ParseCommandLine](../../mfc/reference/cwinapp-class.md#parsecommandline)   
 [CWinApp::ProcessShellCommand](../../mfc/reference/cwinapp-class.md#processshellcommand)


