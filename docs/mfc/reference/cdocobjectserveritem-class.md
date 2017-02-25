---
title: "CDocObjectServerItem クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDocObjectServerItem"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX ドキュメント [C++], ドキュメント サーバー"
  - "CDocObjectServerItem クラス"
  - "docobject サーバー"
  - "ドキュメント オブジェクト サーバー"
  - "サーバー [C++], ActiveX ドキュメント"
  - "サーバー [C++], doc オブジェクト"
ms.assetid: 530f7156-50c8-4806-9328-602c9133f622
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CDocObjectServerItem クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE サーバー動詞を DocObject サーバー用に実装します。  
  
## 構文  
  
```  
class CDocObjectServerItem : public COleServerItem  
```  
  
## メンバー  
  
### プロテクト コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CDocObjectServerItem::CDocObjectServerItem](../Topic/CDocObjectServerItem::CDocObjectServerItem.md)|`CDocObjectServerItem` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CDocObjectServerItem::GetDocument](../Topic/CDocObjectServerItem::GetDocument.md)|項目を含むドキュメントへのポインターを取得します。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CDocObjectServerItem::OnHide](../Topic/CDocObjectServerItem::OnHide.md)|フレームワークが DocObject の項目を非表示にするには、例外をスローします。|  
|[CDocObjectServerItem::OnShow](../Topic/CDocObjectServerItem::OnShow.md)|DocObject の項目に埋め込み先編集をアクティブにするために、フレームワークによって呼び出されます。  項目がでない場合、DocObject [COleServerItem::OnShow](../Topic/COleServerItem::OnShow.md)を呼び出します。|  
  
## 解説  
 `CDocObjectServerItem` は、オーバーライドできるメンバー関数を定義します: [OnHide](../Topic/CDocObjectServerItem::OnHide.md)、[OnOpen](http://msdn.microsoft.com/ja-jp/7a9b1363-6ad8-4732-9959-4e35c07644fd)と [OnShow](../Topic/CDocObjectServerItem::OnShow.md)。  
  
 `CDocObjectServerItem`を使用するには、対象の `COleServerDoc`の [OnGetEmbeddedItem](../Topic/COleServerDoc::OnGetEmbeddedItem.md) の保証オーバーライドする派生クラスは `CDocObjectServerItem` の新しいオブジェクトを返します。  で項目の機能を変更する必要がある場合は、独自の `CDocObjectServerItem`派生クラスの新しいインスタンスを作成できます。  
  
 DocObjects の詳細については、*" MFC リファレンス"*の [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md) と [COleCmdUI](../../mfc/reference/colecmdui-class.md) を参照してください。  また [インターネットの対処方法: Active ドキュメント](../Topic/Active%20Documents%20on%20the%20Internet.md) と [Active ドキュメント](../Topic/Active%20Documents%20on%20the%20Internet.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 [COleServerItem](../../mfc/reference/coleserveritem-class.md)  
  
 `CDocObjectServerItem`  
  
## 必要条件  
 **Header:** afxdocob.h  
  
## 参照  
 [COleServerItem クラス](../../mfc/reference/coleserveritem-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDocObjectServer クラス](../../mfc/reference/cdocobjectserver-class.md)   
 [COleDocObjectItem クラス](../Topic/COleDocObjectItem%20Class.md)