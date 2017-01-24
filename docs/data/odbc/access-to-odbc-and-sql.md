---
title: "ODBC や SQL へのアクセス | Microsoft Docs"
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
  - "API 呼び出し [C++], 呼び出し (直接 DAO または ODBC を)"
  - "ODBC [C++], API 関数"
  - "ODBC API 関数 [C++]"
  - "ODBC API 関数 [C++], 呼び出し (MFC で)"
  - "SQL [C++], 呼び出し (ODBC API 関数を)"
  - "Windows API [C++], 呼び出し (MFC で)"
ms.assetid: 5613d7dc-00b7-4646-99ae-1116c05c52b4
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ODBC や SQL へのアクセス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MFC は多くの Windows API 呼び出しをカプセル化していますが、これを使わずに Windows API 関数を直接呼び出すこともできます。  データベース クラスの場合も ODBC API を直接呼び出せます。  データベース クラスを使うと、複雑な手続きなしに ODBC を利用できますが、その一方で、プログラムの任意の場所から ODBC API 関数を直接呼び出すこともできます。  
  
 また、データベース クラスは、[SQL](../../data/odbc/sql.md) による作業の多くを簡略化する一方で、SQL を直接呼び出すこともできます。  レコードセットを開くときに、レコードセット オブジェクトに独自の SQL ステートメントを渡してカスタマイズしたり、既定のステートメントの一部を設定したりもできます。  SQL を直接呼び出すには、[CDatabase](../../mfc/reference/cdatabase-class.md) クラスのメンバー関数 [ExecuteSQL](../Topic/CDatabase::ExecuteSQL.md) も使えます。  
  
 詳細については、「[ODBC : ODBC API 関数の直接呼び出し](../../data/odbc/odbc-calling-odbc-api-functions-directly.md)」および「[SQL : SQL の直接呼び出し \(ODBC\)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)」を参照してください。  
  
## 参照  
 [ODBC と MFC](../../data/odbc/odbc-and-mfc.md)