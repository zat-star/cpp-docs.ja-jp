---
title: "CMultiDocTemplate クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMultiDocTemplate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMultiDocTemplate クラス"
  - "MDI, テンプレート"
ms.assetid: 5b8aa328-e461-41d0-b388-00594535e119
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CMultiDocTemplate クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MDI \(マルチ ドキュメント インターフェイス\) を実装するドキュメント テンプレートを定義します。  
  
## 構文  
  
```  
  
class CMultiDocTemplate : public CDocTemplate  
  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMultiDocTemplate::CMultiDocTemplate](../Topic/CMultiDocTemplate::CMultiDocTemplate.md)|`CMultiDocTemplate` オブジェクトを構築します。|  
  
## 解説  
 MDI アプリケーションは、メイン フレーム ウィンドウを、それぞれがドキュメントを表示することができるゼロ以上のドキュメント フレーム ウィンドウを開くワークスペース使用します。  MDI の詳細については、*ソフトウェア設計については、Windows インターフェイスのガイドラインを*参照してください。  
  
 ドキュメント テンプレートは、3 種類のクラス間の関係を定義します:  
  
-   、[CDocument](../Topic/CDocument%20Class.md)から派生するドキュメントのクラス。  
  
-   ドキュメント クラスのデータを表示するビュー クラス、先頭にが表示されます。  [&#91;CW2CT&#93;](../Topic/CView%20Class.md)、`CScrollView`、`CFormView`、または `CEditView`からこのクラスを派生させることができます。  \(または `CEditView` を直接使用できます\)。  
  
-   ビューを含むフレーム ウィンドウのクラス。  MDI ドキュメント テンプレートごとに、`CMDIChildWnd`からこのクラスを取得できます。または、ドキュメント フレーム ウィンドウの動作をカスタマイズする必要がない場合は、独自のクラスを派生せずに [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) を直接使用できます。  
  
 MDI アプリケーションでは、ドキュメントの種類をサポートし、異なる種類のドキュメントに同時に表示されます。  アプリケーションでサポートする各ドキュメントの種類の 1 種類のドキュメント テンプレートがあります。  たとえば、MDI アプリケーションがスプレッドシート、およびテキスト ドキュメントの両方をサポートする場合は、アプリケーションに `CMultiDocTemplate` の 2 種類のオブジェクトがあります。  
  
 アプリケーションは、ユーザーが新しいドキュメントを作成すると、ドキュメント テンプレートを使用します。  アプリケーションがドキュメントの種類をサポートしている場合、フレームワークはドキュメント テンプレートでサポートされているドキュメントの種類の名前を取得し、ファイルの新しいダイアログ ボックスの一覧に表示されます。  ユーザーがドキュメントの種類を選択した場合、アプリケーションはドキュメント クラス オブジェクト、フレーム ウィンドウのオブジェクトとビュー オブジェクトを作成し、これらを互いにアタッチします。  
  
 コンストラクター以外\) `CMultiDocTemplate` のメンバー関数を呼び出す必要はありません。  フレームワークは `CMultiDocTemplate` のオブジェクトを内部処理します。  
  
 `CMultiDocTemplate`の詳細については、[ドキュメント テンプレートとドキュメント\/ビューの作成手順](../../mfc/document-templates-and-the-document-view-creation-process.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md)  
  
 `CMultiDocTemplate`  
  
## 必要条件  
 **ヘッダー:** afxwin.h  
  
## 参照  
 [CDocTemplate クラス](../../mfc/reference/cdoctemplate-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDocTemplate クラス](../../mfc/reference/cdoctemplate-class.md)   
 [CSingleDocTemplate クラス](../../mfc/reference/csingledoctemplate-class.md)   
 [CWinApp クラス](../../mfc/reference/cwinapp-class.md)