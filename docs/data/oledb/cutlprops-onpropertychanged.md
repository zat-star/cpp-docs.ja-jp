---
title: "CUtlProps::OnPropertyChanged | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "OnPropertyChanged"
  - "CUtlProps.OnPropertyChanged"
  - "CUtlProps::OnPropertyChanged"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OnPropertyChanged メソッド"
ms.assetid: c5924210-b685-46c4-87f8-1b81e5bd3378
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# CUtlProps::OnPropertyChanged
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ハンドルへのプロパティを設定するというプロパティを連結します。  
  
## 構文  
  
```  
  
      virtual HRESULT OnPropertyChanged(  
   ULONG /* iCurSet */,  
   DBPROP* pDBProp   
);  
```  
  
#### パラメーター  
 `iCurSet`  
 プロパティ セットの配列にインデックス; プロパティ セットを 1 回だけの場合はゼロ。  
  
 `pDBProp`  
 [DBPROP](https://msdn.microsoft.com/en-us/library/ms717970.aspx) 構造体のプロパティ ID と新しい値。  
  
## 戻り値  
 標準の `HRESULT` を返します。  既定の戻り値は `S_OK`です。  
  
## 解説  
 チェーンされたプロパティを処理したい場合は、ブックマークなど\) またはユーザーの値が他方の値に依存している場合、この関数をオーバーライドする必要があります。更新します。  
  
## 使用例  
 この関数では、ユーザーが `DBPROP*` パラメーターからプロパティ ID を取得します。  次に、チェーンとプロパティに対して ID を比較することができます。  プロパティを設定すると、`SetProperties` は、他のプロパティとともに設定されたプロパティと呼ばれます。  この場合、1 は `DBPROP_IRowsetLocate`、`DBPROP_LITERALBOOKMARKS`、または `DBPROP_ORDEREDBOOKMARKS` のプロパティを取得すると、1 は `DBPROP_BOOKMARKS` のプロパティを設定できます。  
  
 [!CODE [NVC_OLEDB_Provider#2](../CodeSnippet/VS_Snippets_Cpp/NVC_OLEDB_Provider#2)]  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [CUtlProps クラス](../../data/oledb/cutlprops-class.md)