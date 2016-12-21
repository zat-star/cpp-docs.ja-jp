---
title: "CSimpleException クラス | Microsoft Docs"
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
  - "CSimpleException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSimpleException クラス"
ms.assetid: be0eb8ef-e5b9-47d6-b0fb-efaff2d1e666
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSimpleException クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、リソース クリティカルな MFC 例外の基本クラスです。  
  
## 構文  
  
```  
  
class AFX_NOVTABLE CSimpleException : public CException  
  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CSimpleException::CSimpleException](../Topic/CSimpleException::CSimpleException.md)|コンストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CSimpleException::GetErrorMessage](../Topic/CSimpleException::GetErrorMessage.md)|発生したエラーに関するテキストが表示されます。|  
  
## 解説  
 `CSimpleException` は、リソース クリティカルな MFC 例外の基本クラスでエラー メッセージの所有権と初期化を実行します。  次のクラスは基本クラスとして `CSimpleException` を使用します:  
  
|||  
|-|-|  
|[CMemoryException のクラス](../../mfc/reference/cmemoryexception-class.md)|メモリ不足の例外|  
|[CNotSupportedException のクラス](../../mfc/reference/cnotsupportedexception-class.md)|サポートされていない操作の要求|  
|[CResourceException のクラス](../../mfc/reference/cresourceexception-class.md)|Windows のリソースが見つからない、または作成できない|  
|[CUserException クラス](../../mfc/reference/cuserexception-class.md)|リソースを示す例外が見つかりませんでした|  
|[CInvalidArgException のクラス](../../mfc/reference/cinvalidargexception-class.md)|無効な引数を示す例外|  
  
 `CSimpleException` が抽象基本クラスであるため、`CSimpleException` のオブジェクトを直接宣言できません。  代わりに、前の表のような派生オブジェクトを宣言する必要があります。  独自の派生クラスを宣言した場合、モデルに直前のクラスを使用します。  
  
 詳細については、" "および [CException クラス](../../mfc/reference/cexception-class.md)[例外処理 \(MFC\)](../../mfc/exception-handling-in-mfc.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CSimpleException`  
  
## 必要条件  
 **ヘッダー :** afx.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [CException クラス](../../mfc/reference/cexception-class.md)   
 [例外処理](../../mfc/exception-handling-in-mfc.md)