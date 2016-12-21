---
title: "PROPERTY_INFO_ENTRY_EX | Microsoft Docs"
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
  - "PROPERTY_INFO_ENTRY_EX"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PROPERTY_INFO_ENTRY_EX マクロ"
ms.assetid: af32dfcd-4c50-449d-af3b-48d21bd67a04
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# PROPERTY_INFO_ENTRY_EX
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プロパティ セットの特定のプロパティを表します。  
  
## 構文  
  
```  
  
PROPERTY_INFO_ENTRY_EX(  
dwPropID  
,  
vt  
,  
dwFlags  
,  
value  
,  
options  
)  
  
```  
  
#### パラメーター  
 *dwPropID*  
 \[入力\] プロパティ セット GUID と組み合わせて使用してプロパティを特定する [DBPROPID](https://msdn.microsoft.com/en-us/library/ms723882.aspx) 値。  
  
 *vt*  
 \[入力\] このプロパティ エントリの [VARTYPE](http://msdn.microsoft.com/ja-jp/317b911b-1805-402d-a9cb-159546bc88b4)。  
  
 `dwFlags`  
 \[入力\] このプロパティ エントリを記述している [DBPROPFLAGS](https://msdn.microsoft.com/en-us/library/ms724342.aspx) 値。  
  
 *値*  
 \[入力\] `DWORD` 型のプロパティ値。  
  
 `options`  
 **DBPROPOPTIONS\_REQUIRED** または **DBPROPOPTIONS\_SETIFCHEAP**。 通常、`options` はコンシューマーによって設定されるため、プロバイダーが設定する必要はありません。  
  
## 解説  
 このマクロでは、オプションとフラグだけでなく、`DWORD` 型のプロパティの値を直接指定できます。 単にプロパティを ATLDB.H に定義されている既定値に設定するには、[PROPERTY\_INFO\_ENTRY](../../data/oledb/property-info-entry.md) を使用します。 オプションやフラグを設定せずに任意の値にプロパティを設定するには、[PROPERTY\_INFO\_ENTRY\_VALUE](../../data/oledb/property-info-entry-value.md) を使用します。  
  
## 使用例  
 「[BEGIN\_PROPSET\_MAP](../Topic/BEGIN_PROPSET_MAP.md)」を参照してください。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [OLE DB プロバイダー テンプレート用マクロ](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)   
 [OLE DB プロバイダーの作成](../../data/oledb/creating-an-ole-db-provider.md)