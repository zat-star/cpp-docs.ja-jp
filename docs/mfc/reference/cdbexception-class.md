---
title: "CDBException クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDBException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDBException クラス"
  - "データベースの例外 [C++]"
  - "エラー [C++], データベース"
  - "例外 [C++], データベース"
  - "ODBC クラス [C++], 例外"
ms.assetid: eb9e1119-89f5-49a7-b9d4-b91cee1ccc82
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CDBException クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

データベース クラスから発生する例外状態を表現します。  
  
## 構文  
  
```  
  
class CDBException : public CException  
  
```  
  
## メンバー  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CDBException::m\_nRetCode](../Topic/CDBException::m_nRetCode.md)|型 **RETCODE**の ODBC \(Open Database Connectivity\) のリターン コードが含まれます。|  
|[CDBException::m\_strError](../Topic/CDBException::m_strError.md)|英数字の用語でエラーを説明する文字列が含まれます。|  
|[CDBException::m\_strStateNativeOrigin](../Topic/CDBException::m_strStateNativeOrigin.md)|ODBC によって返されるエラー コードの観点でエラーを説明する文字列が含まれます。|  
  
## 解説  
 クラスは、例外の原因を判断したり、例外を説明するテキスト メッセージを表示するために使用できる 2 人のパブリック データ メンバーが含まれています。  `CDBException` のオブジェクトは、データベース クラスのメンバー関数によって構築され、がスローされます。  
  
> [!NOTE]
>  このクラスは、MFC の ODBC \(Open Database Connectivity\) のクラスの 1 つです。  代わりに、Data Access Objects \(DAO\) の新しいクラスを使用する場合は、[CDaoException](../../mfc/reference/cdaoexception-class.md) を使用します。  すべての DAO クラス名のプレフィックスとして「」CDao があります。  詳細については、" " [:概要 データベース プログラミング](../../data/data-access-programming-mfc-atl.md)を参照してください。  
  
 例外は、データ ソースまたはネットワーク I\/O エラーなどのプログラムのコントロールの外側の条件を含む、異常実行の場合だけです。  、プログラムの実行の通常のコースでに発生する可能性のあるエラーは、通常、例外とは見なされません。  
  
 **CATCH** の式のスコープ内でこれらのオブジェクトにアクセスできます。  また `AfxThrowDBException` のグローバル関数の独自のコードからの `CDBException` のオブジェクトをスローできます。  
  
 一般に、または `CDBException` のオブジェクトの詳細については、例外処理、" " [例外処理 \(MFC\)](../../mfc/exception-handling-in-mfc.md) と [例外: データベースの例外](../../mfc/exceptions-database-exceptions.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CDBException`  
  
## 必要条件  
 **Header:** afxdb.h  
  
## 参照  
 [CException クラス](../../mfc/reference/cexception-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDatabase クラス](../../mfc/reference/cdatabase-class.md)   
 [CRecordset クラス](../Topic/CRecordset%20Class.md)   
 [CFieldExchange クラス](../../mfc/reference/cfieldexchange-class.md)   
 [AfxThrowDBException](../Topic/AfxThrowDBException.md)   
 [CRecordset::Update](../Topic/CRecordset::Update.md)   
 [CRecordset::Delete](../Topic/CRecordset::Delete.md)   
 [CException クラス](../../mfc/reference/cexception-class.md)