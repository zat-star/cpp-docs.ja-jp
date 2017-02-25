---
title: "ASP、ATL Active Server Page コンポーネント ウィザード | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.codewiz.class.atl.asp.asp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL Active Server Page コンポーネント ウィザード、ASP"
ms.assetid: 4d8cafd6-5e12-4461-8911-29288896af3c
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# ASP、ATL Active Server Page コンポーネント ウィザード
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ATL Active Server Page コンポーネント ウィザードのこのページを使用して、ASP コンポーネントに関連する情報や状態を処理するためのオプションを設定します。  
  
 **追加のメソッド**  
 オプションの ASP メソッド **OnStartPage** と **OnEndPage** がプロジェクトに追加されます。  Active Server Pages の組み込みオブジェクトを設定するには、このオプションを選択する必要があります。  既定では既に選択されています。  
  
-   **OnStartPage\/OnEndPage** [OnStartPage](https://msdn.microsoft.com/en-us/library/ms691624.aspx) は、初めてスクリプトがオブジェクトへのアクセスを試みるときに呼び出されます。  **OnEndPage** は、オブジェクトでのスクリプト処理の終了時に呼び出されます。  
  
 **組み込みオブジェクト**  
 ASP の組み込みオブジェクトを設定するには、\[OnStartPage\/OnEndPage\] を選択する必要があります。  
  
|オプション|説明|  
|-----------|--------|  
|**要求**|Active Server Pages の組み込みの **Request** オブジェクトに対するアクセスを指定します。  **Request** オブジェクトは HTTP リクエストを渡すために使用されます。|  
|**応答**|Active Server Pages の組み込みの **Response** オブジェクトに対するアクセスを指定します。  リクエストに対する応答として、**Response** オブジェクトはユーザー用に表示する情報をブラウザーに送信します。|  
|**Session**|Active Server Pages の組み込みの **Session** オブジェクトに対するアクセスを指定します。  **Session** オブジェクトは、現在のユーザー セッションの情報を保持します。ステータス情報の格納と取得も行われます。|  
|**アプリケーション**|Active Server Pages の組み込みの **Application** オブジェクトに対するアクセスを指定します。  **Application** オブジェクトは、複数の ASP オブジェクトで共有される状態を管理します。|  
|**サーバー**|Active Server Pages の組み込みの **Server** オブジェクトに対するアクセスを指定します。  **Server** オブジェクトを使用すると、ほかの ASP オブジェクトを作成できます。|  
  
## 参照  
 [ATL Active Server Pages コンポーネント ウィザード](../../atl/reference/atl-active-server-page-component-wizard.md)   
 [ATL Active Server Page Component](../../atl/reference/adding-an-atl-active-server-page-component.md)