---
title: "COleDataObject クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IDataObject"
  - "COleDataObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "クリップボード [C++], MFC サポート"
  - "クリップボード [C++], OLE サポート"
  - "COleDataObject クラス"
  - "データ転送 [C++]"
  - "データ転送 [C++], OLE"
  - "ドラッグ アンド ドロップ [C++], MFC サポート"
  - "IDataObject インターフェイス, MFC のカプセル化"
  - "OLE [C++], 汎用データ転送"
  - "OLE クリップボード [C++], サポート"
  - "OLE データ転送 [C++]"
  - "汎用データ転送"
  - "汎用データ転送, OLE"
ms.assetid: d1cc84be-2e1c-4bb3-a8a0-565eb08aaa34
caps.latest.revision: 20
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleDataObject クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

クリップボードや OLE 埋め込みアイテムからさまざまなフォーマットのデータを取得するときのデータ転送に使用します。クリップボードからデータを取得するときは、ドラッグ アンド ドロップを使用します。  
  
## 構文  
  
```  
class COleDataObject  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[COleDataObject::COleDataObject](../Topic/COleDataObject::COleDataObject.md)|`COleDataObject` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[COleDataObject::Attach](../Topic/COleDataObject::Attach.md)|`COleDataObject`に、指定した OLE データ オブジェクトをアタッチします。|  
|[COleDataObject::AttachClipboard](../Topic/COleDataObject::AttachClipboard.md)|クリップボードにデータ オブジェクトを追加します。|  
|[COleDataObject::BeginEnumFormats](../Topic/COleDataObject::BeginEnumFormats.md)|`GetNextFormat` の一つ以上の後続の呼び出しの準備。|  
|[COleDataObject::Detach](../Topic/COleDataObject::Detach.md)|`IDataObject` に関連付けられたオブジェクトをデタッチします。|  
|[COleDataObject::GetData](../Topic/COleDataObject::GetData.md)|指定した形式のアタッチされた OLE データ オブジェクトからデータをコピーします。|  
|[COleDataObject::GetFileData](../Topic/COleDataObject::GetFileData.md)|指定した形式の `CFile` のポインターにアタッチした OLE データ オブジェクトからデータをコピーします。|  
|[COleDataObject::GetGlobalData](../Topic/COleDataObject::GetGlobalData.md)|指定した形式の `HGLOBAL` にアタッチした OLE データ オブジェクトからデータをコピーします。|  
|[COleDataObject::GetNextFormat](../Topic/COleDataObject::GetNextFormat.md)|次のデータ形式が使用できるを返します。|  
|[COleDataObject::IsDataAvailable](../Topic/COleDataObject::IsDataAvailable.md)|指定した形式でデータが使用可能かどうかをチェックします。|  
|[COleDataObject::Release](../Topic/COleDataObject::Release.md)|デタッチとリリース `IDataObject` の関連するオブジェクト。|  
  
## 解説  
 `COleDataObject` には、基本クラスはありません。  
  
 これらの種類のデータはコピー元とコピー先が含まれます。  データ ソースは、[COleDataSource](../../mfc/reference/coledatasource-class.md) のクラスのオブジェクト実行されます。  目的のアプリケーションにドロップされたデータがある場合、またはクリップボードからの貼り付け操作を実行するように要求されると `COleDataObject` クラスのオブジェクトを作成する必要があります。  
  
 このクラスは、データが指定の書式にあるかどうかを判別することができます。  指定された書式が使用できる列挙し、任意の書式でデータをかどうか、または使用可能なデータ形式またはチェックを取得できます。  オブジェクトは、検索 [CFile](../../mfc/reference/cfile-class.md)`HGLOBAL`、または **STGMEDIUM** の構造体の使用を含むいくつかの方法で、実行することもできます。  
  
 詳細については、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) の構造体を参照してください。  
  
 アプリケーションにデータ オブジェクトを使用する方法の詳細については、" " [データ オブジェクトとデータ ソース \(OLE\)](../../mfc/data-objects-and-data-sources-ole.md)を参照してください。  
  
## 継承階層  
 `COleDataObject`  
  
## 必要条件  
 **Header:** afxole.h  
  
## 参照  
 [MFC HIERSVR サンプル](../../top/visual-cpp-samples.md)   
 [MFC の OCLIENT サンプル](../../top/visual-cpp-samples.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleDataSource クラス](../../mfc/reference/coledatasource-class.md)   
 [COleClientItem クラス](../../mfc/reference/coleclientitem-class.md)   
 [COleServerItem クラス](../../mfc/reference/coleserveritem-class.md)   
 [COleDataSource::DoDragDrop](../Topic/COleDataSource::DoDragDrop.md)   
 [CView::OnDrop](../Topic/CView::OnDrop.md)