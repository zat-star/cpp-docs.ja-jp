---
title: "CDaoException クラス | Microsoft Docs"
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
  - "CDaoException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoException クラス"
  - "コレクション, DAO エラー"
  - "DAO (データ アクセス オブジェクト), 例外"
  - "エラー [C++], DAO"
  - "Errors コレクション, DAO"
  - "例外, MFC DAO クラスで"
ms.assetid: b2b01fa9-7ce2-42a1-842e-40f13dc50da4
caps.latest.revision: 24
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDaoException クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

データ アクセス オブジェクト \(DAO: Data Accsess Object\) を基にした MFC データベース クラスから発生する例外条件を表します。  
  
## 構文  
  
```  
class CDaoException : public CException  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CDaoException::CDaoException](../Topic/CDaoException::CDaoException.md)|`CDaoException` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CDaoException::GetErrorCount](../Topic/CDaoException::GetErrorCount.md)|データベース エンジンのエラーのコレクションのエラーの数を返します。|  
|[CDaoException::GetErrorInfo](../Topic/CDaoException::GetErrorInfo.md)|エラーのコレクションの特定のエラー オブジェクトに関するエラー情報を返します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CDaoException::m\_nAfxDaoError](../Topic/CDaoException::m_nAfxDaoError.md)|MFC DAO クラス内のエラーの拡張エラー コードが含まれています。|  
|[CDaoException::m\_pErrorInfo](../Topic/CDaoException::m_pErrorInfo.md)|1 個の DAO のエラー オブジェクトに関する情報を含む [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md) オブジェクトへのポインター。|  
|[CDaoException::m\_scode](../Topic/CDaoException::m_scode.md)|エラーに関連付けられた [SCODE](../Topic/CDaoException::m_scode.md) の値。|  
  
## 解説  
 クラスは、例外の原因を決定するために使用できるパブリック データ メンバーが含まれています。  `CDaoException` のオブジェクトは DAO データベース クラスのメンバー関数によって構築され、がスローされます。  
  
> [!NOTE]
>  DAO データベース クラスは、ODBC \(Open Database Connectivity\) に基づく MFC データベース クラスとは異なります。  すべての DAO データベース クラス名に「CDao」が付きます。  まだ DAO クラスと ODBC データ ソースにアクセスできます。  一般に、に基づく MFC DAO クラスは、ODBC \(DAO クラスより;できます。DAO ベースのクラスには独自のデータベース エンジンで ODBC ドライバーを通じて、含むデータにアクセスできます。  DAO ベースのクラスは、クラスによって DAO を直接呼び出さないでテーブルの追加など、データ定義言語の \(DDL\)、操作をサポートします。  ODBC クラスによってスローされる例外の詳細については [CDBException](../../mfc/reference/cdbexception-class.md)を参照してください。  
  
 [catch](../Topic/CATCH.md) の式のスコープ内で例外オブジェクトにアクセスできます。  また [AfxThrowDaoException](../Topic/AfxThrowDaoException.md) のグローバル関数の独自のコードからの `CDaoException` のオブジェクトをスローできます。  
  
 MFC では、すべての DAO のエラーは、型 `CDaoException`の例外として表現されます。  この種類の例外をキャッチすると、データベース エンジンのエラーのコレクションに格納されている DAO のエラー オブジェクトから情報を取得するために `CDaoException` のメンバー関数を使用できます。  各エラーが発生すると同時に、一つ以上のエラーはエラー オブジェクトのコレクションに設定されます。  \(通常はコレクションは、1 種類のエラー オブジェクトのみが含まれています; ODBC データ ソースを使用する複数のエラー オブジェクトを取得するために、よく発生します。\) 別の DAO の操作がエラーを生成すると、エラーのコレクションが消去され、新しいエラーはエラー オブジェクトのコレクションに設定されます。  エラーが発生しない DAO の操作は、エラーのコレクションには影響しません。  
  
 DAO のエラー コードをファイル DAOERR.H.を参照してください。  関連情報は、DAO ヘルプ トピック「Trappable データ アクセス エラー」を参照してください。  
  
 一般に、または `CDaoException` のオブジェクトの詳細については、例外処理、" " [例外処理 \(MFC\)](../../mfc/exception-handling-in-mfc.md) と [例外: データベースの例外](../../mfc/exceptions-database-exceptions.md)を参照してください。  2 番目の文書は、DAO 例外処理を示すコード例が含まれています。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CDaoException`  
  
## 必要条件  
 **Header:** afxdao.h  
  
## 参照  
 [CException クラス](../../mfc/reference/cexception-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CException クラス](../../mfc/reference/cexception-class.md)