---
title: "CDaoRelationFieldInfo 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDaoRelationFieldInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoRelationFieldInfo 構造体"
  - "DAO (データ アクセス オブジェクト), Relations コレクション"
ms.assetid: 47cb89ca-dc80-47ce-96fd-cc4b88512558
caps.latest.revision: 13
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDaoRelationFieldInfo 構造体
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CDaoRelationFieldInfo` 構造体は、データ アクセス オブジェクト \(DAO\) に対して定義されたリレーションシップのフィールドに関する情報を格納します。  
  
## 構文  
  
```  
  
      struct CDaoRelationFieldInfo  
{  
   CString m_strName;           // Primary  
   CString m_strForeignName;    // Primary  
};  
```  
  
#### パラメーター  
 `m_strName`  
 リレーションシップの主テーブルのフィールドの名前。  
  
 `m_strForeignName`  
 リレーションシップの外部キー テーブルのフィールドの名前。  
  
## 解説  
 DAO のリレーションシップ オブジェクトは主テーブルのフィールドと外部キー テーブルのリレーションシップを定義するフィールドを指定します。  上の構造体の定義に対してへの参照は、クラス `CDaoDatabase`かの [GetRelationInfo](../Topic/CDaoDatabase::GetRelationInfo.md) のメンバー関数を呼び出すことによって情報を取得 [CDaoRelationInfo](../Topic/CDaoRelationInfo%20Structure.md) オブジェクトの `m_pFieldInfos` のメンバーに返されるかを示します。  
  
 Relation オブジェクトおよびリレーションシップを持つフィールド オブジェクトは MFC クラスでは表示されません。  代わりに、クラス [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) の MFC オブジェクトの下にある DAO オブジェクトが呼び出されるリレーションシップ オブジェクトのコレクションをリレーションシップのコレクションが含まれます。  各リレーションシップ オブジェクトは、リレーションシップを持つフィールド オブジェクトのコレクションが含まれます。  各リレーションシップのフィールドはオブジェクト外部キー テーブルのフィールドに主テーブルのフィールドに関連します。  同時に実行、リレーションシップを持つフィールド オブジェクトを一つのリレーションシップを定義する各テーブルのフィールドのグループを定義します。  `CDaoDatabase` は `GetRelationInfo` のメンバー関数を呼び出して、オブジェクトへの `CDaoRelationInfo` リレーションシップ オブジェクトにアクセスできるようにします。  `CDaoRelationInfo` オブジェクトにため、`CDaoRelationFieldInfo` オブジェクトの配列をデータ メンバー、`m_pFieldInfos`を指すことになります。  
  
 リレーションシップでコレクションが注目しているリレーションシップ オブジェクトに格納されている `CDaoDatabase` を含むオブジェクトの [GetRelationInfo](../Topic/CDaoDatabase::GetRelationInfo.md) メンバー関数を呼び出します。  次 [CDaoRelationInfo](../Topic/CDaoRelationInfo%20Structure.md) オブジェクトの `m_pFieldInfos` のメンバーにアクセスします。  `CDaoRelationFieldInfo` は、デバッグ ビルドの `Dump` のメンバー関数を定義します。  `CDaoRelationFieldInfo` オブジェクトの内容をダンプするために `Dump` を使用できます。  
  
## 必要条件  
 **ヘッダー:** afxdao.h  
  
## 参照  
 [構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoRelationInfo 構造体](../Topic/CDaoRelationInfo%20Structure.md)