---
title: "CDaoTableDef クラス | Microsoft Docs"
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
  - "CDaoTableDef"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoTableDef クラス"
  - "データベース クラス [C++], DAO"
  - "データベース テーブル [C++], アタッチされたテーブル定義"
  - "データベース テーブル [C++], ベース テーブルの定義"
  - "テーブル定義 [C++]"
ms.assetid: 7c5d2254-8475-43c4-8a6c-2d32ead194c9
caps.latest.revision: 24
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDaoTableDef クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ベース テーブル、またはアタッチ テーブルの格納された定義を表現します。  
  
## 構文  
  
```  
class CDaoTableDef : public CObject  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CDaoTableDef::CDaoTableDef](../Topic/CDaoTableDef::CDaoTableDef.md)|**CDaoTableDef** オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CDaoTableDef::Append](../Topic/CDaoTableDef::Append.md)|データベースに新しいテーブルが追加されます。|  
|[CDaoTableDef::CanUpdate](../Topic/CDaoTableDef::CanUpdate.md)|テーブルが更新できる場合はゼロを返します \(フィールドまたはテーブルのプロパティの定義を変更できます\)。|  
|[CDaoTableDef::Close](../Topic/CDaoTableDef::Close.md)|開いている tabledef を閉じます。|  
|[CDaoTableDef::Create](../Topic/CDaoTableDef::Create.md)|[&#91;追加&#93;](../Topic/CDaoTableDef::Append.md)を使用してデータベースに追加できるテーブルを作成します。|  
|[CDaoTableDef::CreateField](../Topic/CDaoTableDef::CreateField.md)|テーブルのフィールドを作成するために呼び出されます。|  
|[CDaoTableDef::CreateIndex](../Topic/CDaoTableDef::CreateIndex.md)|テーブルのインデックスを作成するために呼び出されます。|  
|[CDaoTableDef::DeleteField](../Topic/CDaoTableDef::DeleteField.md)|テーブルのフィールドを削除するために呼び出されます。|  
|[CDaoTableDef::DeleteIndex](../Topic/CDaoTableDef::DeleteIndex.md)|テーブルのインデックスを削除するために呼び出されます。|  
|[CDaoTableDef::GetAttributes](../Topic/CDaoTableDef::GetAttributes.md)|`CDaoTableDef` のオブジェクトの一つ以上の特性を示す値を返します。|  
|[CDaoTableDef::GetConnect](../Topic/CDaoTableDef::GetConnect.md)|テーブル ソースに関する情報を提供する値を返します。|  
|[CDaoTableDef::GetDateCreated](../Topic/CDaoTableDef::GetDateCreated.md)|返します `CDaoTableDef` のオブジェクトの基になるベース テーブルが作成された日時。|  
|[CDaoTableDef::GetDateLastUpdated](../Topic/CDaoTableDef::GetDateLastUpdated.md)|行われたベース テーブルのデザインに対する直前の変更の日時を返します。|  
|[CDaoTableDef::GetFieldCount](../Topic/CDaoTableDef::GetFieldCount.md)|テーブルのフィールド数を表す値を返します。|  
|[CDaoTableDef::GetFieldInfo](../Topic/CDaoTableDef::GetFieldInfo.md)|特定の種類の表のフィールドに関する情報を返します。|  
|[CDaoTableDef::GetIndexCount](../Topic/CDaoTableDef::GetIndexCount.md)|テーブルのインデックスの数を返します。|  
|[CDaoTableDef::GetIndexInfo](../Topic/CDaoTableDef::GetIndexInfo.md)|特定の種類のテーブルのインデックスに関する情報を返します。|  
|[CDaoTableDef::GetName](../Topic/CDaoTableDef::GetName.md)|テーブルのユーザー定義の名前を返します。|  
|[CDaoTableDef::GetRecordCount](../Topic/CDaoTableDef::GetRecordCount.md)|テーブル内のレコード数を返します。|  
|[CDaoTableDef::GetSourceTableName](../Topic/CDaoTableDef::GetSourceTableName.md)|ソース データベースにアタッチ テーブルの名前を示す値を返します。|  
|[CDaoTableDef::GetValidationRule](../Topic/CDaoTableDef::GetValidationRule.md)|テーブルに変更または追加されるたびにフィールドにデータを検証する値を返します。|  
|[CDaoTableDef::GetValidationText](../Topic/CDaoTableDef::GetValidationText.md)|オブジェクトのフィールドの値が指定された検証規則を満たすアプリケーションが表示するメッセージのテキストを指定する値を返します。|  
|[CDaoTableDef::IsOpen](../Topic/CDaoTableDef::IsOpen.md)|テーブルが開いている場合は、を返します。|  
|[CDaoTableDef::Open](../Topic/CDaoTableDef::Open.md)|データベースの TableDef のコレクションに格納されている既存の tabledef を開きます。|  
|[CDaoTableDef::RefreshLink](../Topic/CDaoTableDef::RefreshLink.md)|アタッチ テーブルの接続情報を更新します。|  
|[CDaoTableDef::SetAttributes](../Topic/CDaoTableDef::SetAttributes.md)|`CDaoTableDef` のオブジェクトの一つ以上の特性を示す値を設定します。|  
|[CDaoTableDef::SetConnect](../Topic/CDaoTableDef::SetConnect.md)|テーブル ソースに関する情報を提供する値を設定します。|  
|[CDaoTableDef::SetName](../Topic/CDaoTableDef::SetName.md)|テーブルの名前を設定します。|  
|[CDaoTableDef::SetSourceTableName](../Topic/CDaoTableDef::SetSourceTableName.md)|ソース データベースにアタッチ テーブルの名前を指定する値を設定します。|  
|[CDaoTableDef::SetValidationRule](../Topic/CDaoTableDef::SetValidationRule.md)|テーブルに変更または追加されるたびにフィールドにデータを検証する値を設定します。|  
|[CDaoTableDef::SetValidationText](../Topic/CDaoTableDef::SetValidationText.md)|オブジェクトのフィールドの値が指定された検証規則を満たすアプリケーションが表示するメッセージのテキストを指定する値を設定します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CDaoTableDef::m\_pDAOTableDef](../Topic/CDaoTableDef::m_pDAOTableDef.md)|tabledef オブジェクトの下にある DAO インターフェイスへのポインター。|  
|[CDaoTableDef::m\_pDatabase](../Topic/CDaoTableDef::m_pDatabase.md)|このテーブルのソース データベース。|  
  
## 解説  
 各 DAO データベース オブジェクトはすべてに保存した DAO tabledef オブジェクトを含む TableDefs と呼ばれるコレクションを保持します。  
  
 `CDaoTableDef` のオブジェクトを使用してテーブル定義を処理します。  たとえば、次のように操作できます。  
  
-   アタッチされているデータベースのすべてのローカルまたは外部テーブルのフィールドとインデックス付き構造を確認します。  
  
-   アタッチ テーブルの `SetConnect` と `SetSourceTableName` のメンバー関数を呼び出し、アタッチ テーブルへの接続を更新するには `RefreshLink` のメンバー関数を使用します。  
  
-   テーブルのフィールド定義を編集できるかどうかを確認するに `CanUpdate` のメンバー関数を呼び出します。  
  
-   `GetValidationRule` と `SetValidationRule`を使用して検証の状態、および `GetValidationText` と `SetValidationText` のメンバー関数を取得または設定します。  
  
-   スナップショットの型 `CDaoRecordset` の表に、ダイナセット、またはオブジェクトを作成するために **\[開く\]** のメンバー関数を使用します。  
  
    > [!NOTE]
    >  DAO データベース クラスは、ODBC \(Open Database Connectivity\) に基づく MFC データベース クラスとは異なります。  すべての DAO データベース クラス名に「CDao」が付きます。  まだ DAO クラスと ODBC データ ソースにアクセスできます; DAO クラスは、一般に Microsoft Jet データベース エンジンに固有であるため、優れた機能を提供します。  
  
### 既存のテーブルを使用する、tabledef オブジェクトを使用するか、新しいテーブルを作成するには  
  
1.  いずれの場合も、最初にテーブルが属する [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) オブジェクトへのポインターを指定する `CDaoTableDef` のオブジェクトを構築します。  
  
2.  を与えない場合によっては、次する:  
  
    -   既存のを使用すると、テーブルを呼び出します。保存されたテーブルの名前を指定して tabledef オブジェクトの [&#91;開く&#93;](../Topic/CDaoTableDef::Open.md) のメンバー関数をしました。  
  
    -   新しいテーブルを作成するには、テーブルの名前を指定して tabledef オブジェクトの [&#91;作成&#93;](../Topic/CDaoTableDef::Create.md) のメンバー関数を呼び出します。  テーブルのフィールドとインデックスを追加するに [CreateField](../Topic/CDaoTableDef::CreateField.md) と [CreateIndex](../Topic/CDaoTableDef::CreateIndex.md) を呼び出します。  
  
    -   データベースの TableDefs のコレクションに追加してテーブルを保存するに [&#91;追加&#93;](../Topic/CDaoTableDef::Append.md) を呼び出します。  **\[作成\]** は、開いている状態に tabledef を入力するため、**\[作成\]** を呼び出した後 **\[開く\]**を呼び出さないでください。  
  
        > [!TIP]
        >  保存されたテーブルを作成する最も簡単な方法は、を作成し、Microsoft Access を使用して、データベースに格納します。  次に、MFC コードでそれらを開いて使用できます。  
  
 で、開くか、または作成し、tabledef オブジェクトを使用するには、`nOpenType` のパラメーターで **dbOpenTable** の値を持つ tabledef の名前を指定する `CDaoRecordset` のオブジェクトを作成してを開きます。  
  
 [CDaoRecordset::Open](../Topic/CDaoRecordset::Open.md)を呼び出すときに `CDaoRecordset` のオブジェクトを作成するには、tabledef オブジェクトを使用するには、通常、作成するか、tabledef を既に説明したように開けましたり、tabledef オブジェクトへのポインターを渡すレコードセット オブジェクトを構築します。  に渡す tabledef は、開いている状態である必要があります。  詳細については、クラス [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)を参照してください。  
  
 tabledef オブジェクトを使い終わったら [&#91;閉じる&#93;](../Topic/CDaoRecordset::Close.md) のメンバー関数を呼び出します。; その後、tabledef オブジェクトを破棄します。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CDaoTableDef`  
  
## 必要条件  
 **Header:** afxdao.h  
  
## 参照  
 [CObject クラス](../Topic/CObject%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDaoDatabase クラス](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoRecordset クラス](../../mfc/reference/cdaorecordset-class.md)