---
title: "CDataRecoveryHandler クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDataRecoveryHandler
- AFXDATARECOVERY/CDataRecoveryHandler
- AFXDATARECOVERY/CDataRecoveryHandler::CDataRecoveryHandler
- AFXDATARECOVERY/CDataRecoveryHandler::AutosaveAllDocumentInfo
- AFXDATARECOVERY/CDataRecoveryHandler::AutosaveDocumentInfo
- AFXDATARECOVERY/CDataRecoveryHandler::CreateDocumentInfo
- AFXDATARECOVERY/CDataRecoveryHandler::DeleteAllAutosavedFiles
- AFXDATARECOVERY/CDataRecoveryHandler::DeleteAutosavedFile
- AFXDATARECOVERY/CDataRecoveryHandler::GenerateAutosaveFileName
- AFXDATARECOVERY/CDataRecoveryHandler::GetAutosaveInterval
- AFXDATARECOVERY/CDataRecoveryHandler::GetAutosavePath
- AFXDATARECOVERY/CDataRecoveryHandler::GetDocumentListName
- AFXDATARECOVERY/CDataRecoveryHandler::GetNormalDocumentTitle
- AFXDATARECOVERY/CDataRecoveryHandler::GetRecoveredDocumentTitle
- AFXDATARECOVERY/CDataRecoveryHandler::GetRestartIdentifier
- AFXDATARECOVERY/CDataRecoveryHandler::GetSaveDocumentInfoOnIdle
- AFXDATARECOVERY/CDataRecoveryHandler::GetShutdownByRestartManager
- AFXDATARECOVERY/CDataRecoveryHandler::Initialize
- AFXDATARECOVERY/CDataRecoveryHandler::QueryRestoreAutosavedDocuments
- AFXDATARECOVERY/CDataRecoveryHandler::ReadOpenDocumentList
- AFXDATARECOVERY/CDataRecoveryHandler::RemoveDocumentInfo
- AFXDATARECOVERY/CDataRecoveryHandler::ReopenPreviousDocuments
- AFXDATARECOVERY/CDataRecoveryHandler::RestoreAutosavedDocuments
- AFXDATARECOVERY/CDataRecoveryHandler::SaveOpenDocumentList
- AFXDATARECOVERY/CDataRecoveryHandler::SetAutosaveInterval
- AFXDATARECOVERY/CDataRecoveryHandler::SetAutosavePath
- AFXDATARECOVERY/CDataRecoveryHandler::SetRestartIdentifier
- AFXDATARECOVERY/CDataRecoveryHandler::SetSaveDocumentInfoOnIdle
- AFXDATARECOVERY/CDataRecoveryHandler::SetShutdownByRestartManager
- AFXDATARECOVERY/CDataRecoveryHandler::UpdateDocumentInfo
dev_langs:
- C++
helpviewer_keywords:
- CDataRecoveryHandler class
ms.assetid: 7794802c-e583-4eba-90b9-2fed1a161f9c
caps.latest.revision: 18
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
ms.openlocfilehash: c2a99e32a88b8cb3f12d0961451025596886abb0
ms.lasthandoff: 02/24/2017

---
# <a name="cdatarecoveryhandler-class"></a>CDataRecoveryHandler クラス
`CDataRecoveryHandler`自動保存を文書化し、アプリケーションが予期せず終了した場合に復元します。  
  
## <a name="syntax"></a>構文  
  
```  
class CDataRecoveryHandler : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="constructors"></a>コンストラクター  
  
|||  
|-|-|  
|[CDataRecoveryHandler::CDataRecoveryHandler](#cdatarecoveryhandler)|`CDataRecoveryHandler` オブジェクトを構築します。|  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[CDataRecoveryHandler::AutosaveAllDocumentInfo](#autosavealldocumentinfo)|登録されている各ファイルの自動保存、`CDataRecoveryHandler`クラスです。|  
|[CDataRecoveryHandler::AutosaveDocumentInfo](#autosavedocumentinfo)|指定したドキュメントを自動保存します。|  
|[CDataRecoveryHandler::CreateDocumentInfo](#createdocumentinfo)|開いているドキュメントの一覧にドキュメントを追加します。|  
|[CDataRecoveryHandler::DeleteAllAutosavedFiles](#deleteallautosavedfiles)|現在の自動保存されたファイルをすべて削除します。|  
|[CDataRecoveryHandler::DeleteAutosavedFile](#deleteautosavedfile)|指定された自動保存ファイルを削除します。|  
|[CDataRecoveryHandler::GenerateAutosaveFileName](#generateautosavefilename)|指定されたドキュメントのファイル名に関連付けられている自動保存ファイルの名前を生成します。|  
|[CDataRecoveryHandler::GetAutosaveInterval](#getautosaveinterval)|自動保存の試行間隔を返します。|  
|[CDataRecoveryHandler::GetAutosavePath](#getautosavepath)|自動保存されたファイルのパスを返します。|  
|[CDataRecoveryHandler::GetDocumentListName](#getdocumentlistname)|ドキュメントの名前を取得、`CDocument`オブジェクトです。|  
|[CDataRecoveryHandler::GetNormalDocumentTitle](#getnormaldocumenttitle)|指定したドキュメントの通常のタイトルを取得します。|  
|[CDataRecoveryHandler::GetRecoveredDocumentTitle](#getrecovereddocumenttitle)|作成し、回復されたドキュメントのタイトルを返します。|  
|[CDataRecoveryHandler::GetRestartIdentifier](#getrestartidentifier)|アプリケーションの一意の再起動の識別子を取得します。|  
|[CDataRecoveryHandler::GetSaveDocumentInfoOnIdle](#getsavedocumentinfoonidle)|示すかどうか、`CDataRecoveryHandler`現在アイドル ループの自動保存を実行します。|  
|[CDataRecoveryHandler::GetShutdownByRestartManager](#getshutdownbyrestartmanager)|再起動マネージャーのアプリケーションを終了する原因となったかどうかを示します。|  
|[CDataRecoveryHandler::Initialize](#initialize)|`CDataRecoveryHandler` を初期化します。|  
|[CDataRecoveryHandler::QueryRestoreAutosavedDocuments](#queryrestoreautosaveddocuments)|各ドキュメントをユーザーにダイアログ ボックスを表示、`CDataRecoveryHandler`自動保存します。 ダイアログ ボックスでは、自動保存されたドキュメントを復元するかどうかを決定します。|  
|[CDataRecoveryHandler::ReadOpenDocumentList](#readopendocumentlist)|レジストリから開いているドキュメントの一覧を読み込みます。|  
|[CDataRecoveryHandler::RemoveDocumentInfo](#removedocumentinfo)|指定されたドキュメントを開いているドキュメントの一覧から削除します。|  
|[CDataRecoveryHandler::ReopenPreviousDocuments](#reopenpreviousdocuments)|既に開いているドキュメントを開きます。|  
|[CDataRecoveryHandler::RestoreAutosavedDocuments](#restoreautosaveddocuments)|ユーザー入力に基づいて自動保存されたドキュメントを復元します。|  
|[CDataRecoveryHandler::SaveOpenDocumentList](#saveopendocumentlist)|現在開いているドキュメントの一覧を Windows レジストリに保存します。|  
|[CDataRecoveryHandler::SetAutosaveInterval](#setautosaveinterval)|ミリ秒単位での自動保存サイクルの間隔を設定します。|  
|[CDataRecoveryHandler::SetAutosavePath](#setautosavepath)|自動保存されたファイルが格納されているディレクトリを設定します。|  
|[CDataRecoveryHandler::SetRestartIdentifier](#setrestartidentifier)|このインスタンスの一意の再起動の識別子を設定、`CDataRecoveryHandler`です。|  
|[CDataRecoveryHandler::SetSaveDocumentInfoOnIdle](#setsavedocumentinfoonidle)|設定するかどうか、`CDataRecoveryHandler`現在アイドル サイクル中に、開いているドキュメントの情報を Windows レジストリに保存します。|  
|[CDataRecoveryHandler::SetShutdownByRestartManager](#setshutdownbyrestartmanager)|再起動マネージャーによって、アプリケーションの前回の終了が発生したかどうかを設定します。|  
|[CDataRecoveryHandler::UpdateDocumentInfo](#updatedocumentinfo)|ユーザーが保存されるため、ドキュメントの情報を更新します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|||  
|-|-|  
|m_bRestoringPreviousOpenDocs|データ復元ハンドラーが既に開いているドキュメントを再度開かれますかどうかを示します。|  
|m_bSaveDocumentInfoOnIdle|次のアイドル ループでデータ回復のハンドラーの自動保存がドキュメントかどうかを示します。|  
|m_bShutdownByRestartManager|再起動マネージャー アプリケーションを終了するかどうかを示します。|  
|m_dwRestartManagerSupportFlags|アプリケーションの再起動マネージャーをサポートする内容を示すフラグを提供します。|  
|m_lstAutosavesToDelete|元のドキュメントを閉じたときに削除されなかった自動保存されたファイルの一覧。 アプリケーションを終了すると、ファイルを削除する再起動マネージャー再試行します。|  
|m_mapDocNameToAutosaveName|自動保存されたファイル名にドキュメント名のマップです。|  
|m_mapDocNameToDocumentPtr|ドキュメント名のマップ、 [CDocument](../../mfc/reference/cdocument-class.md)ポインター。|  
|m_mapDocNameToRestoreBool|自動保存されたドキュメントを復元するかどうかを示すブール値パラメーターのドキュメント名のマップです。|  
|m_mapDocumentPtrToDocName|マップ、`CDocument`ドキュメント名へのポインター。|  
|m_mapDocumentPtrToDocTitle|マップ、`CDocument`ドキュメント タイトルへのポインター。 これらのタイトルは、ファイルを保存するために使用されます。|  
|m_nAutosaveInterval|自動保存の間隔をミリ秒単位の時間。|  
|m_nTimerID|自動保存タイマーの識別子です。|  
|m_strAutosavePath|自動保存されたドキュメントが格納されている場所です。|  
|m_strRestartIdentifier|再起動マネージャーの GUID の文字列表現。|  
  
## <a name="remarks"></a>コメント  
 再起動マネージャーを使用して、`CDataRecoveryHandler`を保持するクラスに追跡をすべての開いているドキュメントと自動保存を必要に応じて。 自動保存を有効にするには、 [CDataRecoveryHandler::SetSaveDocumentInfoOnIdle](#setsavedocumentinfoonidle)メソッドです。 このメソッドにより、`CDataRecoveryHandler`を次のアイドル ループの自動保存を実行します。 再起動マネージャー呼び出し`SetSaveDocumentInfoOnIdle`ときに、`CDataRecoveryHandler`自動保存を実行する必要があります。  
  
 すべてのメソッドの`CDataRecoveryHandler`クラスは、仮想です。 独自のカスタム データ回復のハンドラーを作成するには、このクラスのメソッドをオーバーライドします。 データ回復ハンドラーの作成や、再起動マネージャーをを除きには、CDataRecoveryHandler がインスタンス化できません。 [CWinApp クラス](../../mfc/reference/cwinapp-class.md)を作成、`CDataRecoveryHandler`オブジェクトが必要です。  
  
 使用する前に、`CDataRecoveryHandler`オブジェクトを呼び出す必要があります[CDataRecoveryHandler::Initialize](#initialize)します。  
  
 `CDataRecoveryHandler`クラスは、再起動マネージャーに密接に関連して`CDataRecoveryHandler`グローバル パラメーターに依存する`m_dwRestartManagerSupportFlags`です。 このパラメーターは、再起動マネージャーがどのようなアクセス許可と、アプリケーションと対話する方法を決定します。 再起動マネージャーを既存のアプリケーションに組み込むに割り当てる必要があります`m_dwRestartManagerSupportFlags`メイン アプリケーションのコンス トラクターに適切な値です。 再起動マネージャーを使用する方法の詳細については、次を参照してください。[方法: 再起動マネージャーのサポートの追加](../../mfc/how-to-add-restart-manager-support.md)します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdatarecovery.h  
  
##  <a name="autosavealldocumentinfo"></a>CDataRecoveryHandler::AutosaveAllDocumentInfo  
 登録されている各ファイルの自動保存、`CDataRecoveryHandler`クラスです。  
  
```  
virtual BOOL AutosaveAllDocumentInfo();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`場合、`CDataRecoveryHandler`すべてのドキュメントの保存`FALSE`任意のドキュメントが保存されていない場合。  
  
### <a name="remarks"></a>コメント  
 このメソッドが戻る`TRUE`ドキュメントを保存する必要がない場合。 返します`TRUE`を取得する場合は、すべてのドキュメントを保存せず、`CWinApp`または`CDocManager`のアプリケーション エラーが発生します。  
  
 か、このメソッドを使用する`AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART`または`AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL`で設定する必要があります`m_dwRestartManagerSupportFlags`します。 参照してください[m_dwRestartManagerSupportFlags](#m_dwrestartmanagersupportflags)の詳細。  
  
##  <a name="autosavedocumentinfo"></a>CDataRecoveryHandler::AutosaveDocumentInfo  
 指定したドキュメントを自動保存します。  
  
```  
virtual BOOL AutosaveDocumentInfo(
    CDocument* pDocument,  
    BOOL bResetModifiedFlag = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `pDocument`|ポインター、`CDocument`を保存します。|  
|[入力] `bResetModifiedFlag`|`TRUE`示して、`CDataRecoveryHandler`考慮`pDocument`を変更できます。`FALSE`フレームワークが判断したことを示します`pDocument`変更します。 このフラグの効果についての詳細については、「解説」を参照してください。|  
  
### <a name="return-value"></a>戻り値  
 `TRUE`適切なフラグが設定されている場合、`pDocument`が有効な`CDocument`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 各`CDocument`オブジェクトは、それが最後に保存してから変更されていないことを示すフラグを持ちます。 使用[CDocument::IsModified](../../mfc/reference/cdocument-class.md#ismodified)このフラグの状態を判断します。 場合、`CDocument`が前回保存以降変更されていない`AutosaveDocumentInfo`そのドキュメント用の自動保存されたファイルを削除します。 ドキュメントが最後に保存してから変更されている場合に終了する、閉じる前にドキュメントを保存するユーザーがメッセージを表示します。  
  
> [!NOTE]
>  使用して`bResetModifiedFlag`に変更されていない、ドキュメントの状態を変更することがありますが原因でユーザー データが失われる。 フレームワーク、ドキュメントが変更されていない場合、終了するユーザーから求められませんを保存します。  
  
 このメソッドで例外をスローする、 [ASSERT](http://msdn.microsoft.com/library/1e70902d-d58c-4e7b-9f69-2aeb6cbe476c)マクロ場合`pDocument`が無効です`CDocument`オブジェクトです。  
  
 か、このメソッドを使用する`AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART`または`AFX_RESTARTMANAGER_AUTOSAVE_AT_INTERVAL`で設定する必要があります`m_dwRestartManagerSupportFlags`します。   
  
##  <a name="cdatarecoveryhandler"></a>CDataRecoveryHandler::CDataRecoveryHandler  
 `CDataRecoveryHandler` オブジェクトを構築します。  
  
```  
CDataRecoveryHandler(
    DWORD dwRestartManagerSupportFlags,  
    int nAutosaveInterval);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `dwRestartManagerSupportFlags`|再起動マネージャーのオプションがサポートされていることを示します。|  
|[入力] `nAutosaveInterval`|自動保存までの時間。 このパラメーターはミリ秒です。|  
  
### <a name="remarks"></a>コメント  
 MFC フレームワークが自動的に作成、`CDataRecoveryHandler`を使用する場合、アプリケーションのオブジェクト、**新しいプロジェクト**ウィザード。 データの回復の動作をカスタマイズすることも、再起動マネージャーをする場合は、しない限り、作成してはいけない、`CDataRecoveryHandler`オブジェクトです。  
  
  
##  <a name="createdocumentinfo"></a>CDataRecoveryHandler::CreateDocumentInfo  
 開いているドキュメントの一覧にドキュメントを追加します。  
  
```  
virtual BOOL CreateDocumentInfo(CDocument* pDocument);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `pDocument`|ポインター、`CDocument`です。 このメソッドは、このドキュメントの情報を作成`CDocument`します。|  
  
### <a name="return-value"></a>戻り値  
 既定の実装では、`TRUE` が返されます。  
  
### <a name="remarks"></a>コメント  
 このメソッドはチェック場合`pDocument`ドキュメントを追加する前に、ドキュメントの一覧にあります。 場合`pDocument`は既にこのメソッドの一覧で、自動保存されたファイルに関連付けられている削除`pDocument`します。  
  
 か、このメソッドを使用する`AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART`または`AFX_RESTARTMANAGER_AUTOSAVE_AT_INTERVAL`で設定する必要があります`m_dwRestartManagerSupportFlags`します。 
  
##  <a name="deleteallautosavedfiles"></a>CDataRecoveryHandler::DeleteAllAutosavedFiles  
 現在の自動保存されたファイルをすべて削除します。  
  
```  
virtual BOOL DeleteAllAutosavedFiles();
```  
  
### <a name="return-value"></a>戻り値  
 既定の実装を常に`TRUE`します。  
  
##  <a name="deleteautosavedfile"></a>CDataRecoveryHandler::DeleteAutosavedFile  
 指定された自動保存ファイルを削除します。  
  
```  
virtual BOOL DeleteAutosavedFile(const CString& strAutosavedFile);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `strAutosavedFile`|自動保存されたファイル名を含む文字列です。|  
  
### <a name="return-value"></a>戻り値  
 既定の実装を常に戻り`TRUE`します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、自動保存されたファイルを削除できない場合は、一覧で、ファイルの名前を保存します。 デストラクター、`CDataRecoveryHandler`リストで指定された各自動保存されたファイルを削除しようとしています。  
  
##  <a name="generateautosavefilename"></a>CDataRecoveryHandler::GenerateAutosaveFileName  
 指定されたドキュメントのファイル名に関連付けられている自動保存ファイルの名前を生成します。  
  
```  
virtual CString GenerateAutosaveFileName(const CString& strDocumentName) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `strDocumentName`  
 ドキュメントの名前を表す文字列。 `GenerateAutosaveFileName`このドキュメントの名前を使用すると、対応する自動保存ファイル名を生成します。  
  
### <a name="return-value"></a>戻り値  
 自動保存ファイル名から生成された`strDocumentName`します。  
  
### <a name="remarks"></a>コメント  
 各ドキュメント名では、自動保存ファイル名と一対一のマッピングがいます。  
  
##  <a name="getautosaveinterval"></a>CDataRecoveryHandler::GetAutosaveInterval  
 自動保存の試行間隔を返します。  
  
```  
virtual int GetAutosaveInterval() const;  
```  
  
### <a name="return-value"></a>戻り値  
 自動保存の間隔をミリ秒単位の数が試行されます。  
  
##  <a name="getautosavepath"></a>CDataRecoveryHandler::GetAutosavePath  
 自動保存されたファイルのパスを返します。  
  
```  
virtual CString GetAutosavePath() const;  
```  
  
### <a name="return-value"></a>戻り値  
 自動保存されたドキュメントが格納されている場所です。  
  
##  <a name="getdocumentlistname"></a>CDataRecoveryHandler::GetDocumentListName  
 ドキュメントの名前を取得、`CDocument`オブジェクトです。  
  
```  
virtual CString GetDocumentListName(CDocument* pDocument) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `pDocument`|ポインター、`CDocument`です。 `GetDocumentListName`このドキュメントの名前を取得`CDocument`します。|  
  
### <a name="return-value"></a>戻り値  
 ドキュメントの名前から`pDocument`します。  
  
### <a name="remarks"></a>コメント  
 `CDataRecoveryHandler`ドキュメント名でキーとして使用`m_mapDocNameToAutosaveName`、 `m_mapDocNameToDocumentPtr`、および`m_mapDocNameToRestoreBool`です。 これらのパラメーターを有効にする、`CDataRecoveryHandler`を監視する`CDocument`オブジェクトや自動保存ファイル名は、自動保存の設定です。  
  
##  <a name="getnormaldocumenttitle"></a>CDataRecoveryHandler::GetNormalDocumentTitle  
 指定したドキュメントの通常のタイトルを取得します。  
  
```  
virtual CString GetNormalDocumentTitle(CDocument* pDocument);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `pDocument`|ポインター、`CDocument`です。|  
  
### <a name="return-value"></a>戻り値  
 指定したドキュメントの通常のタイトル。  
  
### <a name="remarks"></a>コメント  
 ドキュメントの通常のタイトルは、通常パスを含まないドキュメントのファイル名です。 これは、タイトル、**ファイル名**のフィールド、**名前を付けて保存** ダイアログ ボックス。  
  
##  <a name="getrecovereddocumenttitle"></a>CDataRecoveryHandler::GetRecoveredDocumentTitle  
 作成し、回復されたドキュメントのタイトルを返します。  
  
```  
virtual CString GetRecoveredDocumentTitle(const CString& strDocumentTitle) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `strDocumentTitle`  
 ドキュメントの通常のタイトル。  
  
### <a name="return-value"></a>戻り値  
 回復されたドキュメント タイトルです。  
  
### <a name="remarks"></a>コメント  
 既定では、ドキュメントの回復されたタイトルには通常のタイトルを**[回復]**が追加されます。 回復したタイトルが、ユーザーに表示されるときに、`CDataRecoveryHandler`自動保存されたドキュメントを復元するユーザーのクエリを実行します。  
  
##  <a name="getrestartidentifier"></a>CDataRecoveryHandler::GetRestartIdentifier  
 アプリケーションの一意の再起動の識別子を取得します。  
  
```  
virtual CString GetRestartIdentifier() const;  
```  
  
### <a name="return-value"></a>戻り値  
 一意の識別子を再起動します。  
  
### <a name="remarks"></a>コメント  
 再起動識別子は、アプリケーションを実行するたびに一意です。  
  
 `CDataRecoveryHandler`レジストリの現在開いているドキュメントに関する情報を格納します。 再起動マネージャーは、アプリケーションを終了するし、再起動し、再起動識別子を提供、`CDataRecoveryHandler`です。 `CDataRecoveryHandler`再起動識別子を使用して、既に開いているドキュメントの一覧を取得します。 これにより、`CDataRecoveryHandler`検索し、自動保存されたファイルを復元しようとします。  
  
##  <a name="getsavedocumentinfoonidle"></a>CDataRecoveryHandler::GetSaveDocumentInfoOnIdle  
 示すかどうか、`CDataRecoveryHandler`現在アイドル ループの自動保存を実行します。  
  
```  
virtual BOOL GetSaveDocumentInfoOnIdle() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`示す、`CDataRecoveryHandler`現在のアイドル ループの自動保存`FALSE`そうでないことを示します。  
  
##  <a name="getshutdownbyrestartmanager"></a>CDataRecoveryHandler::GetShutdownByRestartManager  
 再起動マネージャーのアプリケーションを終了する原因となったかどうかを示します。  
  
```  
virtual BOOL GetShutdownByRestartManager() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`再起動マネージャーのアプリケーションを終了する原因となったことを示します。`FALSE`しないことを示します。  
  
##  <a name="initialize"></a>CDataRecoveryHandler::Initialize  
 `CDataRecoveryHandler` を初期化します。  
  
```  
virtual BOOL Initialize();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`初期化が成功した場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 初期化プロセスでは、レジストリからの自動保存ファイルを保存するためのパスを読み込みます。 場合、`Initialize`メソッドがこのディレクトリを見つけられない、またはパスがあるかどうか`NULL`、`Initialize`失敗し、返す`FALSE`します。  
  
 使用[CDataRecoveryHandler::SetAutosavePath](#setautosavepath) 、アプリケーションが初期化された後に自動保存のパスを変更する、`CDataRecoveryHandler`です。  
  
 `Initialize`メソッドも次の自動保存が発生したときに監視するタイマーを開始します。 使用[CDataRecoveryHandler::SetAutosaveInterval](#setautosaveinterval) 、アプリケーションが初期化された後に自動保存の間隔を変更する、`CDataRecoveryHandler`です。  
  
##  <a name="queryrestoreautosaveddocuments"></a>CDataRecoveryHandler::QueryRestoreAutosavedDocuments  
 各ドキュメントをユーザーにダイアログ ボックスを表示、`CDataRecoveryHandler`自動保存します。 ダイアログ ボックスでは、自動保存されたドキュメントを復元するかどうかを決定します。  
  
```  
virtual void QueryRestoreAutosavedDocuments();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドを表示、アプリケーションが Unicode の場合、 [CTaskDialog](../../mfc/reference/ctaskdialog-class.md)をユーザーにします。 それ以外の場合、フレームワークを使用して[AfxMessageBox](../../mfc/reference/cstring-formatting-and-message-box-display.md#afxmessagebox)ユーザーを照会します。  
  
 後に`QueryRestoreAutosavedDocuments`すべての応答を収集してユーザーからメンバー変数に、情報が格納`m_mapDocNameToRestoreBool`します。 このメソッドでは、自動保存されたドキュメントは復元されません。  
  
##  <a name="readopendocumentlist"></a>CDataRecoveryHandler::ReadOpenDocumentList  
 レジストリから開いているドキュメントの一覧を読み込みます。  
  
```  
virtual BOOL ReadOpenDocumentList();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`示します`ReadOpenDocumentList`に少なくとも&1; つのドキュメントの情報をレジストリから読み込まれました。`FALSE`ドキュメントの情報が読み込まれていないことを示します。  
  
### <a name="remarks"></a>コメント  
 この関数は、開いているドキュメントの情報をレジストリから読み込むし、メンバー変数に格納`m_mapDocNameToAutosaveName`します。  
  
 後に`ReadOpenDocumentList`はすべてのデータを読み込み、レジストリからドキュメントの情報を削除します。  
  
##  <a name="removedocumentinfo"></a>CDataRecoveryHandler::RemoveDocumentInfo  
 指定されたドキュメントを開いているドキュメントの一覧から削除します。  
  
```  
virtual BOOL RemoveDocumentInfo(CDocument* pDocument);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `pDocument`|削除するドキュメントへのポインター。|  
  
### <a name="return-value"></a>戻り値  
 `TRUE`場合`pDocument`は、リストから削除されました`FALSE`場合はエラーが発生しました。  
  
### <a name="remarks"></a>コメント  
 ユーザーがドキュメントを閉じると、フレームワークは、開いているドキュメントの一覧から削除するのにこのメソッドを使用します。  
  
 場合`RemoveDocumentInfo`を見つけられない`pDocument`、開いているドキュメントの一覧では何もして返します`TRUE`します。  
  
 このメソッドを使用して`AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES`で設定する必要があります`m_dwRestartManagerSupportFlags`します。   
  
##  <a name="reopenpreviousdocuments"></a>CDataRecoveryHandler::ReopenPreviousDocuments  
 既に開いているドキュメントを開きます。  
  
```  
virtual BOOL ReopenPreviousDocuments();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`少なくとも&1; つのドキュメントが開いていた場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、既に開いているドキュメントの最新の保存を開きます。 ドキュメントが保存されていない場合や自動保存された、`ReopenPreviousDocuments`ファイルの種類のテンプレートに基づく、空白の文書を開きます。  
  
 このメソッドを使用して`AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES`で設定する必要があります`m_dwRestartManagerSupportFlags`します。 このパラメーターが設定されていない場合`ReopenPreviousDocuments`は何もしませんし、返します`FALSE`します。  
  
 既に開いているドキュメントの一覧に格納されたドキュメントがない場合`ReopenPreviousDocuments`は何もしませんし、返します`FALSE`します。  
  
##  <a name="restoreautosaveddocuments"></a>CDataRecoveryHandler::RestoreAutosavedDocuments  
 ユーザー入力に基づいて自動保存されたドキュメントを復元します。  
  
```  
virtual BOOL RestoreAutosavedDocuments();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`このメソッドは、ドキュメントを正常に復元します。 場合、  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出す[CDataRecoveryHandler::QueryRestoreAutosavedDocuments](#queryrestoreautosaveddocuments)を復元する必要がどのドキュメントをユーザーを決定します。 ユーザーが、自動保存されたドキュメントを回復することに決定した場合は`RestoreAutosavedDocuments`自動保存ファイルを削除します。 それ以外の場合、`RestoreAutosavedDocuments`を自動保存されたバージョンと、開いているドキュメントを置き換えます。  
  
 か、このメソッドを使用する`AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES`または`AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES`で設定する必要があります`m_dwRestartManagerSupportFlags`します。   
  
##  <a name="saveopendocumentlist"></a>CDataRecoveryHandler::SaveOpenDocumentList  
 現在開いているドキュメントの一覧を Windows レジストリに保存します。  
  
```  
virtual BOOL SaveOpenDocumentList();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`開いているドキュメントを保存することがない場合、または正常に保存されている場合。 `FALSE`場合、レジストリに保存するドキュメントがあるが、エラーが発生したため、保存されませんでした。  
  
### <a name="remarks"></a>コメント  
 再起動マネージャー呼び出し`SaveOpenDocumentList`アプリケーションが予期せず終了すると、またはアップグレードのための終了時にします。 使用して、アプリケーションが再起動したら、 [CDataRecoveryHandler::ReadOpenDocumentList](#readopendocumentlist)開いているドキュメントの一覧を取得します。  
  
 このメソッドは、開いているドキュメントの一覧のみを保存します。 メソッド[CDataRecoveryHandler::AutosaveDocumentInfo](#autosavedocumentinfo)ドキュメントそのものの保存を担当します。  
  
##  <a name="setautosaveinterval"></a>CDataRecoveryHandler::SetAutosaveInterval  
 ミリ秒単位での自動保存サイクルの間隔を設定します。  
  
```  
Virtual void SetAutosaveInterval(int nAutosaveInterval);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nAutosaveInterval`  
 ミリ秒単位での新しい自動保存の間隔。  
  
##  <a name="setautosavepath"></a>CDataRecoveryHandler::SetAutosavePath  
 自動保存されたファイルが格納されているディレクトリを設定します。  
  
```  
virtual void SetAutosavePath(const CString& strAutosavePath);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `strAutosavePath`|自動保存ファイルの保存場所のパス。|  
  
### <a name="remarks"></a>コメント  
 自動保存ディレクトリを変更するファイルは移動されません現在自動保存します。  
  
##  <a name="setrestartidentifier"></a>CDataRecoveryHandler::SetRestartIdentifier  
 このインスタンスの一意の再起動の識別子を設定、`CDataRecoveryHandler`です。  
  
```  
virtual void SetRestartIdentifier(const CString& strRestartIdentifier);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `strRestartIdentifier`|再起動マネージャーの一意の識別子。|  
  
### <a name="remarks"></a>コメント  
 再起動マネージャーは、開いているドキュメントに関する情報をレジストリに記録します。 この情報は、一意の再起動識別子と共にキーとして保存されます。 再起動識別子は、アプリケーションの各インスタンスに対して一意であるため、アプリケーションの複数のインスタンスに予期せず終了した場合し、再起動マネージャーには、それぞれの回復できます。  
  
##  <a name="setsavedocumentinfoonidle"></a>CDataRecoveryHandler::SetSaveDocumentInfoOnIdle  
 設定するかどうか、`CDataRecoveryHandler`現在アイドル サイクル中に、開いているドキュメントの情報を Windows レジストリに保存します。  
  
```  
virtual void SetSaveDocumentInfoOnIdle(BOOL bSaveOnIdle);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `bSaveOnIdle`|`TRUE`現在のアイドル サイクル中にドキュメント情報を保存するには`FALSE to not perform a save`.|  
  
##  <a name="setshutdownbyrestartmanager"></a>CDataRecoveryHandler::SetShutdownByRestartManager  
 再起動マネージャーによって、アプリケーションの前回の終了が発生したかどうかを設定します。  
  
```  
virtual void SetShutdownByRestartManager(BOOL bShutdownByRestartManager);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `bShutdownByRestartManager`|`TRUE`再起動マネージャーのアプリケーションを終了する原因となったことを示すために`FALSE`を別の理由で、アプリケーションが終了していることを示します。|  
  
### <a name="remarks"></a>コメント  
 フレームワークでは、前回の終了が予想されるかどうか、または再起動マネージャーによって開始されたかどうかに基づいて異なる方法では動作します。  
  
##  <a name="updatedocumentinfo"></a>CDataRecoveryHandler::UpdateDocumentInfo  
 ユーザーが保存されるため、ドキュメントの情報を更新します。  
  
```  
virtual BOOL UpdateDocumentInfo(CDocument* pDocument);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `pDocument`|保存されたドキュメントへのポインター。|  
  
### <a name="return-value"></a>戻り値  
 `TRUE`このメソッドは、自動保存されたドキュメントを削除し、ドキュメントの情報を更新する場合`FALSE`場合はエラーが発生しました。  
  
### <a name="remarks"></a>コメント  
 ドキュメントを保存すると、不要になったために、アプリケーションは、自動保存されたファイルを削除します。 `UpdateDocumentInfo`呼び出して、自動保存されたファイルを削除[CDataRecoveryHandler::RemoveDocumentInfo](#removedocumentinfo)します。 `UpdateDocumentInfo`情報を追加`pDocument`の一覧に現在開くドキュメント`RemoveDocumentInfo`が保存されている、その情報を削除を開いたままです。  
  
 このメソッドを使用して`AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES`で設定する必要があります`m_dwRestartManagerSupportFlags`します。   
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [方法: 再起動マネージャーのサポートを追加](../../mfc/how-to-add-restart-manager-support.md)


