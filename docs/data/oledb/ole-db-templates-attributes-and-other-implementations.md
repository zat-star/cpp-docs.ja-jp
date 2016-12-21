---
title: "OLE DB テンプレート、属性、およびその他の実装 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OLE DB テンプレート"
  - "OLE DB テンプレート, OLE DB テンプレートの概要"
  - "OLE DB, 実装"
ms.assetid: 0c780c1b-9bba-4788-8c33-8552d9f120ac
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OLE DB テンプレート、属性、およびその他の実装
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## ATL OLE DB テンプレート  
 OLE DB テンプレートは ATL \(Active Template Library\) の一部です。一般に使用されている多くの OLE DB インターフェイスを実装するクラスを提供することで、パフォーマンスの高い OLE DB データベース テクノロジを使いやすくしています。  このテンプレート ライブラリには、OLE DB 初期アプリケーションの作成をサポートするウィザードが付属しています。  
  
 このテンプレート ライブラリは 2 つの部分から構成されます。  
  
-   **OLE DB コンシューマー テンプレート** OLE DB クライアント \(コンシューマー\) アプリケーションの実装に使用します。  
  
-   **OLE DB プロバイダー テンプレート** OLE DB サーバー \(プロバイダー\) アプリケーションの実装に使用します。  
  
 OLE DB テンプレートを使用するには、C\+\+ テンプレート、COM、および OLE DB インターフェイスに関する知識が必要です。  OLE DB についてあまり知識がない場合は、「[OLE DB Programmer's Reference](https://msdn.microsoft.com/en-us/library/ms713643.aspx)」を参照してください。  
  
 ほかにも、次の事項が役立ちます。  
  
-   [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)または [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)に関するトピックを参照します。  
  
-   [OLE DB コンシューマー](../../data/oledb/creating-an-ole-db-consumer.md)または [OLE DB プロバイダー](../../data/oledb/creating-an-ole-db-provider.md)を作成します。  
  
-   [OLE DB コンシューマー クラス](../../data/oledb/ole-db-consumer-templates-reference.md)または [OLE DB プロバイダー クラス](../../data/oledb/ole-db-provider-templates-reference.md)の一覧を参照します。  
  
-   [OLE DB テンプレート サンプル](http://msdn.microsoft.com/ja-jp/08958863-0b5f-41ad-ae99-fca7440c553c)の一覧を参照します。  
  
-   「[OLE DB Programmer's Reference](https://msdn.microsoft.com/en-us/library/ms713643.aspx)」\([!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)]\) を参照してください。  
  
## OLE DB 属性  
 [OLE DB コンシューマー属性](../../windows/ole-db-consumer-attributes.md)には、OLE DB コンシューマーを簡単に作成する方法が用意されています。  OLE DB 属性は、[OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-reference.md)に基づいてコードを挿入し、OLE DB コンシューマーとプロバイダーを作成します。  属性でサポートされていない機能を指定する場合は、コード内で OLE DB テンプレートを属性と組み合わせて使用できます。  
  
## MFC OLE DB クラス  
 MFC ライブラリには、データベース レコードをコントロールに表示する [COleDBRecordView](../../mfc/reference/coledbrecordview-class.md) という 1 つのクラスが含まれています。  ビューは、`CRowset` オブジェクトに直接接続されるフォーム ビューであり、`CRowset` オブジェクトのフィールドをダイアログ テンプレートのコントロールに表示します。  最初、次、前、または最後のレコードに移動するための既定の実装と、ビューに現在表示されているレコードを更新するインターフェイスも用意されています。  詳細については、「`COleDBRecordView`」を参照してください。  
  
## OLE DB SDK インターフェイス  
 OLE DB テンプレートが OLE DB 機能をサポートしていない場合は、OLE DB インターフェイス自体を使用する必要があります。  詳細については、[!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)] の「[OLE DB Programmer's Reference](https://msdn.microsoft.com/en-us/library/ms713643.aspx)」を参照してください。  
  
## 参照  
 [OLE DB プログラミング](../../data/oledb/ole-db-programming.md)   
 [OLE DB プログラミングの概要](../../data/oledb/ole-db-programming-overview.md)