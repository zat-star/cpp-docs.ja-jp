---
title: "CRichEditDoc クラス | Microsoft Docs"
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
  - "CRichEditDoc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRichEditDoc クラス"
  - "ドキュメント/ビュー アーキテクチャ, リッチ エディット コントロール"
  - "ドキュメント, リッチ エディット"
  - "OLE コンテナー, リッチ エディット"
  - "リッチ エディット コントロール, OLE コンテナー"
ms.assetid: c936ec18-d516-49d4-b7fb-c9aa0229eddc
caps.latest.revision: 24
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRichEditDoc クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[CRichEditView](../../mfc/reference/cricheditview-class.md) [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md)とともに、MFC のドキュメント ビュー アーキテクチャのコンテキストでリッチ エディット コントロールの機能を提供します。  
  
## 構文  
  
```  
  
class CRichEditDoc : public COleServerDoc  
  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CRichEditDoc::CreateClientItem](../Topic/CRichEditDoc::CreateClientItem.md)|ドキュメントのクリーンアップを実行します。|  
|[CRichEditDoc::GetStreamFormat](../Topic/CRichEditDoc::GetStreamFormat.md)|ストリーム入出力が書式設定情報を含めるかどうかを示します。|  
|[CRichEditDoc::GetView](../Topic/CRichEditDoc::GetView.md)|[CRichEditView](../../mfc/reference/cricheditview-class.md) の asssociated オブジェクトを取得します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CRichEditDoc::m\_bRTF](../Topic/CRichEditDoc::m_bRTF.md)|ストリーム入出力の形式を含めるかどうかを示します。|  
  
## 解説  
 「リッチ エディット コントロール」はユーザーがテキストを入力し、編集できるウィンドウです。  テキストは、文字と段落書式を割り当て、埋め込み OLE オブジェクトを含めることができます。  リッチ エディット コントロールは、テキストの書式を設定するプログラミング インターフェイスを提供します。  ただし、アプリケーションは書式設定操作をユーザーが使用できるようにするために必要なユーザー インターフェイス コンポーネントを実装する必要があります。  
  
 `CRichEditView` は、テキストに一意のテキストと書式設定を保持します。  `CRichEditDoc` は、ビューのクライアント項目のリストを保持します。  `CRichEditCntrItem` は OLE クライアント項目へのコンテナー側のアクセスを提供します。  
  
 このの Windows コモン コントロール \(したがって [CRichEditCtrl](../Topic/CRichEditCtrl%20Class.md) と関連クラス\) \/98 Windows 95 および Windows NT 3.51 以降で実行されるプログラムにのみ使用できます。  
  
 MFC アプリケーションのリッチ エディットのドキュメントの使用例については、[WORDPAD](../../top/visual-cpp-samples.md) サンプル アプリケーションを参照します。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CDocument](../Topic/CDocument%20Class.md)  
  
 [COleDocument](../../mfc/reference/coledocument-class.md)  
  
 [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)  
  
 [COleServerDoc](../Topic/COleServerDoc%20Class.md)  
  
 `CRichEditDoc`  
  
## 必要条件  
 **Header:** afxrich.h  
  
## 参照  
 [MFC WORDPAD サンプル](../../top/visual-cpp-samples.md)   
 [COleServerDoc クラス](../Topic/COleServerDoc%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CRichEditView クラス](../../mfc/reference/cricheditview-class.md)   
 [CRichEditCntrItem クラス](../../mfc/reference/cricheditcntritem-class.md)   
 [COleDocument クラス](../../mfc/reference/coledocument-class.md)   
 [CRichEditCtrl クラス](../Topic/CRichEditCtrl%20Class.md)