---
title: "CDocTemplate クラス | Microsoft Docs"
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
  - "CDocTemplate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDocTemplate クラス"
  - "ドキュメント テンプレート"
  - "テンプレート, ドキュメント"
ms.assetid: 14b41a1f-bf9d-4eac-b6a8-4c54ffcc77f6
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDocTemplate クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ドキュメント テンプレートの基本的な機能を定義する抽象基本クラスです。  
  
## 構文  
  
```  
class CDocTemplate : public CCmdTarget  
```  
  
## メンバー  
  
### プロテクト コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CDocTemplate::CDocTemplate](../Topic/CDocTemplate::CDocTemplate.md)|`CDocTemplate` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CDocTemplate::AddDocument](../Topic/CDocTemplate::AddDocument.md)|テンプレートにドキュメントを追加します。|  
|[CDocTemplate::CloseAllDocuments](../Topic/CDocTemplate::CloseAllDocuments.md)|テンプレートに関連付けられているすべてのドキュメントを閉じます。|  
|[CDocTemplate::CreateNewDocument](../Topic/CDocTemplate::CreateNewDocument.md)|新しいドキュメントを作成します。|  
|[CDocTemplate::CreateNewFrame](../Topic/CDocTemplate::CreateNewFrame.md)|ドキュメントやビューを持つ新しいフレーム ウィンドウを作成します。|  
|[CDocTemplate::CreateOleFrame](../Topic/CDocTemplate::CreateOleFrame.md)|OLE が許可されたフレーム ウィンドウを作成します。|  
|[CDocTemplate::CreatePreviewFrame](../Topic/CDocTemplate::CreatePreviewFrame.md)|リッチ プレビューに使用する子フレームを作成します。|  
|[CDocTemplate::GetDocString](../Topic/CDocTemplate::GetDocString.md)|ドキュメントの型に関連付けられている文字列を取得します。|  
|[CDocTemplate::GetFirstDocPosition](../Topic/CDocTemplate::GetFirstDocPosition.md)|テンプレートに関連付けられた最初のドキュメントの位置を取得します。|  
|[CDocTemplate::GetNextDoc](../Topic/CDocTemplate::GetNextDoc.md)|ドキュメントとその次のドキュメントの位置を取得します。|  
|[CDocTemplate::InitialUpdateFrame](../Topic/CDocTemplate::InitialUpdateFrame.md)|フレーム ウィンドウを初期化します。オプションで表示もします。|  
|[CDocTemplate::LoadTemplate](../Topic/CDocTemplate::LoadTemplate.md)|指定した `CDocTemplate` または派生クラスのリソースを読み込みます。|  
|[CDocTemplate::MatchDocType](../Topic/CDocTemplate::MatchDocType.md)|ドキュメントの型とテンプレート間で、一致の信頼度を調べます。|  
|[CDocTemplate::OpenDocumentFile](../Topic/CDocTemplate::OpenDocumentFile.md)|パス名で指定されたファイルを開きます。|  
|[CDocTemplate::RemoveDocument](../Topic/CDocTemplate::RemoveDocument.md)|テンプレートからドキュメントを削除します。|  
|[CDocTemplate::SaveAllModified](../Topic/CDocTemplate::SaveAllModified.md)|テンプレートに関連付けられている修正済みのすべてのドキュメントを保存します。|  
|[CDocTemplate::SetContainerInfo](../Topic/CDocTemplate::SetContainerInfo.md)|埋め込み先の OLE アイテムを編集するときの OLE コンテナーのリソースを決定します。|  
|[CDocTemplate::SetDefaultTitle](../Topic/CDocTemplate::SetDefaultTitle.md)|ドキュメント ウィンドウのタイトル バーに既定のタイトルを表示します。|  
|[CDocTemplate::SetPreviewInfo](../Topic/CDocTemplate::SetPreviewInfo.md)|アウトプロセスのプレビュー ハンドラーを設定します。|  
|[CDocTemplate::SetServerInfo](../Topic/CDocTemplate::SetServerInfo.md)|サーバー ドキュメントが埋め込まれたり、埋め込み先で編集されるとき、リソースやクラスを決定します。|  
  
## 解説  
 通常、アプリケーションの `InitInstance` の関数の実装の一つ以上のドキュメント テンプレートを作成します。  ドキュメント テンプレートは、3 種類のクラス間の関係を定義します:  
  
-   、**CDocument**から派生するドキュメントのクラス。  
  
-   ドキュメント クラスのデータを表示するビュー クラス、先頭にが表示されます。  `CView`、`CScrollView`、`CFormView`、または `CEditView`からこのクラスを派生させることができます。  \(または `CEditView` を直接使用できます\)。  
  
-   ビューを含むフレーム ウィンドウのクラス。  シングル ドキュメント インターフェイスの \(SDI\) アプリケーションでは、`CFrameWnd`からこのクラスを取得します。  マルチ ドキュメント インターフェイスの \(MDI\) アプリケーションでは、`CMDIChildWnd`からこのクラスを取得します。  フレーム ウィンドウの動作をカスタマイズする必要がない場合は、独自のクラスを派生せずに `CFrameWnd` か `CMDIChildWnd` クラスを直接使用できます。  
  
 アプリケーションでサポートするドキュメントの種類ごとに 1 回ドキュメント テンプレートがあります。  たとえば、アプリケーションがスプレッドシート、およびテキスト ドキュメントの両方をサポートする場合は、アプリケーションに 2 個のドキュメント テンプレート オブジェクトがあります。  各ドキュメント テンプレートは、型のすべてのドキュメントを作成および管理する必要があります。  
  
 ドキュメント テンプレートによってドキュメント、ビュー、およびフレーム ウィンドウ クラスの `CRuntimeClass` オブジェクトへのポインターを格納します。  `CRuntimeClass` のこれらのオブジェクトはドキュメント テンプレートを構築するときに指定されます。  
  
 ドキュメント テンプレートによってドキュメントの種類で使用するリソース ID \(メニュー、アイコン、またはアクセラレータ テーブル リソースなど\)。  ドキュメント テンプレートでは、ドキュメントの種類に関する追加情報を含む文字列があります。  これらはドキュメントの種類 \(「」\) ワークシートとファイル拡張子 \(.xls、「」\) の名前が含まれています。  オプションで、アプリケーションのユーザー インターフェイス、Windows のファイル マネージャーとオブジェクトのリンクと埋め込み OLE\) のサポートで使用される別の文字列を含めることができます。  
  
 アプリケーションが OLE コンテナーとサーバーの場合、ドキュメント テンプレートは、埋め込み先でアクティブ化の際に使用されたメニュー ID を定義します。  アプリケーションで OLE サーバーの場合、ドキュメント テンプレートは、埋め込み先編集の有効化時に使用するツール バーとメニュー ID を定義します。  `SetContainerInfo` と `SetServerInfo`を呼び出して、これらの追加の OLE リソースを指定します。  
  
 `CDocTemplate` が抽象クラスであるため、クラスを直接使用できません。  一般的なアプリケーションで 2 `CDocTemplate`の 1 つが\- Microsoft Foundation Class ライブラリに用意されている派生クラスが使用されます: `CSingleDocTemplate`、SDI を実行すると、`CMultiDocTemplate`、MDI を実装する。  ドキュメント テンプレートの使用の詳細については、クラスを参照してください。  
  
 アプリケーションが SDI または MDI と基に違いがあるユーザー インターフェイス パラダイムを要求した場合、`CDocTemplate`から独自のクラスを派生させることができます。  
  
 `CDocTemplate`の詳細については、[ドキュメント テンプレートとドキュメント\/ビューの作成手順](../../mfc/document-templates-and-the-document-view-creation-process.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 `CDocTemplate`  
  
## 必要条件  
 **ヘッダー:** afxwin.h  
  
## 参照  
 [CCmdTarget クラス](../Topic/CCmdTarget%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CSingleDocTemplate クラス](../../mfc/reference/csingledoctemplate-class.md)   
 [CMultiDocTemplate クラス](../../mfc/reference/cmultidoctemplate-class.md)   
 [CDocument クラス](../Topic/CDocument%20Class.md)   
 [CView クラス](../Topic/CView%20Class.md)   
 [CScrollView クラス](../../mfc/reference/cscrollview-class.md)   
 [CEditView クラス](../Topic/CEditView%20Class.md)   
 [CFormView クラス](../../mfc/reference/cformview-class.md)   
 [CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)   
 [CMDIChildWnd クラス](../../mfc/reference/cmdichildwnd-class.md)