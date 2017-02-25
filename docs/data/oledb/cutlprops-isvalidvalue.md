---
title: "CUtlProps::IsValidValue | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CUtlProps::IsValidValue"
  - "CUtlProps.IsValidValue"
  - "IsValidValue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IsValidValue メソッド"
ms.assetid: 1164556e-8d98-429c-a396-fc9a699e0e97
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CUtlProps::IsValidValue
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プロパティを設定する前に値を検証するために使用します。  
  
## 構文  
  
```  
  
      virtual HRESULT CUtlPropsBase::IsValidValue(  
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
 プロパティを設定するように示されている、値で実行する検証ルーチンがある場合は、この関数をオーバーライドする必要があります。  たとえば、パスワード テーブルに対して有効な値を判断するに **DBPROP\_AUTH\_PASSWORD** を検証できます。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [CUtlProps クラス](../../data/oledb/cutlprops-class.md)