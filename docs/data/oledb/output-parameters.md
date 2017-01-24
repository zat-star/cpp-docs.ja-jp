---
title: "出力パラメーター | Microsoft Docs"
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
  - "OLE DB, ストアド プロシージャ"
  - "プロシージャ呼び出し"
  - "プロシージャ呼び出し, ストアド プロシージャ"
  - "ストアド プロシージャ, 呼び出し"
  - "ストアド プロシージャ, パラメーター"
ms.assetid: 4f7c2700-1c2d-42f3-8c9f-7e83962b2442
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 出力パラメーター
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ストアド プロシージャの呼び出しは、SQL コマンドの呼び出しと似ています。  主な違いは、ストアド プロシージャが出力パラメーターと戻り値を使用することです。  
  
 次のストアド プロシージャでは、最初の "?" が戻り値 \(phone\) で、2 番目の "?" が入力パラメーター \(name\) です。  
  
```  
DEFINE_COMMAND(CMySProcAccessor, _T("{ ? = SELECT phone FROM shippers WHERE name = ? }")  
```  
  
 パラメーター マップで、入力パラメーターと出力パラメーターを指定します。  
  
```  
BEGIN_PARAM_MAP(CMySProcAccessor)  
   SET_PARAM_TYPE(DBPARAMIO_OUTPUT)  
   COLUMN_ENTRY(1, m_Phone)   // Phone is the return value  
   SET_PARAM_TYPE(DBPARAMIO_INPUT)  
   COLUMN_ENTRY(2, m_Name)   // Name is the input parameter  
END_PARAM_MAP()  
```  
  
 アプリケーションでは、ストアド プロシージャから返された出力を処理する必要があります。  別の OLE DB プロバイダーが、結果の処理中に別の時点で出力パラメーターと戻り値を返します。  たとえば、SQL Server 用の Microsoft OLE DB プロバイダー \(SQLOLEDB\) は、ストアド プロシージャから返された結果セットがコンシューマーによって取得または取り消されるまで、出力パラメーターとリターン コードを提供しません。  出力は、サーバーからの最後の TDS パケットで返されます。  
  
## 行数  
 OLE DB コンシューマー テンプレートを使用して、出力パラメーターを持つストアド プロシージャを実行する場合は、行セットを閉じるまで行数が設定されません。  
  
 たとえば、1 つの行セットと 1 つの出力パラメーターがあるストアド プロシージャについて考えます。  
  
```  
create procedure sp_test  
   @_rowcount integer output  
as  
   select top 50 * from test  
   @_rowcount = @@rowcount  
return 0  
```  
  
 @\_rowcount 出力パラメーターは、test テーブルから実際に返された行数を報告します。  ただし、このストアド プロシージャでは、最大行数が 50 に制限されます。  たとえば、test テーブルに 100 行ある場合、このコードは先頭の 50 行だけを取得するため、rowcount は 50 になります。  テーブルに 30 行しかない場合、rowcount は 30 になります。  この値をフェッチする前に、**Close** または **CloseAll** を呼び出して、出力パラメーターにデータを設定する必要があります。  
  
## 参照  
 [ストアド プロシージャの使用](../../data/oledb/using-stored-procedures.md)