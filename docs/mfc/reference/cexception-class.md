---
title: "CException クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CArchiveException クラス, 基本クラス"
  - "CDaoException クラス, 基本クラス"
  - "CDBException クラス, 基本クラス"
  - "CException クラス"
  - "CFileException クラス, 基本クラス"
  - "CInternetException クラス, 基本クラス"
  - "CMemoryException クラス, 基本クラス"
  - "CNotSupportedException クラス, 基本クラス"
  - "COleDispatchException クラス, 基本クラス"
  - "COleException クラス, 基本クラス"
  - "CResourceException クラス, 基本クラス"
  - "CUserException クラス"
  - "例外, クラス"
  - "マクロ, 例外処理"
ms.assetid: cfacf14d-bfe4-4666-a5c7-38b800512920
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CException クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MFC \(Microsoft Foundation Class\) ライブラリ内のすべての例外に関する基本クラスです。  
  
## 構文  
  
```  
class AFX_NOVTABLE CException : public CObject  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CException::CException](../Topic/CException::CException.md)|`CException` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CException::Delete](../Topic/CException::Delete.md)|`CException` オブジェクトを削除します。|  
|[CException::ReportError](../Topic/CException::ReportError.md)|ユーザーに対するエラー メッセージをメッセージ ボックスに表示します。|  
  
## 解説  
 `CException` は抽象基本クラスです。したがって、`CException` オブジェクトを作成することはできないので、派生クラスのオブジェクトを作成します。  独自の `CException` スタイル クラスを作成するには、以下の一覧の派生クラスの 1 つをモデルとして使ってください。  派生クラスでは必ず `IMPLEMENT_DYNAMIC` を使います。  
  
 このクラスの派生クラスには次のものがあります。  
  
|||  
|-|-|  
|[CSimpleException](../../mfc/reference/csimpleexception-class.md)|リソース クリティカルな MFC 例外の基本クラス|  
|[CInvalidArgException](../../mfc/reference/cinvalidargexception-class.md)|無効な引数の例外状態|  
|[CMemoryException](../../mfc/reference/cmemoryexception-class.md)|メモリ不足の例外|  
|[CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)|サポートされていない操作に関する例外|  
|[CArchiveException](../../mfc/reference/carchiveexception-class.md)|アーカイブ関連例外|  
|[CFileException](../../mfc/reference/cfileexception-class.md)|ファイル関連例外|  
|[CResourceException](../../mfc/reference/cresourceexception-class.md)|Windows のリソースが見つからない、または作成できない|  
|[COleException](../../mfc/reference/coleexception-class.md)|OLE の例外|  
|[CDBException](../../mfc/reference/cdbexception-class.md)|データベースの例外 \(ODBC \(Open Database Connectivity\) を基礎とした MFC データベース クラスでの例外状態\)|  
|[COleDispatchException](../Topic/COleDispatchException%20Class.md)|OLE ディスパッチ \(オートメーション\) の例外|  
|[CUserException](../../mfc/reference/cuserexception-class.md)|リソースが見つからなかったことを示す例外|  
|[CDaoException](../../mfc/reference/cdaoexception-class.md)|DAO \(Data Access Object\) の例外 \(DAO クラスでの例外状態\)|  
|[CInternetException](../../mfc/reference/cinternetexception-class.md)|インターネットの例外 \(Internet クラスでの例外状態\)|  
  
 これらの例外は [THROW](../Topic/THROW%20\(MFC\).md)、[THROW\_LAST](../Topic/THROW_LAST.md)、[TRY](../Topic/TRY.md)、[CATCH](../Topic/CATCH.md)、[AND\_CATCH](../Topic/AND_CATCH.md)、および [END\_CATCH](../Topic/END_CATCH.md) マクロで使います。  例外の詳細については、「[例外処理](../../mfc/reference/exception-processing.md)」または「[例外処理 \(MFC\)](../../mfc/exception-handling-in-mfc.md)」を参照してください。  
  
 特定の例外をキャッチするには、適切な派生クラスを使います。  すべての種類の例外をキャッチするには、`CException` クラスを使い、[CObject::IsKindOf](../Topic/CObject::IsKindOf.md) を使って `CException` 派生クラスを区別します。  動的な型チェックを利用するため、`CObject::IsKindOf` は [IMPLEMENT\_DYNAMIC](../Topic/IMPLEMENT_DYNAMIC.md) マクロを使って宣言されているクラスにのみ作用します。  作成するすべての `CException` 派生クラスでも `IMPLEMENT_DYNAMIC` マクロが使われます。  
  
 例外の詳細な情報をユーザーにリポートするには、[GetErrorMessage](../Topic/CFileException::GetErrorMessage.md) または [ReportError](../Topic/CException::ReportError.md) を呼び出します。この 2 つのメンバー関数は、どの `CException` 派生クラスでも動作します。  
  
 例外がマクロの 1 つでキャッチされたときは、`CException` オブジェクトは自動的に削除されます。このオブジェクトは、手動で削除しないでください。  **catch** キーワードを使って例外をキャッチしたときは、自動的には削除されません。  例外オブジェクトの削除が必要な場合については、「[例外処理 \(MFC\)](../../mfc/exception-handling-in-mfc.md)」を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CException`  
  
## 必要条件  
 **ヘッダー:** afx.h  
  
## 参照  
 [CObject クラス](../Topic/CObject%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [例外処理](../../mfc/reference/exception-processing.md)   
 [操作方法: My 独自のカスタム例外クラスを作成します。](http://go.microsoft.com/fwlink/?LinkId=128045)