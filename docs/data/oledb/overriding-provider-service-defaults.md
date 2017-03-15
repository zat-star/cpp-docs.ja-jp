---
title: "プロバイダー サービスの既定のオーバーライド | Microsoft Docs"
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
  - "OLE DB サービス [OLE DB], オーバーライド (既定値を)"
  - "サービス プロバイダー [OLE DB]"
ms.assetid: 08e366c0-74d8-463b-93a6-d58a8dc195f8
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# プロバイダー サービスの既定のオーバーライド
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プロバイダーの **OLEDB\_SERVICES** のレジストリ値は、データ ソース オブジェクトの [DBPROP\_INIT\_OLEDBSERVICES](https://msdn.microsoft.com/en-us/library/ms716898.aspx) 初期化プロパティの既定値として返されます。  
  
 レジストリ エントリが存在する限り、プロバイダーのオブジェクトは集約されます。ユーザーは初期化の前に **DBPROP\_INIT\_OLEDBSERVICES** プロパティを設定することにより、プロバイダーの有効なサービスの既定の設定をオーバーライドできます。  特定のサービスを有効または無効にするために、一般には、**DBPROP\_INIT\_OLEDBSERVICES** プロパティの現在値を取得し、有効または無効にする特定のプロパティのビットを設定またはクリアして、プロパティのリセットを行います。  **DBPROP\_INIT\_OLEDBSERVICES** は、OLE DB で直接設定するか、ADO または **IDataInitialize::GetDatasource** に渡される接続文字列で設定できます。  各サービスを有効または無効にする値を次の表に示します。  
  
|既定の有効なサービス|DBPROP\_INIT\_OLEDBSERVICES プロパティ値|接続文字列内の値|  
|----------------|----------------------------------------|--------------|  
|すべてのサービス \(既定\)|**DBPROPVAL\_OS\_ENABLEALL**|"OLE DB Services \= \-1;"|  
|プールと自動確保を除くすべて|**DBPROPVAL\_OS\_ENABLEALL &**<br /><br /> **~DBPROPVAL\_OS\_RESOURCEPOOLING &**<br /><br /> **~DBPROPVAL\_OS\_TXNENLISTMENT**|"OLE DB Services \= \-4;"|  
|クライアント カーソルを除くすべて|**DBPROPVAL\_OS\_ENABLEALL**&<br /><br /> ~**DBPROPVAL\_OS\_CLIENTCURSOR**|"OLE DB Services \= \-5;"|  
|プール、自動確保、およびクライアント カーソルを除くすべて|**DBPROPVAL\_OS\_ENABLEALL &**<br /><br /> **~DBPROPVAL\_OS\_TXNENLISTMENT &**<br /><br /> **~DBPROPVAL\_OS\_CLIENTCURSOR**|"OLE DB Services \= \-7;"|  
|サービスなし|~**DBPROPVAL\_OS\_ENABLEALL**|"OLE DB Services \= 0;"|  
  
 レジストリ エントリがプロバイダーに対して存在しない場合、コンポーネント マネージャーはプロバイダーのオブジェクトを集約せず、ユーザーにより明示的に要求された場合でもサービスは起動しません。  
  
## 参照  
 [Resource Pooling](https://msdn.microsoft.com/en-us/library/ms713655.aspx)   
 [How Consumers Use Resource Pooling](https://msdn.microsoft.com/en-us/library/ms715907.aspx)   
 [How Providers Work Effectively with Resource Pooling](https://msdn.microsoft.com/en-us/library/ms714906.aspx)   
 [OLE DB サービスの有効化と無効化](../../data/oledb/enabling-and-disabling-ole-db-services.md)