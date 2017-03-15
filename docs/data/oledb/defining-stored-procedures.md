---
title: "ストアド プロシージャの定義 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
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
  - "ストアド プロシージャ, 定義"
  - "ストアド プロシージャ, OLE DB"
  - "ストアド プロシージャ, 構文"
ms.assetid: 54949b81-3275-4dd9-96e4-3eda1ed755f2
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# ストアド プロシージャの定義
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ストアド プロシージャを呼び出す前に、[DEFINE\_COMMAND](../../data/oledb/define-command.md) マクロを使用してストアド プロシージャを定義する必要があります。  コマンドを定義する場合は、パラメーターにパラメーター マーカーとして疑問符 \(?\) を付けてください。  
  
```  
DEFINE_COMMAND(CMySProcAccessor, _T("{INSERT {name, phone} into shippers  (?,?)}")  
```  
  
 このトピックのコード例で使用している構文 \(中かっこの使用など\) は、SQL Server 固有です。  ストアド プロシージャで使用する構文は、使用するプロバイダーによって異なる場合があります。  
  
 次に、パラメーター マップで、コマンドで使用したパラメーターを指定します。パラメーターは、コマンドで出現する順序で示します。  
  
```  
BEGIN_PARAM_MAP(CMySProcAccessor)  
   SET_PARAM_TYPE(DBPARAMIO_INPUT)  
   COLUMN_ENTRY(1, m_Name)   // name corresponds to first '?' param  
   SET_PARAM_TYPE(DBPARAMIO_INPUT)  
   COLUMN_ENTRY(2, m_Phone)  // phone corresponds to second '?' param  
END_PARAM_MAP()  
```  
  
 前の例では、ストアド プロシージャを定義しています。  通常は、コードを効率良く再利用するために、"Sales by Year" や "dt\_adduserobject" などの名前で定義されているストアド プロシージャのセットがデータセットに含まれています。SQL Server Enterprise Manager を使用して、これらの定義を表示できます。  これらのストアド プロシージャは、次のように呼び出します。"?" パラメーターの配置は、ストアド プロシージャのインターフェイスにより決定します。  
  
```  
DEFINE_COMMAND(CMySProcAccessor, _T("{CALL \"Sales by Year\" (?,?) }")  
DEFINE_COMMAND(CMySProcAccessor, _T("{CALL dbo.dt_adduserobject (?,?) }")  
```  
  
 次に、コマンド クラスを宣言します。  
  
```  
class CMySProc : public CCommand<CAccessor<CMySProcAccessor> >  
```  
  
 最後に、`OpenRowset` で次のようにストアド プロシージャを呼び出します。  
  
```  
CSession m_session;  
HRESULT OpenRowset()  
{  
   return CCommand<CAccessor<CMySProcAccessor> >::Open(m_session);  
}  
```  
  
 次のように、データベース属性 [db\_command](../../windows/db-command.md) を使用してストアド プロシージャを定義することもできます。  
  
```  
db_command("{ ? = CALL dbo.dt_adduserobject }")  
```  
  
## 参照  
 [ストアド プロシージャの使用](../../data/oledb/using-stored-procedures.md)