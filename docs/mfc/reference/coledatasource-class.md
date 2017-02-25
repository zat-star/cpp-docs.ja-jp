---
title: "COleDataSource クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleDataSource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "クリップボード [C++], MFC サポート"
  - "クリップボード [C++], OLE サポート"
  - "COleDataSource クラス"
  - "データ転送 [C++], OLE"
  - "ドラッグ アンド ドロップ [C++], MFC サポート"
  - "IDataObject, MFC のカプセル化"
  - "OLE [C++], 汎用データ転送"
  - "OLE クリップボード [C++], サポート"
  - "OLE データ転送 [C++]"
  - "汎用データ転送"
  - "汎用データ転送, OLE"
ms.assetid: 02c8ee7d-8e10-4463-8613-bb2a0305ca69
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# COleDataSource クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE アプリケーションが、クリップボード操作やドラッグ アンド ドロップ操作のようなデータ転送操作中に用意するデータを置くキャッシュの役目をします。  
  
## 構文  
  
```  
class COleDataSource : public CCmdTarget  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[COleDataSource::COleDataSource](../Topic/COleDataSource::COleDataSource.md)|`COleDataSource` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[COleDataSource::CacheData](../Topic/COleDataSource::CacheData.md)|**STGMEDIUM** の構造を使用して、指定した書式指定のデータ。|  
|[COleDataSource::CacheGlobalData](../Topic/COleDataSource::CacheGlobalData.md)|`HGLOBAL`を使用して指定した形式でデータを提供します。|  
|[COleDataSource::DelayRenderData](../Topic/COleDataSource::DelayRenderData.md)|遅延レンダリングを使用して指定した形式でデータを提供します。|  
|[COleDataSource::DelayRenderFileData](../Topic/COleDataSource::DelayRenderFileData.md)|`CFile` のポインターの指定した形式でデータを提供します。|  
|[COleDataSource::DelaySetData](../Topic/COleDataSource::DelaySetData.md)|`OnSetData`でサポートされている任意の書式で呼び出されます。|  
|[COleDataSource::DoDragDrop](../Topic/COleDataSource::DoDragDrop.md)|データ ソースのドラッグ アンド ドロップ操作を実行します。|  
|[COleDataSource::Empty](../Topic/COleDataSource::Empty.md)|データの `COleDataSource` のオブジェクトを空にします。|  
|[COleDataSource::FlushClipboard](../Topic/COleDataSource::FlushClipboard.md)|クリップボードにすべてのデータが表示されます。|  
|[COleDataSource::GetClipboardOwner](../Topic/COleDataSource::GetClipboardOwner.md)|クリップボードに配置されたデータをリモート コンピューターにあることを確認します。|  
|[COleDataSource::OnRenderData](../Topic/COleDataSource::OnRenderData.md)|遅延レンダリングの一部として取得します。|  
|[COleDataSource::OnRenderFileData](../Topic/COleDataSource::OnRenderFileData.md)|遅延レンダリングの一部として `CFile` にデータを取得します。|  
|[COleDataSource::OnRenderGlobalData](../Topic/COleDataSource::OnRenderGlobalData.md)|遅延レンダリングの一部として `HGLOBAL` にデータを取得します。|  
|[COleDataSource::OnSetData](../Topic/COleDataSource::OnSetData.md)|`COleDataSource` のデータを置き換えるために呼び出すオブジェクトします。|  
|[COleDataSource::SetClipboard](../Topic/COleDataSource::SetClipboard.md)|クリップボードに `COleDataSource` のオブジェクトを設定します。|  
  
## 解説  
 OLE データ ソースを直接作成できます。  また、[COleClientItem](../../mfc/reference/coleclientitem-class.md) と [COleServerItem](../../mfc/reference/coleserveritem-class.md) のクラスは `CopyToClipboard` と `DoDragDrop` のメンバー関数に応じて、OLE データ ソースを作成します。  簡単な説明については [COleServerItem::CopyToClipboard](../Topic/COleServerItem::CopyToClipboard.md) を参照してください。  `CopyToClipboard` または `DoDragDrop` のメンバー関数に作成される OLE データ ソースのデータに追加のクリップボード形式を適用するには、クライアント項目またはサーバー項目クラスの `OnGetClipboardData` のメンバー関数をオーバーライドします。  
  
 コピーのデータを準備するたびにこのクラスのオブジェクトを作成し、データの最も適切なメソッドを使用してデータで塗りつぶされます。  データ ソースに挿入する方法は直接データをすばやく指定するかどうか \(即時レンダリング\) か、必要に応じて影響 \(遅延レンダリングされます\)。  使用するクリップボード形式データを提供するクリップボード形式の場合 \(および [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) の省略可能な構造\) を渡すことにより、呼び出し [DelayRenderData](../Topic/COleDataSource::DelayRenderData.md)。  
  
 データ ソースとデータ転送に関する詳細については、" " [データ オブジェクトとデータ ソース \(OLE\)](../../mfc/data-objects-and-data-sources-ole.md)を参照してください。  また、" " [クリップボードのトピック](../../mfc/clipboard.md) は、OLE クリップボード機構について説明します。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 `COleDataSource`  
  
## 必要条件  
 **Header:** afxole.h  
  
## 参照  
 [MFC HIERSVR サンプル](../../top/visual-cpp-samples.md)   
 [MFC の OCLIENT サンプル](../../top/visual-cpp-samples.md)   
 [CCmdTarget クラス](../Topic/CCmdTarget%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleDataObject クラス](../../mfc/reference/coledataobject-class.md)