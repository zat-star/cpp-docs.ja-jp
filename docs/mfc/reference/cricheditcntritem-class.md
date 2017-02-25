---
title: "CRichEditCntrItem クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CRichEditCntrItem"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRichEditCntrItem クラス"
  - "OLE 項目, リッチ エディット ビューで"
  - "リッチ エディット コントロール, OLE 項目"
  - "リッチ エディット コントロール, 使用"
ms.assetid: 6c0b4efe-0fb8-4621-b5e1-fdcb8ec48c3b
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CRichEditCntrItem クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[CRichEditView](../../mfc/reference/cricheditview-class.md) [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)とともに、MFC のドキュメント ビュー アーキテクチャのコンテキストでリッチ エディット コントロールの機能を提供します。  
  
## 構文  
  
```  
class CRichEditCntrItem : public COleClientItem  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CRichEditCntrItem::CRichEditCntrItem](../Topic/CRichEditCntrItem::CRichEditCntrItem.md)|`CRichEditCntrItem` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CRichEditCntrItem::SyncToRichEditObject](../Topic/CRichEditCntrItem::SyncToRichEditObject.md)|異なる型として項目をアクティブにします。|  
  
## 解説  
 「リッチ エディット コントロール」はユーザーがテキストを入力し、編集できるウィンドウです。  テキストは、文字と段落書式を割り当て、埋め込み OLE オブジェクトを含めることができます。  リッチ エディット コントロールは、テキストの書式を設定するプログラミング インターフェイスを提供します。  ただし、アプリケーションは書式設定操作をユーザーが使用できるようにするために必要なユーザー インターフェイス コンポーネントを実装する必要があります。  
  
 `CRichEditView` は、テキストに一意のテキストと書式設定を保持します。  `CRichEditDoc` は、ビューにある OLE クライアント項目のリストを保持します。  `CRichEditCntrItem` は OLE クライアント項目へのコンテナー側のアクセスを提供します。  
  
 このの Windows コモン コントロール \(したがって [CRichEditCtrl](../Topic/CRichEditCtrl%20Class.md) と関連クラス\) \/98 Windows 95 および Windows NT 3.51 以降で実行されるプログラムにのみ使用できます。  
  
 リッチ使用例については、MFC アプリケーションのコンテナーの項目は、" "を [WORDPAD](../../top/visual-cpp-samples.md) サンプル アプリケーションを編集します。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 [COleClientItem](../../mfc/reference/coleclientitem-class.md)  
  
 `CRichEditCntrItem`  
  
## 必要条件  
 **Header:** afxrich.h  
  
## 参照  
 [MFC WORDPAD サンプル](../../top/visual-cpp-samples.md)   
 [COleClientItem クラス](../../mfc/reference/coleclientitem-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CRichEditDoc クラス](../../mfc/reference/cricheditdoc-class.md)   
 [CRichEditView クラス](../../mfc/reference/cricheditview-class.md)