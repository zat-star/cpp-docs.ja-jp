---
title: "CDocTemplate クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDocTemplate
- AFXWIN/CDocTemplate
- AFXWIN/CDocTemplate::CDocTemplate
- AFXWIN/CDocTemplate::AddDocument
- AFXWIN/CDocTemplate::CloseAllDocuments
- AFXWIN/CDocTemplate::CreateNewDocument
- AFXWIN/CDocTemplate::CreateNewFrame
- AFXWIN/CDocTemplate::CreateOleFrame
- AFXWIN/CDocTemplate::CreatePreviewFrame
- AFXWIN/CDocTemplate::GetDocString
- AFXWIN/CDocTemplate::GetFirstDocPosition
- AFXWIN/CDocTemplate::GetNextDoc
- AFXWIN/CDocTemplate::InitialUpdateFrame
- AFXWIN/CDocTemplate::LoadTemplate
- AFXWIN/CDocTemplate::MatchDocType
- AFXWIN/CDocTemplate::OpenDocumentFile
- AFXWIN/CDocTemplate::RemoveDocument
- AFXWIN/CDocTemplate::SaveAllModified
- AFXWIN/CDocTemplate::SetContainerInfo
- AFXWIN/CDocTemplate::SetDefaultTitle
- AFXWIN/CDocTemplate::SetPreviewInfo
- AFXWIN/CDocTemplate::SetServerInfo
dev_langs:
- C++
helpviewer_keywords:
- document templates
- templates, document
- CDocTemplate class
ms.assetid: 14b41a1f-bf9d-4eac-b6a8-4c54ffcc77f6
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
ms.openlocfilehash: 56ad45a061986c320e14054a2c77683cb5d89ac2
ms.lasthandoff: 02/24/2017

---
# <a name="cdoctemplate-class"></a>CDocTemplate クラス
ドキュメント テンプレートの基本的な機能を定義する抽象基底クラスです。  
  
## <a name="syntax"></a>構文  
  
```  
class CDocTemplate : public CCmdTarget  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="protected-constructors"></a>プロテクト コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CDocTemplate::CDocTemplate](#cdoctemplate)|`CDocTemplate` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDocTemplate::AddDocument](#adddocument)|テンプレートにドキュメントを追加します。|  
|[CDocTemplate::CloseAllDocuments](#closealldocuments)|このテンプレートに関連付けられているすべてのドキュメントを閉じます。|  
|[CDocTemplate::CreateNewDocument](#createnewdocument)|文書を新規に作成します。|  
|[CDocTemplate::CreateNewFrame](#createnewframe)|ドキュメントとビューを含む、新しいフレーム ウィンドウを作成します。|  
|[CDocTemplate::CreateOleFrame](#createoleframe)|OLE が有効なフレーム ウィンドウを作成します。|  
|[CDocTemplate::CreatePreviewFrame](#createpreviewframe)|リッチ プレビューに使用される子フレームを作成します。|  
|[CDocTemplate::GetDocString](#getdocstring)|ドキュメントの種類に関連付けられている文字列を取得します。|  
|[CDocTemplate::GetFirstDocPosition](#getfirstdocposition)|このテンプレートに関連付けられている最初のドキュメントの位置を取得します。|  
|[CDocTemplate::GetNextDoc](#getnextdoc)|ドキュメントと、次の位置を取得します。|  
|[CDocTemplate::InitialUpdateFrame](#initialupdateframe)|フレーム ウィンドウを初期化し、必要に応じてようになります。|  
|[CDocTemplate::LoadTemplate](#loadtemplate)|リソースを読み込み、指定された`CDocTemplate`またはその派生クラスです。|  
|[CDocTemplate::MatchDocType](#matchdoctype)|ドキュメントの種類とこのテンプレートの間の一致で信頼度を決定します。|  
|[CDocTemplate::OpenDocumentFile](#opendocumentfile)|パス名で指定されたファイルを開きます。|  
|[CDocTemplate::RemoveDocument](#removedocument)|テンプレートからドキュメントを削除します。|  
|[CDocTemplate::SaveAllModified](#saveallmodified)|変更されているこのテンプレートに関連付けられているすべてのドキュメントを保存します。|  
|[CDocTemplate::SetContainerInfo](#setcontainerinfo)|インプレース OLE アイテムを編集するときは、OLE コンテナーのリソースを決定します。|  
|[CDocTemplate::SetDefaultTitle](#setdefaulttitle)|ドキュメント ウィンドウのタイトル バーに既定のタイトルを表示します。|  
|[CDocTemplate::SetPreviewInfo](#setpreviewinfo)|プロセス外の設定は、ハンドラーをプレビューします。|  
|[CDocTemplate::SetServerInfo](#setserverinfo)|サーバー ドキュメントが埋め込まれているか、一括編集するときは、リソースやクラスを決定します。|  
  
## <a name="remarks"></a>コメント  
 通常、アプリケーションの実装では&1; つまたは複数のドキュメント テンプレートを作成する`InitInstance`関数です。 ドキュメント テンプレートには、3 種類のクラス間の関係を定義します。  
  
-   派生するドキュメント クラス**CDocument**します。  
  
-   ビュー クラス上に示したドキュメント クラスからのデータが表示されます。 このクラスから派生できます`CView`、 `CScrollView`、 `CFormView`、または`CEditView`です。 (使用することも`CEditView`直接)。  
  
-   ビューを含むフレーム ウィンドウ クラスです。 シングル ドキュメント インターフェイス (SDI) アプリケーションをからには、このクラスを派生`CFrameWnd`します。 このクラスからの派生のマルチ ドキュメント インターフェイス (MDI) アプリケーションを`CMDIChildWnd`します。 使用することができます、フレーム ウィンドウの動作をカスタマイズしない場合は、`CFrameWnd`または`CMDIChildWnd`独自のクラスを派生させることがなく直接します。  
  
 アプリケーションでは、サポートされているドキュメントの種類ごとに&1; つのドキュメント テンプレートを持ちます。 たとえば、アプリケーションでは、スプレッドシートやテキスト ドキュメントの両方をサポートする場合、アプリケーションには、2 つのドキュメント テンプレート オブジェクトがあります。 それぞれのドキュメント テンプレートを作成して、その型のすべてのドキュメントの管理を担当します。  
  
 ドキュメント テンプレートへのポインターを格納する、`CRuntimeClass`ドキュメント、ビュー、およびフレーム ウィンドウ クラスのオブジェクト。 これら`CRuntimeClass`ドキュメント テンプレートを作成するときに、オブジェクトが指定されています。  
  
 ドキュメント テンプレートには、(メニューのアイコン、またはテーブル リソースのアクセラレータ) などのドキュメントの種類に使用されているリソースの ID が含まれています。 ドキュメント テンプレートには、そのドキュメントの種類に関する追加情報を含む文字列もあります。 ドキュメントの種類 (たとえば、「ワークシート」) とファイル拡張子 (たとえば、".xls"など) の名前が含まれます。 必要に応じて、アプリケーションのユーザー インターフェイス、Windows のファイル マネージャー、およびオブジェクトのリンクおよび Embedding (OLE) サポートで使用されるその他の文字列を格納できます。  
  
 アプリケーションが OLE コンテナーやサーバーの場合は、ドキュメント テンプレートは、インプレース アクティブ化時に使用されるメニューの ID も定義します。 アプリケーションが OLE サーバーである場合は、ドキュメント テンプレートは、インプレース アクティブ化時に使用するメニューのツールバーの ID を定義します。 呼び出してこれらの追加 OLE リソースを指定する`SetContainerInfo`と`SetServerInfo`です。  
  
 `CDocTemplate`抽象クラスでは、クラスを直接使用することはできません。 一般的なアプリケーションを使用して、2 つのいずれかの`CDocTemplate`-Microsoft Foundation Class ライブラリが提供するクラスを派生: `CSingleDocTemplate`、SDI を実装して`CMultiDocTemplate`MDI を実装します。 ドキュメント テンプレートの使用に関する詳細については、これらのクラスを参照してください。  
  
 独自のクラスを派生させることができます、アプリケーションには基本的に異なります SDI または MDI ユーザー インターフェイスのパラダイムが必要な場合`CDocTemplate`します。  
  
 詳細については`CDocTemplate`を参照してください[ドキュメント テンプレートとドキュメント/ビューの作成手順](../../mfc/document-templates-and-the-document-view-creation-process.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocTemplate`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="adddocument"></a>CDocTemplate::AddDocument  
 この関数を使用すると、テンプレートにドキュメントを追加できます。  
  
```  
virtual void AddDocument(CDocument* pDoc);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDoc`  
 追加するドキュメントへのポインター。  
  
### <a name="remarks"></a>コメント  
 派生クラス[CMultiDocTemplate](../../mfc/reference/cmultidoctemplate-class.md)と[関数](../../mfc/reference/csingledoctemplate-class.md)この関数をオーバーライドします。 ドキュメント テンプレートからのクラスを派生するかどうかは`CDocTemplate`、派生クラスは、この関数をオーバーライドする必要があります。  
  
##  <a name="cdoctemplate"></a>CDocTemplate::CDocTemplate  
 `CDocTemplate` オブジェクトを構築します。  
  
```  
CDocTemplate (
    UINT nIDResource,  
    CRuntimeClass* pDocClass,  
    CRuntimeClass* pFrameClass,  
    CRuntimeClass* pViewClass);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDResource`  
 ドキュメントの種類に使用されているリソースの ID を指定します。 これには、メニューのアイコン、アクセラレータ テーブル、および文字列リソースが含まれます。  
  
 文字列リソースは、"\n"文字で区切られた最大&7; つの部分文字列で構成されます (部分文字列が含まれていない場合は、プレース ホルダーとして"\n"文字が必要。 ただし、末尾の"\n"文字は必要ありません) です。これらの部分文字列では、ドキュメントの種類について説明します。 詳細については、部分文字列は、次を参照してください。 [GetDocString](#getdocstring)します。 アプリケーションのリソース ファイルでは、この文字列リソースが見つかります。 例:  
  
 `// MYCALC.RC`  
  
 `STRINGTABLE PRELOAD DISCARDABLE`  
  
 `BEGIN`  
  
 `IDR_SHEETTYPE "\nSheet\nWorksheet\nWorksheets (*.myc)\n.myc\n MyCalcSheet\nMyCalc Worksheet"`  
  
 `END`  
  
 文字列の先頭が"\n"文字であることに注意してください。これは、最初の部分文字列が MDI アプリケーションで実行されていない、したがってが含まれていないためです。 ストリング エディターを使用してこの文字列を編集することができます。文字列全体は、7 つの別のエントリとしてではなく文字列エディターで、1 つのエントリとして表示されます。  
  
 `pDocClass`  
 指す、`CRuntimeClass`ドキュメント クラスのオブジェクト。 このクラスは、 **CDocument**-には、ドキュメントを表すために定義するクラスを派生します。  
  
 `pFrameClass`  
 指す、`CRuntimeClass`フレーム ウィンドウ クラスのオブジェクト。 このクラスを指定できます、`CFrameWnd`の派生クラス、または実行できます`CFrameWnd`自体のメイン フレーム ウィンドウの既定の動作をする場合。  
  
 `pViewClass`  
 指す、`CRuntimeClass`ビュー クラスのオブジェクト。 このクラスは、 `CView`-には、ドキュメントを表示するように定義するクラスを派生します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数を使用して、作成、`CDocTemplate`オブジェクトです。 動的に割り当てる、`CDocTemplate`オブジェクトに渡すと[とき](../../mfc/reference/cwinapp-class.md#adddoctemplate)から、`InitInstance`アプリケーション クラスのメンバー関数。  
  
##  <a name="closealldocuments"></a>CDocTemplate::CloseAllDocuments  
 開いているすべてのドキュメントを閉じるには、このメンバー関数を呼び出します。  
  
```  
virtual void CloseAllDocuments(BOOL bEndSession);
```  
  
### <a name="parameters"></a>パラメーター  
 `bEndSession`  
 セッションが終了するかどうかを指定します。 **TRUE**終了以外の場合、セッションがされている場合は**FALSE**します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は通常、ファイルの終了 コマンドの一部として使用されます。 この関数の既定の実装、[のに](../../mfc/reference/cdocument-class.md#deletecontents)メンバー関数をドキュメントのデータと削除し、ドキュメントにアタッチされているすべてのビュー、フレーム ウィンドウを閉じます。  
  
 ドキュメントを閉じる前に、特別なクリーンアップ処理を実行するユーザーを要求する場合は、この関数をオーバーライドします。 たとえば、ドキュメントは、データベースのレコードを表している場合、データベースを閉じるには、この関数をオーバーライドします。  
  
##  <a name="createnewdocument"></a>CDocTemplate::CreateNewDocument  
 このドキュメント テンプレートに関連付けられている型の新しいドキュメントを作成するには、このメンバー関数を呼び出します。  
  
```  
virtual CDocument* CreateNewDocument();
```  
  
### <a name="return-value"></a>戻り値  
 新しく作成されたドキュメントへのポインターまたは**NULL**場合は、エラーが発生します。  
  
##  <a name="createnewframe"></a>CDocTemplate::CreateNewFrame  
 ドキュメントとビューを含む、新しいフレーム ウィンドウを作成します。  
  
```  
virtual CFrameWnd* CreateNewFrame(
    CDocument* pDoc,  
    CFrameWnd* pOther);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDoc`  
 ドキュメントが新しいフレーム ウィンドウが参照してください。 できる**NULL**します。  
  
 `pOther`  
 フレーム ウィンドウは、新しいフレーム ウィンドウに基づいています。 できる**NULL**します。  
  
### <a name="return-value"></a>戻り値  
 新しく作成されたフレーム ウィンドウへのポインターまたは**NULL**場合は、エラーが発生します。  
  
### <a name="remarks"></a>コメント  
 `CreateNewFrame`使用して、`CRuntimeClass`オブジェクト、ドキュメントを添付し、新しいフレーム ウィンドウを作成するコンス トラクターに渡されます。 場合、`pDoc`パラメーターは**NULL**フレームワークは、トレース メッセージを出力します。  
  
 `pOther`新しいウィンドウのコマンドを実装するパラメーターを使用します。 フレーム ウィンドウは、新しいフレーム ウィンドウのモデルを提供します。 新しいフレーム ウィンドウを非表示には、通常は作成されます。 新しいファイルとファイルを開くの標準的なフレームワーク実装の外部のフレーム ウィンドウを作成するには、この関数を呼び出します。  
  
##  <a name="createoleframe"></a>CDocTemplate::CreateOleFrame  
 OLE のフレーム ウィンドウを作成します。  
  
```  
CFrameWnd* CreateOleFrame(
    CWnd* pParentWnd,  
    CDocument* pDoc,  
    BOOL bCreateView);
```  
  
### <a name="parameters"></a>パラメーター  
 `pParentWnd`  
 フレームの親ウィンドウへのポインター。  
  
 `pDoc`  
 新しい OLE フレーム ウィンドウを参照するドキュメントへのポインター。  
  
 `bCreateView`  
 フレームとビューを作成するかどうかを決定します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、フレーム ウィンドウへのポインターそれ以外の場合**NULL**します。  
  
### <a name="remarks"></a>コメント  
 場合`bCreateView`0 の場合は、空のフレームを作成します。  
  
##  <a name="getdocstring"></a>CDocTemplate::GetDocString  
 ドキュメントの種類に関連付けられている文字列を取得します。  
  
```  
virtual BOOL GetDocString(
    CString& rString,  
    enum DocStringIndex index) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `rString`  
 参照、`CString`関数が戻るときに、文字列を格納するオブジェクト。  
  
 *インデックス*  
 ドキュメントの種類を表す文字列から取得する部分文字列のインデックス。 このパラメーターには、次のいずれかの値を指定できます。  
  
- **CDocTemplate::windowTitle**アプリケーション ウィンドウのタイトル バーに (たとえば、"Excel") 表示される名前です。 SDI アプリケーションのドキュメント テンプレートにのみ存在します。  
  
- **CDocTemplate::docName** (たとえば、「シート」) の既定のドキュメント名のルートです。 このルートと、数は、(たとえば、「シート&1;」または"Sheet2") は、ファイル メニューから新規作成 を選択するたびにこの型の新しいドキュメントの既定名として使用されます。 指定しない場合、「無題」は、既定値として使用します。  
  
- **CDocTemplate::fileNewName**このドキュメントの種類の名前。 アプリケーションでは、ドキュメントの&1; つ以上の種類をサポートする場合は、新しいファイル ダイアログ ボックス (たとえば、「ワークシート」) でこの文字列が表示されます。 指定しない場合、ドキュメントの種類がファイルの新規作成 コマンドを使用してアクセスできません。  
  
- **CDocTemplate::filterName**ドキュメントの種類とこのタイプのドキュメントに一致するワイルドカード フィルターの説明。 この文字列は、ファイルを開く ダイアログ ボックス (「ワークシート (*.xls)」など) でファイルの種類のドロップダウン リストに表示されます。 指定しない場合、ドキュメントの種類がファイルを開くコマンドを使用してアクセスできません。  
  
- **CDocTemplate::filterExt**この型 (たとえば、".xls"など) のドキュメントの拡張子です。 指定しない場合、ドキュメントの種類がファイルを開くコマンドを使用してアクセスできません。  
  
- **CDocTemplate::regFileTypeId** Windows によって管理される登録データベースに格納されているドキュメントの種類の識別子。 この文字列は、内部の使用のみ (たとえば、「したりできます」) です。 指定しない場合、ドキュメントの種類は Windows ファイル マネージャーに登録できません。  
  
- **CDocTemplate::regFileTypeName** registration データベースに格納されているドキュメントの種類の名前。 この文字列は、registration データベース (たとえば、「Microsoft Excel ワークシート」) にアクセスするアプリケーションのダイアログ ボックスに表示されます。  
  
### <a name="return-value"></a>戻り値  
 指定した部分文字列が見つかった場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ドキュメント型を記述する特定の部分文字列を取得するには、この関数を呼び出します。 これらの部分文字列を含む文字列では、ドキュメント テンプレートに格納され、アプリケーションのリソース ファイル内の文字列から派生します。 フレームワークでは、アプリケーションのユーザー インターフェイスに必要な文字列を取得するには、この関数を呼び出します。 アプリケーションのドキュメントのファイル名拡張子を指定した場合もフレームワーク Windows の登録データベースにエントリを追加する場合これにより、ドキュメントを Windows ファイル マネージャーから開きます。  
  
 独自のクラスを派生する場合にのみ、この関数を呼び出す`CDocTemplate`します。  
  
##  <a name="getfirstdocposition"></a>CDocTemplate::GetFirstDocPosition  
 このテンプレートに関連付けられている最初のドキュメントの位置を取得します。  
  
```  
virtual POSITION GetFirstDocPosition() const = 0;  
```  
  
### <a name="return-value"></a>戻り値  
 A**位置**ドキュメント テンプレートに関連付けられたドキュメントのリストを反復処理するために使用される値または**NULL**リストが空の場合。  
  
### <a name="remarks"></a>コメント  
 この関数を使用すると、このテンプレートに関連付けられているドキュメントの一覧内の最初のドキュメントの位置を取得できます。 使用して、**位置**への引数として値[CDocTemplate::GetNextDoc](#getnextdoc)テンプレートに関連付けられているドキュメントのリストを反復処理します。  
  
 [関数](../../mfc/reference/csingledoctemplate-class.md)と[CMultiDocTemplate](../../mfc/reference/cmultidoctemplate-class.md)両方が純粋仮想関数をオーバーライドします。 任意のクラスから派生した`CDocTemplate`この関数をオーバーライドもする必要があります。  
  
##  <a name="getnextdoc"></a>CDocTemplate::GetNextDoc  
 識別されるリストの要素を取得`rPos`、設定し、`rPos`に、**位置**一覧の次のエントリの値。  
  
```  
virtual CDocument* GetNextDoc(POSITION& rPos) const = 0;  
```  
  
### <a name="return-value"></a>戻り値  
 このテンプレートに関連付けられているドキュメントの一覧の次のドキュメントへのポインター。  
  
### <a name="parameters"></a>パラメーター  
 `rPos`  
 参照、**位置**を以前の呼び出しによって返される値[GetFirstDocPosition](#getfirstdocposition)または`GetNextDoc`です。  
  
### <a name="remarks"></a>コメント  
 取得した要素が値の場合、リスト内の最後の新しいの`rPos`に設定されている**NULL**します。  
  
 使用する`GetNextDoc`への呼び出しでは、最初の位置を確立する場合は、順方向の反復ループで[GetFirstDocPosition](#getfirstdocposition)します。  
  
 確認する必要があります、**位置**値がリスト内の有効な位置を表します。 有効な場合は、Microsoft Foundation Class ライブラリのデバッグ バージョンはアサートします。  
  
##  <a name="initialupdateframe"></a>CDocTemplate::InitialUpdateFrame  
 フレーム ウィンドウを初期化し、必要に応じてようになります。  
  
```  
virtual void InitialUpdateFrame(
    CFrameWnd* pFrame,  
    CDocument* pDoc,  
    BOOL bMakeVisible = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `pFrame`  
 最初の更新プログラムが必要なフレーム ウィンドウです。  
  
 `pDoc`  
 フレームが関連付けられているドキュメントです。 できる**NULL**します。  
  
 `bMakeVisible`  
 フレームが表示され、アクティブになる必要があるかどうかを示します。  
  
### <a name="remarks"></a>コメント  
 呼び出す**IntitialUpdateFrame**と新しいフレームを作成した後`CreateNewFrame`します。 これにより、ビューを受信するには、そのフレーム ウィンドウで、`OnInitialUpdate`呼び出しです。 また、ある以前なかった場合、アクティブなビュー、フレーム ウィンドウのプライマリ ビューはアクティブになりです。プライマリ ビューの子の ID では、ビューは、 **AFX_IDW_PANE_FIRST**します。 最後に、フレーム ウィンドウが表示される場合は`bMakeVisible`は&0; 以外。 場合`bMakeVisible`0、現在のフォーカスとフレーム ウィンドウの表示状態は変更されません。  
  
 新しいファイルとファイルを開くのフレームワークの実装を使用する場合は、この関数を呼び出す必要はありません。  
  
##  <a name="loadtemplate"></a>CDocTemplate::LoadTemplate  
 リソースを読み込み、指定された`CDocTemplate`またはその派生クラスです。  
  
```  
virtual void LoadTemplate();
```  
  
### <a name="remarks"></a>コメント  
 リソースを読み込むために、フレームワークによって呼び出されます、指定された`CDocTemplate`またはその派生クラスです。 通常ときに呼び出されます構築時を除く、テンプレートがグローバルに構築されています。 その場合、呼び出しを`LoadTemplate`まで遅延[とき](../../mfc/reference/cwinapp-class.md#adddoctemplate)が呼び出されます。  
  
##  <a name="matchdoctype"></a>CDocTemplate::MatchDocType  
 ドキュメントの種類とこのテンプレートの間の一致で信頼度を決定します。  
  
```  
virtual Confidence MatchDocType(
    LPCTSTR lpszPathName,  
    CDocument*& rpDocMatch);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszPathName`  
 型を指定するファイルのパス名。  
  
 `rpDocMatch`  
 ファイルが指定された場合、一致するドキュメントを割り当てられているドキュメントへのポインター`lpszPathName`が既に開いています。  
  
### <a name="return-value"></a>戻り値  
 値、**信頼**列挙体は、次のように定義されています。  
  
 `enum Confidence`  
  
 `{`  
  
 `noAttempt,`  
  
 `maybeAttemptForeign,`  
  
 `maybeAttemptNative,`  
  
 `yesAttemptForeign,`  
  
 `yesAttemptNative,`  
  
 `yesAlreadyOpen`  
  
 `};`  
  
### <a name="remarks"></a>コメント  
 この関数を使用して、ファイルを開くときに使用するドキュメント テンプレートの種類を決定します。 アプリケーションでは、複数のファイルの種類をサポートする場合などできますこの関数を使用する決定を呼び出すことで特定のファイルに対して適切な使用可能なドキュメント テンプレートのどれが`MatchDocType`を有効にすると、信頼度の値に従ってテンプレートを選択するには、各テンプレートが返されます。  
  
 ファイルが指定された場合`lpszPathName`が既に開いている場合は、この関数を返します**CDocTemplate::yesAlreadyOpen**ファイルのコピーと**CDocument**オブジェクトにあるオブジェクトを`rpDocMatch`します。  
  
 ファイルが開いていて、拡張機能でもない場合`lpszPathName`で指定した拡張子と一致する**CDocTemplate::filterExt**、この関数を返します**CDocTemplate::yesAttemptNative**設定と`rpDocMatch`に**NULL**します。 詳細については**CDocTemplate::filterExt**を参照してください[CDocTemplate::GetDocString](#getdocstring)します。  
  
 どちらの場合があるかどうかは true、関数を返します**とき**します。  
  
 既定の実装を返さない**CDocTemplate::maybeAttemptForeign**または**CDocTemplate::maybeAttemptNative**します。 これら&2; つの値を使用して、アプリケーションに適したの型の一致ロジックを実装するには、この関数をオーバーライド、**信頼**列挙します。  
  
##  <a name="opendocumentfile"></a>CDocTemplate::OpenDocumentFile  
 パスで指定されたファイルを開きます。  
  
```  
virtual CDocument* OpenDocumentFile(LPCTSTR lpszPathName) = 0;  
 
virtual CDocument* OpenDocumentFile(
    LPCTSTR lpszPathName,  
    BOOL bAddToMRU) = 0;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszPathName`  
 開かれているドキュメントが含まれているファイルのパスへのポインター。  
  
 [入力] `bAddToMRU`  
 `TRUE`ドキュメントが最新のファイルのいずれかを示します`FALSE`ドキュメントが最新のファイルのいずれかを示します。  
  
### <a name="return-value"></a>戻り値  
 ファイルの名前は、ドキュメントへのポインター`lpszPathName`です。`NULL`失敗した場合。  
  
### <a name="remarks"></a>コメント  
 パスが指定されたファイルを開き`lpszPathName`します。 場合`lpszPathName`は`NULL`、このテンプレートに関連付けられている型のドキュメントを含む新しいファイルが作成されます。  
  
##  <a name="removedocument"></a>CDocTemplate::RemoveDocument  
 ドキュメントを指す削除`pDoc`このテンプレートに関連付けられているドキュメントの一覧からです。  
  
```  
virtual void RemoveDocument(CDocument* pDoc);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDoc`  
 削除するドキュメントへのポインター。  
  
### <a name="remarks"></a>コメント  
 派生クラス`CMultiDocTemplate`と`CSingleDocTemplate`この関数をオーバーライドします。 ドキュメント テンプレートからのクラスを派生するかどうかは`CDocTemplate`、派生クラスは、この関数をオーバーライドする必要があります。  
  
##  <a name="saveallmodified"></a>CDocTemplate::SaveAllModified  
 変更されたすべてのドキュメントを保存します。  
  
```  
virtual BOOL SaveAllModified();
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外それ以外の場合 0 を返します。  
  
##  <a name="setcontainerinfo"></a>CDocTemplate::SetContainerInfo  
 インプレース OLE アイテムを編集するときは、OLE コンテナーのリソースを決定します。  
  
```  
void SetContainerInfo(UINT nIDOleInPlaceContainer);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDOleInPlaceContainer`  
 埋め込みオブジェクトがアクティブになったときに使用したリソースの ID です。  
  
### <a name="remarks"></a>コメント  
 OLE オブジェクトはインプレース アクティブ化されるときに使用されるリソースを設定するには、この関数を呼び出します。 これらのリソースには、メニューやアクセラレータ テーブルを含めることができます。 この関数は通常コール、[場合は](../../mfc/reference/cwinapp-class.md#initinstance)アプリケーションの機能です。  
  
 関連付けられたメニュー`nIDOleInPlaceContainer`コンテナー アプリケーションのメニューを使用してマージをアクティブ化されたインプレース項目のメニューを許可する区切り記号が含まれています。 サーバーとコンテナーのメニューのマージに関する詳細については、記事を参照してください。[メニューとリソース (OLE)](../../mfc/menus-and-resources-ole.md)します。  
  
##  <a name="setdefaulttitle"></a>CDocTemplate::SetDefaultTitle  
 ドキュメントの既定のタイトルを読み込んで、ドキュメントのタイトル バーに表示するには、この関数を呼び出します。  
  
```  
virtual void SetDefaultTitle(CDocument* pDocument) = 0;  
```  
  
### <a name="parameters"></a>パラメーター  
 *pDocument*  
 タイトルを設定するドキュメントへのポインター。  
  
### <a name="remarks"></a>コメント  
 既定のタイトルの詳細については、説明を参照してください。 **CDocTemplate::docName**で[CDocTemplate::GetDocString](#getdocstring)します。  
  
##  <a name="setserverinfo"></a>CDocTemplate::SetServerInfo  
 サーバー ドキュメントが埋め込まれているか、一括編集するときは、リソースやクラスを決定します。  
  
```  
void SetServerInfo(
    UINT nIDOleEmbedding,  
    UINT nIDOleInPlaceServer = 0,  
    CRuntimeClass* pOleFrameClass = NULL,  
    CRuntimeClass* pOleViewClass = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *nIDOleEmbedding*  
 別のウィンドウで、埋め込みオブジェクトが開かれたときに使用されるリソースの ID です。  
  
 `nIDOleInPlaceServer`  
 埋め込みオブジェクトを使用したリソースの ID では、インプレース アクティブ化されます。  
  
 *pOleFrameClass*  
 ポインター、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)インプレース アクティブ化が発生したときに作成されるフレーム ウィンドウ オブジェクトのクラスの情報を含む構造体。  
  
 *pOleViewClass*  
 ポインター、`CRuntimeClass`インプレース アクティブ化を行うときに作成するビュー オブジェクトのクラスの情報を含む構造体。  
  
### <a name="remarks"></a>コメント  
 埋め込まれたオブジェクトのアクティブ化を要求すると、サーバー アプリケーションで使用されるリソースを識別するには、このメンバー関数を呼び出します。 これらのリソースは、メニューやアクセラレータ テーブルで構成されます。 この関数は通常コール、`InitInstance`アプリケーションのです。  
  
 関連付けられたメニュー`nIDOleInPlaceServer`コンテナーのメニューを使用してサーバー メニューにマージを許可する区切り記号が含まれています。 サーバーとコンテナーのメニューのマージに関する詳細については、記事を参照してください。[メニューとリソース (OLE)](../../mfc/menus-and-resources-ole.md)します。  
  
##  <a name="createpreviewframe"></a>CDocTemplate::CreatePreviewFrame  
 リッチ プレビューに使用される子フレームを作成します。  
  
```  
CFrameWnd* CreatePreviewFrame(
    CWnd* pParentWnd,  
    CDocument* pDoc);
```  
  
### <a name="parameters"></a>パラメーター  
 `pParentWnd`  
 (通常は、シェルによって提供されます)、親ウィンドウへのポインター。  
  
 `pDoc`  
 ドキュメント オブジェクトは、その内容をプレビューへのポインター。  
  
### <a name="return-value"></a>戻り値  
 有効なポインター、`CFrameWnd`オブジェクト、または`NULL`場合は、作成に失敗します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setpreviewinfo"></a>CDocTemplate::SetPreviewInfo  
 プロセスのプレビュー ハンドラーの出力を設定します。  
  
```  
void SetPreviewInfo(
    UINT nIDPreviewFrame,  
    CRuntimeClass* pPreviewFrameClass = NULL,  
    CRuntimeClass* pPreviewViewClass = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDPreviewFrame`  
 プレビューのフレームのリソース ID を指定します。  
  
 `pPreviewFrameClass`  
 プレビュー フレームのランタイム クラス情報構造体へのポインターを指定します。  
  
 `pPreviewViewClass`  
 プレビュー ビューのランタイム クラス情報構造体へのポインターを指定します。  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [関数のクラス](../../mfc/reference/csingledoctemplate-class.md)   
 [CMultiDocTemplate クラス](../../mfc/reference/cmultidoctemplate-class.md)   
 [CDocument クラス](../../mfc/reference/cdocument-class.md)   
 [CView クラス](../../mfc/reference/cview-class.md)   
 [CScrollView クラス](../../mfc/reference/cscrollview-class.md)   
 [CEditView クラス](../../mfc/reference/ceditview-class.md)   
 [CFormView クラス](../../mfc/reference/cformview-class.md)   
 [CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)   
 [CMDIChildWnd クラス](../../mfc/reference/cmdichildwnd-class.md)

