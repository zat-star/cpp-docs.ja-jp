---
title: "CDaoFieldExchange クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDaoFieldExchange"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoFieldExchange クラス"
  - "DAO (データ アクセス オブジェクト), レコード フィールド エクスチェンジ (DFX)"
  - "DFX (DAO レコード フィールド エクスチェンジ)"
  - "DFX (DAO レコード フィールド エクスチェンジ), DAO レコード フィールド エクスチェンジ"
  - "交換 (データベースとレコードセット間でデータを)"
  - "フィールド エクチェンジ"
  - "フィールド エクチェンジ, レコード (DAO クラスの)"
  - "RFX (レコード フィールド エクスチェンジ)"
  - "RFX (レコード フィールド エクスチェンジ), DAO クラス"
ms.assetid: 350a663e-92ff-44ab-ad53-d94efa2e5823
caps.latest.revision: 23
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDaoFieldExchange クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

DAO データベース クラスで使われる DAO レコード フィールド エクスチェンジ \(DFX: DAO Record Field eXchange\) ルーチンをサポートします。  
  
## 構文  
  
```  
class CDaoFieldExchange  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CDaoFieldExchange::IsValidOperation](../Topic/CDaoFieldExchange::IsValidOperation.md)|現在の操作が更新されるフィールドの種類に適したの場合はを返します。|  
|[CDaoFieldExchange::SetFieldType](../Topic/CDaoFieldExchange::SetFieldType.md)|DFX にすべての後続の呼び出しによって表されるレコードセット データ メンバーの型である列またはパラメーター—機能します `SetFieldType`に次の呼び出しまで指定します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CDaoFieldExchange::m\_nOperation](../Topic/CDaoFieldExchange::m_nOperation.md)|レコードセットの `DoFieldExchange` のメンバー関数、現在の呼び出しによって実行される DFX の操作。|  
|[CDaoFieldExchange::m\_prs](../Topic/CDaoFieldExchange::m_prs.md)|DFX の操作が行われているレコードセットへのポインター。|  
  
## 解説  
 `CDaoFieldExchange` には、基本クラスはありません。  
  
 カスタム データ型のデータ エクスチェンジ ルーチンを記述する場合は、このクラスを使用してください; それ以外の場合は、このクラスを直接使用しません。  [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) のオブジェクトのフィールド データ メンバーとデータ ソースの間の DFX 対応するフィールド データを交換します。  DFX は両方向の、データ ソースのとデータ ソースへの交換を管理します。  書き込み DFX カスタム ルーチンについては、[テクニカル ノート 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md) を参照してください。  
  
> [!NOTE]
>  DAO データベース クラスは、ODBC \(Open Database Connectivity\) に基づく MFC データベース クラスとは異なります。  すべての DAO データベース クラス名に「CDao」が付きます。  まだ DAO クラスと ODBC データ ソースにアクセスできます。  一般に、に基づく MFC DAO クラスは、ODBC に基づいて MFC クラスよりもできます。  DAO ベースのクラスには独自のデータベース エンジンで ODBC ドライバーを通じて、含むデータにアクセスできます。  また、DAO クラスで独自を呼び出してせずにテーブルを追加するなどのデータ定義言語の \(DDL\) の操作をサポートしています。  
  
> [!NOTE]
>  DAO レコード フィールド エクスチェンジ \(DFX\) は、ODBC ベースの MFC データベース クラス \(`CDatabase`、`CRecordset`\) のレコード フィールド エクスチェンジ \(RFX\) とよく似ています。  RFX を理解する場合は、使いやすい DFX 検索します。  
  
 `CDaoFieldExchange` のオブジェクトは DAO レコード フィールド エクスチェンジで発生するために必要なコンテキスト情報を提供します。  `CDaoFieldExchange` のオブジェクトは、現在のレコードのフィールドの結合のパラメーター、フィールド データ メンバーと設定のさまざまなフラグが含まれる多数の操作をサポートしています。  DFX の操作は `CDaoFieldExchange`で `enum`**FieldType** によって定義される型のレコードセット クラスのデータ メンバーで実行されます。  **FieldType** の値は次のとおりです:  
  
-   フィールド データ メンバーの**CDaoFieldExchange::outputColumn**。  
  
-   パラメーター データ メンバーの**CDaoFieldExchange::param**。  
  
 [IsValidOperation](../Topic/CDaoFieldExchange::IsValidOperation.md) のメンバー関数は独自のカスタム DFX のルーチンを記述するために使用されます。  [CDaoRecordset::DoFieldExchange](../Topic/CDaoRecordset::DoFieldExchange.md) の関数で [SetFieldType](../Topic/CDaoFieldExchange::SetFieldType.md) を頻繁に使用します。  DFX のグローバル関数の詳細については、[レコード フィールド エクスチェンジ関数](../../mfc/reference/record-field-exchange-functions.md)を参照してください。  独自のデータ型の書き込み DFX カスタム ルーチンについては、[テクニカル ノート 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md)を参照してください。  
  
## 継承階層  
 `CDaoFieldExchange`  
  
## 必要条件  
 **Header:** afxdao.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDaoRecordset クラス](../../mfc/reference/cdaorecordset-class.md)