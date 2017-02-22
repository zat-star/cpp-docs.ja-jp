---
title: "データ アクセス: ADO および RDO | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "バインド コントロール [C++], ADO"
  - "バインド コントロール [C++], RDO"
  - "コントロール [C++], データ バインド"
  - "データ アクセス [C++], RDO のデータ コントロール"
  - "データ バインディング [C++], ADO"
  - "データ バインディング [C++], RDO"
  - "データ コントロール [C++]"
  - "データ バインド コントロール [C++], ADO"
  - "データ バインド コントロール [C++], RDO"
ms.assetid: 92da8f1e-144b-4605-ac0a-43c25bdc14a7
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# データ アクセス: ADO および RDO
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

データ ソース コントロールまたはデータ バインド コントロールをサポートする基本的な 2 つのテクノロジを次に示します。  
  
 **ADO**  
 ADO は、OLE DB の COM ラッパーです。ADO を使用すると、データ アクセス アプリケーション \(コンシューマー\) を簡単に作成できます。  COM ベースの汎用データ アクセス技術である OLE DB を使用すると、ISAM \(Indexed Sequential Access Method\) および SQL ベースのデータベースのほか、あらゆるデータ ソースを利用できます。  
  
 OLE DB プロバイダーは、さまざまなデータ ソースのデータにアクセスでき、SQL クエリのほか、プロバイダーで定義したクエリでも、データを取得できます。  
  
 **RDO**  
 RDO は、ODBC の COM ラッパーです。  ODBC は、C 言語ベースの API であり、汎用的な \(異種データ ソース間での\) データ アクセスを行うことができます。  ただし、RDO では、データ アクセス用のコマンド言語として、SQL を使用する必要があります。  
  
 RDO ベースのデータ アクセス コントロールではなく ADO ベースのデータ アクセス コントロールを使用することをお勧めします。  
  
 ADO データ コントロールと RDO データ コントロールの主な相違点を次に示します。  
  
 **データ バインド コントロール**  
 RDO データ連結コントロールは、**ICursor** インターフェイスを使用します。一方、ADO データ連結コントロールは、OLE DB `IRowset` インターフェイスを使用します。  どちらのインターフェイスも、行セットを返します。  
  
 RDO データ連結コントロールは、Visual Basic 向けにデザインされています。  したがって、RDO データ連結コントロールの一部の機能 \(特に書式化機能\) は、Visual C\+\+ で作成したアプリケーションで利用できません。  ADO データ連結コントロールでは、このような問題はありません。  
  
 **Data コントロール**  
 ADO データ コントロールは、**IDataSource** インターフェイスを実装しています。RDO データ コントロールは、**IVBDSC** インターフェイスを実装しています。  `IRowset` インターフェイス ポインターを取得するには、**IDataSource** のメソッドを呼び出します。  同様に、**ICursor** インターフェイス ポインターを取得するには、IVBDSC のメソッドを呼び出します。  
  
## 参照  
 [Visual C\+\+ で ActiveX コントロールによるデータ連結を行う](../../data/ado-rdo/databinding-with-activex-controls-in-visual-cpp.md)