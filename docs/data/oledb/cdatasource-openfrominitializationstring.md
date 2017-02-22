---
title: "CDataSource::OpenFromInitializationString | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDataSource.OpenFromInitializationString"
  - "OpenFromInitializationString"
  - "CDataSource::OpenFromInitializationString"
  - "ATL::CDataSource::OpenFromInitializationString"
  - "ATL.CDataSource.OpenFromInitializationString"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OpenFromInitializationString メソッド"
ms.assetid: 5ef1f1fd-92a9-4e1c-ad80-d3601b094b8c
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# CDataSource::OpenFromInitializationString
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ユーザーが入力した初期化文字列で指定されるデータ ソースを開きます。  
  
## 構文  
  
```  
  
      HRESULT OpenFromInitializationString(   
   LPCOLESTR szInitializationString,   
   bool fPromptForInfo = false    
) throw( );  
```  
  
#### パラメーター  
 *szInitializationString*  
 \[入力\] 初期化文字列。  
  
 *fPromptForInfo*  
 \[入力\] この引数に **true** を指定すると、`OpenFromInitializationString` は **DBPROP\_INIT\_PROMPT** プロパティを **DBPROMPT\_COMPLETEREQUIRED** に設定します。この結果、必要な情報がある場合にだけ、ユーザーに入力を要求するようになります。  これは、初期化文字列がパスワードを必要とするデータベースを指定しているのに、初期化文字列内にパスワードが入っていない場合に便利です。  ユーザーは、データベースに接続しようとしたときにパスワード \(または、その他の見つからない情報\) の入力を求められます。  
  
 既定値は **false** です。この場合、ユーザー入力が要求されることはありません。**DBPROP\_INIT\_PROMPT** が **DBPROMPT\_NOPROMPT** に設定されます。  
  
## 戻り値  
 標準の `HRESULT` を返します。  
  
## 解説  
 このメソッドは、oledb32.dll 内のサービス コンポーネントを使ってデータ ソース オブジェクトを開きます。この DLL には、リソース プーリング、自動トランザクション参加などのサービス コンポーネント機能の実装が含まれています。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CDataSource クラス](../Topic/CDataSource%20Class.md)