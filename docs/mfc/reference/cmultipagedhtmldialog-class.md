---
title: "CMultiPageDHtmlDialog クラス | Microsoft Docs"
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
  - "CMultiPageDHtmlDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMultiPageDHtmlDialog クラス"
ms.assetid: 971accc1-824d-4df4-b4c1-b1a20e0f7e4f
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMultiPageDHtmlDialog クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

マルチページ ダイアログは、複数の HTML ページを順番に表示し、各ページのイベントを処理します。  
  
## 構文  
  
```  
class CMultiPageDHtmlDialog : public CDHtmlDialog  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMultiPageDHtmlDialog::CMultiPageDHtmlDialog](../Topic/CMultiPageDHtmlDialog::CMultiPageDHtmlDialog.md)|マルチページの \(ウィザード スタイルの\)  DHTML ダイアログ オブジェクトを構築します。|  
|[CMultiPageDHtmlDialog::~CMultiPageDHtmlDialog](../Topic/CMultiPageDHtmlDialog::~CMultiPageDHtmlDialog.md)|マルチページの DHTML ダイアログ オブジェクトを破棄します。|  
  
## 解説  
 各ページの [埋め込みイベント マップ](../Topic/BEGIN_EMBED_DHTML_EVENT_MAP.md) を含むこれを行うための機構は [と DHTML イベント マップの URL](http://msdn.microsoft.com/ja-jp/2a7332f0-79d7-46e4-b816-0a618c46777a)です。  
  
## 使用例  
 このマルチページ ダイアログは、単純なウィザードに似た機能を定義する 3 種類の HTML リソースを前提としています。  最初のページに `Next` のボタン、2 番目の **\[前へ\]** と `Next` のボタン、および番目のボタン **\[前へ\]** があります。  ボタンの 1 つがが押されると、適切な新しいページを読み込むハンドラー関数呼び出し [CDHtmlDialog::LoadFromResource](../Topic/CDHtmlDialog::LoadFromResource.md)。  
  
 クラス宣言の適切な部分 \(CMyMultiPageDlg.h\) :  
  
 [!code-cpp[NVC_MFCDocView#181](../../mfc/codesnippet/CPP/cmultipagedhtmldialog-class_1.h)]  
  
 クラスの実装の適切な部分 \(CMyMultipageDlg.cpp\) :  
  
 [!code-cpp[NVC_MFCDocView#182](../../mfc/codesnippet/CPP/cmultipagedhtmldialog-class_2.cpp)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CDHtmlSinkHandlerBase2`  
  
 `CDHtmlSinkHandlerBase1`  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 `CDHtmlSinkHandler`  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 `CDHtmlEventSink`  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDHtmlDialog](../Topic/CDHtmlDialog%20Class.md)  
  
 `CMultiPageDHtmlDialog`  
  
## 必要条件  
 **ヘッダー :** afxdhtml.h  
  
## 参照  
 [CDHtmlDialog クラス](../Topic/CDHtmlDialog%20Class.md)   
 [Multipage DHTML and URL Event Maps \(NIB\)](http://msdn.microsoft.com/ja-jp/2a7332f0-79d7-46e4-b816-0a618c46777a)