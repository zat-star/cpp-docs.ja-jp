---
title: "CFileException クラス | Microsoft Docs"
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
  - "CFileException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFile クラス, 例外"
  - "CFileException クラス"
  - "例外, ファイルの種類"
ms.assetid: f6491bb9-bfbc-42fd-a952-b33f9b62323f
caps.latest.revision: 20
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CFileException クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ファイルに関連した例外状態を表します。  
  
## 構文  
  
```  
class CFileException : public CException  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CFileException::CFileException](../Topic/CFileException::CFileException.md)|`CFileException` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CFileException::ErrnoToException](../Topic/CFileException::ErrnoToException.md)|ランタイム エラー番号に相当する原因コードを返します。|  
|[CFileException::GetErrorMessage](../Topic/CFileException::GetErrorMessage.md)|例外を説明したメッセージを取得します。|  
|[CFileException::OsErrorToException](../Topic/CFileException::OsErrorToException.md)|オペレーティング システムのエラー コードに相当する原因コードを返します。|  
|[CFileException::ThrowErrno](../Topic/CFileException::ThrowErrno.md)|ランタイム エラー番号に応じたファイル例外をスローします。|  
|[CFileException::ThrowOsError](../Topic/CFileException::ThrowOsError.md)|オペレーティング システムのエラー番号に応じたファイル例外をスローします。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CFileException::m\_cause](../Topic/CFileException::m_cause.md)|例外原因を示す移植性のあるコードを保持します。|  
|[CFileException::m\_lOsError](../Topic/CFileException::m_lOsError.md)|関連するオペレーティング システムのエラー番号を保持します。|  
|[CFileException::m\_strFileName](../Topic/CFileException::m_strFileName.md)|例外に関連したファイル名が入ります。|  
  
## 解説  
 `CFileException` のクラスは、ポータブル原因コードと操作システム固有のエラー番号を保持するパブリック データ メンバーが含まれています。  クラスは、例外のスロー ファイルとオペレーティング システムのエラーと C ランタイム エラーの両方の原因コードに返す静的メンバー関数を提供します。  
  
 `CFileException` のオブジェクトは `CFile` のメンバー関数と派生クラスのメンバー関数で構築され、がスローされます。  **CATCH** の式のスコープ内でこれらのオブジェクトにアクセスできます。  移植性を考慮して、例外の理由を取得する原因コードのみを使用します。  例外の詳細については、" " [例外処理 \(MFC\)](../../mfc/exception-handling-in-mfc.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CFileException`  
  
## 必要条件  
 **ヘッダー:** afx.h  
  
## 参照  
 [CException クラス](../../mfc/reference/cexception-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [例外処理](../../mfc/reference/exception-processing.md)