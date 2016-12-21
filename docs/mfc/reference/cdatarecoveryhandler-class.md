---
title: "CDataRecoveryHandler クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDataRecoveryHandler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDataRecoveryHandler クラス"
ms.assetid: 7794802c-e583-4eba-90b9-2fed1a161f9c
caps.latest.revision: 18
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDataRecoveryHandler クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CDataRecoveryHandler` は、アプリケーションが予期せずに終了した場合にドキュメントを自動保存し、復元します。  
  
## 構文  
  
```  
class CDataRecoveryHandler : public CObject  
```  
  
## メンバー  
  
### コンストラクター  
  
|||  
|-|-|  
|[CDataRecoveryHandler::CDataRecoveryHandler](../Topic/CDataRecoveryHandler::CDataRecoveryHandler.md)|`CDataRecoveryHandler` オブジェクトを構築します。|  
  
### メソッド  
  
|||  
|-|-|  
|[CDataRecoveryHandler::AutosaveAllDocumentInfo](../Topic/CDataRecoveryHandler::AutosaveAllDocumentInfo.md)|`CDataRecoveryHandler` クラスに登録されている各ファイルを自動保存します。|  
|[CDataRecoveryHandler::AutosaveDocumentInfo](../Topic/CDataRecoveryHandler::AutosaveDocumentInfo.md)|指定されたドキュメントを自動保存します。|  
|[CDataRecoveryHandler::CreateDocumentInfo](../Topic/CDataRecoveryHandler::CreateDocumentInfo.md)|開いているドキュメントのリストにドキュメントを追加します。|  
|[CDataRecoveryHandler::DeleteAllAutosavedFiles](../Topic/CDataRecoveryHandler::DeleteAllAutosavedFiles.md)|現在の自動保存ファイルをすべて削除します。|  
|[CDataRecoveryHandler::DeleteAutosavedFile](../Topic/CDataRecoveryHandler::DeleteAutosavedFile.md)|指定された自動保存ファイルを削除します。|  
|[CDataRecoveryHandler::GenerateAutosaveFileName](../Topic/CDataRecoveryHandler::GenerateAutosaveFileName.md)|指定されたドキュメント ファイル名に関連付けられた自動保存ファイルの名前を生成します。|  
|[CDataRecoveryHandler::GetAutosaveInterval](../Topic/CDataRecoveryHandler::GetAutosaveInterval.md)|自動保存の試行間隔を返します。|  
|[CDataRecoveryHandler::GetAutosavePath](../Topic/CDataRecoveryHandler::GetAutosavePath.md)|自動保存ファイルのパスを返します。|  
|[CDataRecoveryHandler::GetDocumentListName](../Topic/CDataRecoveryHandler::GetDocumentListName.md)|`CDocument` オブジェクトからドキュメント名を取得します。|  
|[CDataRecoveryHandler::GetNormalDocumentTitle](../Topic/CDataRecoveryHandler::GetNormalDocumentTitle.md)|指定されたドキュメントの通常のタイトルを取得します。|  
|[CDataRecoveryHandler::GetRecoveredDocumentTitle](../Topic/CDataRecoveryHandler::GetRecoveredDocumentTitle.md)|復元されたドキュメントのタイトルを作成して返します。|  
|[CDataRecoveryHandler::GetRestartIdentifier](../Topic/CDataRecoveryHandler::GetRestartIdentifier.md)|アプリケーションの一意の再起動識別子を取得します。|  
|[CDataRecoveryHandler::GetSaveDocumentInfoOnIdle](../Topic/CDataRecoveryHandler::GetSaveDocumentInfoOnIdle.md)|`CDataRecoveryHandler` が現在のアイドル ループで自動保存を行うかどうかを示します。|  
|[CDataRecoveryHandler::GetShutdownByRestartManager](../Topic/CDataRecoveryHandler::GetShutdownByRestartManager.md)|再起動マネージャーによってアプリケーションが終了されたかどうかを示します。|  
|[CDataRecoveryHandler::Initialize](../Topic/CDataRecoveryHandler::Initialize.md)|`CDataRecoveryHandler` を初期化します。|  
|[CDataRecoveryHandler::QueryRestoreAutosavedDocuments](../Topic/CDataRecoveryHandler::QueryRestoreAutosavedDocuments.md)|`CDataRecoveryHandler` によって自動保存された各ドキュメントについてユーザーにダイアログ ボックスを表示します。  このダイアログ ボックスで、ユーザーが自動保存されたドキュメントを復元するかどうかを確認します。|  
|[CDataRecoveryHandler::ReadOpenDocumentList](../Topic/CDataRecoveryHandler::ReadOpenDocumentList.md)|開いているドキュメントのリストをレジストリから読み込みます。|  
|[CDataRecoveryHandler::RemoveDocumentInfo](../Topic/CDataRecoveryHandler::RemoveDocumentInfo.md)|開いているドキュメントのリストから指定されたドキュメントを削除します。|  
|[CDataRecoveryHandler::ReopenPreviousDocuments](../Topic/CDataRecoveryHandler::ReopenPreviousDocuments.md)|以前に開いていたドキュメントを開きます。|  
|[CDataRecoveryHandler::RestoreAutosavedDocuments](../Topic/CDataRecoveryHandler::RestoreAutosavedDocuments.md)|ユーザーの入力に基づいて自動保存ドキュメントを復元します。|  
|[CDataRecoveryHandler::SaveOpenDocumentList](../Topic/CDataRecoveryHandler::SaveOpenDocumentList.md)|現在の開いているドキュメントのリストを Windows レジストリに保存します。|  
|[CDataRecoveryHandler::SetAutosaveInterval](../Topic/CDataRecoveryHandler::SetAutosaveInterval.md)|自動保存サイクル間の時間をミリ秒単位で設定します。|  
|[CDataRecoveryHandler::SetAutosavePath](../Topic/CDataRecoveryHandler::SetAutosavePath.md)|自動保存ファイルが格納されるディレクトリを設定します。|  
|[CDataRecoveryHandler::SetRestartIdentifier](../Topic/CDataRecoveryHandler::SetRestartIdentifier.md)|`CDataRecoveryHandler` のこのインスタンスに対して一意の再起動識別子を設定します。|  
|[CDataRecoveryHandler::SetSaveDocumentInfoOnIdle](../Topic/CDataRecoveryHandler::SetSaveDocumentInfoOnIdle.md)|`CDataRecoveryHandler` が、現在のアイドル サイクル中に、開いているドキュメントの情報を Windows レジストリに保存するかどうかを設定します。|  
|[CDataRecoveryHandler::SetShutdownByRestartManager](../Topic/CDataRecoveryHandler::SetShutdownByRestartManager.md)|前回のアプリケーションの終了が再起動マネージャーによるものかどうかを設定します。|  
|[CDataRecoveryHandler::UpdateDocumentInfo](../Topic/CDataRecoveryHandler::UpdateDocumentInfo.md)|ドキュメントの情報をユーザーが保存したときに更新します。|  
  
### データ メンバー  
  
|||  
|-|-|  
|m\_bRestoringPreviousOpenDocs|データ復元ハンドラーが、前に開いていたドキュメントを再度開くかどうかを示します。|  
|m\_bSaveDocumentInfoOnIdle|データ復元ハンドラーが、次のアイドル ループでドキュメントを自動保存するかどうかを示します。|  
|m\_bShutdownByRestartManager|再起動マネージャーによってアプリケーションが終了されるかどうかを示します。|  
|m\_dwRestartManagerSupportFlags|再起動マネージャーがアプリケーションに対してどのようなサポートを提供するかを示すフラグです。|  
|m\_lstAutosavesToDelete|元のドキュメントを閉じたときに削除されなかった自動保存ファイルのリストです。  アプリケーションの終了時に、再起動マネージャーはファイルの削除を再試行します。|  
|m\_mapDocNameToAutosaveName|ドキュメント名と自動保存ファイル名の対応マップです。|  
|m\_mapDocNameToDocumentPtr|ドキュメント名と [CDocument](../Topic/CDocument%20Class.md) ポインターの対応マップです。|  
|m\_mapDocNameToRestoreBool|ドキュメント名と自動保存ドキュメントを復元するかどうかを示すブール値パラメーターの対応マップです。|  
|m\_mapDocumentPtrToDocName|`CDocument` ポインターとドキュメント名の対応マップです。|  
|m\_mapDocumentPtrToDocTitle|`CDocument` ポインターとドキュメント タイトルの対応マップです。  これらのタイトルは、ファイルの保存に使用されます。|  
|m\_nAutosaveInterval|自動保存の実行間隔です \(ミリ秒単位\)。|  
|m\_nTimerID|自動保存タイマーの識別子です。|  
|m\_strAutosavePath|自動保存ファイルが格納される場所です。|  
|m\_strRestartIdentifier|再起動マネージャーの GUID の文字列形式です。|  
  
## 解説  
 再起動マネージャーは、`CDataRecoveryHandler` クラスを使用して、すべての開いているドキュメントを追跡し、必要に応じてそれらを自動保存します。  自動保存を有効にするには、[CDataRecoveryHandler::SetSaveDocumentInfoOnIdle](../Topic/CDataRecoveryHandler::SetSaveDocumentInfoOnIdle.md) メソッドを使用します。  このメソッドは、次のアイドル ループで自動保存を実行するように `CDataRecoveryHandler` に指示します。  `CDataRecoveryHandler` が自動保存を行う必要がある場合、再起動マネージャーは `SetSaveDocumentInfoOnIdle` を呼び出します。  
  
 `CDataRecoveryHandler` クラスのメソッドはすべて仮想メソッドです。  独自のカスタム データ復元ハンドラーを作成するには、このクラスのメソッドをオーバーライドします。  独自のデータ復元ハンドラーまたは再起動マネージャーを作成しない場合は、CDataRecoveryHandler をインスタンス化しないでください。  [CWinApp クラス](../../mfc/reference/cwinapp-class.md)は、必要に応じて `CDataRecoveryHandler` オブジェクトを作成します。  
  
 `CDataRecoveryHandler` オブジェクトを使用する前に、[CDataRecoveryHandler::Initialize](../Topic/CDataRecoveryHandler::Initialize.md) を呼び出す必要があります。  
  
 `CDataRecoveryHandler` クラスは再起動マネージャーと緊密に結び付いているため、`CDataRecoveryHandler` はグローバル パラメーター `m_dwRestartManagerSupportFlags` に依存します。  このパラメーターは、再起動マネージャーがどのようなアクセス許可を持ち、アプリケーションとどのようにやり取りするかを決定します。  再起動マネージャーを既存のアプリケーションに組み込むには、メイン アプリケーションのコンストラクターで `m_dwRestartManagerSupportFlags` に適切な値を割り当てる必要があります。  再起動マネージャーの使用方法の詳細については、「[方法: 再起動マネージャーのサポートを追加する](../../mfc/how-to-add-restart-manager-support.md)」を参照してください。  
  
## 必要条件  
 **ヘッダー:** afxdatarecovery.h  
  
## 参照  
 [クラス](../Topic/MFC%20Classes.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CObject クラス](../Topic/CObject%20Class.md)   
 [方法: 再起動マネージャーのサポートを追加する](../../mfc/how-to-add-restart-manager-support.md)