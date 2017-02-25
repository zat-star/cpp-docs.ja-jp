---
title: "SET_PARAM_TYPE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SET_PARAM_TYPE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SET_PARAM_TYPE マクロ"
ms.assetid: 85979070-2d55-4c67-94b1-9b9058babc59
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# SET_PARAM_TYPE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`SET_PARAM_TYPE` マクロの後に続く `COLUMN_ENTRY` マクロが入力、出力、入出力のいずれであるかを指定します。  
  
## 構文  
  
```  
  
SET_PARAM_TYPE(  
type  
 )  
  
```  
  
#### パラメーター  
 `type`  
 \[入力\] 設定するパラメーターの種類。  
  
## 解説  
 プロバイダーは、基になるデータ ソースによってサポートされているパラメーター入出力タイプだけをサポートします。 type は、1 つ以上の **DBPARAMIO** 値の組み合わせです \(*OLE DB プログラマーズ リファレンス*の「[DBBINDING Structures \(DBBINDING 構造体\)](https://msdn.microsoft.com/en-us/library/ms716845.aspx)」を参照してください\)。  
  
-   **DBPARAMIO\_NOTPARAM** アクセサーにパラメーターがありません。 通常、行アクセサーで **eParamIO** をこの値に設定して、パラメーターが無視されることをユーザーに知らせます。  
  
-   **DBPARAMIO\_INPUT** 入力パラメーター。  
  
-   **DBPARAMIO\_OUTPUT** 出力パラメーター。  
  
-   **DBPARAMIO\_INPUT &#124; DBPARAMIO\_OUTPUT** パラメーターは入力パラメーターと出力パラメーターの両方です。  
  
## 使用例  
 [!CODE [NVC_OLEDB_Consumer#18](../CodeSnippet/VS_Snippets_Cpp/NVC_OLEDB_Consumer#18)]  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [OLE DB コンシューマー テンプレート用マクロおよびグローバル関数](../Topic/Macros%20and%20Global%20Functions%20for%20OLE%20DB%20Consumer%20Templates.md)