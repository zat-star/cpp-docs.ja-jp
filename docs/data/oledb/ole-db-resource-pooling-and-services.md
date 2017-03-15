---
title: "OLE DB リソース プールとサービス | Microsoft Docs"
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
  - "OLE DB プロバイダー, リソース プール"
  - "OLE DB サービス [OLE DB]"
  - "OLE DB サービス [OLE DB], プロバイダーの必要条件"
  - "OLE DB, リソース プール"
  - "リソース プール [OLE DB], プロバイダーの必要条件"
  - "サービス プロバイダー [OLE DB]"
ms.assetid: 360c36e2-25ae-4caf-8ee7-d4a6b6898f68
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# OLE DB リソース プールとサービス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE DB プールまたは任意の OLE DB サービスを使用するには、プロバイダーはすべてのオブジェクトの集約をサポートする必要があります。  これは、OLE DB 1.5 以降のすべてのプロバイダーの要件です。  これはサービスの利用に不可欠です。  集約をサポートしないプロバイダーはプールできないため、追加のサービスを利用できません。  
  
 プールするには、プロバイダーがフリー スレッド モデルをサポートしている必要があります。  リソース プールは、**DBPROP\_THREADMODEL** プロパティに基づいてプロバイダーのスレッド モデルを判断します。  
  
 データ ソースが初期化状態にあるときに、変更される可能性のあるグローバル接続状態にプロバイダーがある場合は、新しい **DBPROP\_RESETDATASOURCE** プロパティをサポートする必要があります。  このプロパティは、接続が再利用される前に呼び出され、次に使用される前に状態をクリーンアップする機会をプロバイダーに与えます。  プロバイダーは、接続に関連付けられている状態をクリーンアップできない場合、プロパティに対して **DBPROPSTATUS\_NOTSETTABLE** を返すことができます。この場合は、接続が再利用されません。  
  
 リモート データベースに接続し、その接続が失われたかどうかを検出できるプロバイダーは、**DBPROP\_CONNECTIONSTATUS** プロパティをサポートする必要があります。  このプロパティは、OLE DB サービスに対して切断された接続を検出し、それらがプールに返されていないことを確認する機能を与えます。  
  
 最後に、自動トランザクション確保は、一般にプールの発生と同じレベルで実装されていない限り動作しません。  自動トランザクション確保をサポートするプロバイダーは、**DBPROP\_INIT\_OLEDBSERVICES** プロパティを公開し、**DBPROPVAL\_OS\_TXNENLISTMENT** が選択解除された場合に確保を無効にすることにより、この確保の無効化をサポートする必要があります。  
  
## 参照  
 [高度なプロバイダー手法](../Topic/Advanced%20Provider%20Techniques.md)