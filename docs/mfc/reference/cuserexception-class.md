---
title: "CUserException クラス | Microsoft Docs"
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
  - "CUserException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CUserException クラス"
  - "エラー [C++], トラッピング"
  - "例外, スロー"
  - "操作 [C++]"
  - "操作 [C++], 停止"
  - "スロー (例外を), 中止 (ユーザーの操作の)"
ms.assetid: 2156ba6d-2cce-415a-9000-6f02c26fcd7d
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CUserException クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

エンド ユーザーの操作を中止するためにスローします。  
  
## 構文  
  
```  
class CUserException : public CSimpleException  
```  
  
## 解説  
 アプリケーション固有の例外に対してスロー\/キャッチ例外機構を使用する場合は、CUserException を使います。"  クラス名に使用されている "User" は、"処理の必要な例外をアプリケーションのユーザーが引き起こした" ということを表しています。  
  
 通常、`CUserException` クラスをスローする前に、グローバル関数 `AfxMessageBox` を呼び出して、操作が失敗したことをユーザーに通知します。  例外ハンドラーを記述するときは、ユーザーは既に操作の失敗を通知されているので、例外の処理方法が異なります。  フレームワークでは、ある条件でこの例外をスローします。  `CUserException` を自分でスローするときは、ユーザーに警告してからグローバル関数 `AfxThrowUserException` を呼び出します。  
  
 操作が失敗するとユーザーに警告し、`CUserException` をスローする関数の例は、次のとおりです。  呼び出し元の関数は、例外をキャッチし、専用の処理を行います。  
  
 [!code-cpp[NVC_MFCExceptions#24](../../mfc/codesnippet/CPP/cuserexception-class_1.cpp)]  
  
 `CUserException` の使い方の詳細については、「[例外処理 \(MFC\)](../../mfc/exception-handling-in-mfc.md)」を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CUserException`  
  
## 必要条件  
 **ヘッダー:** afxwin.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [CException クラス](../../mfc/reference/cexception-class.md)   
 [AfxMessageBox](../Topic/AfxMessageBox.md)   
 [AfxThrowUserException](../Topic/AfxThrowUserException.md)   
 [操作方法: My 独自のカスタム例外クラスを作成します。](http://go.microsoft.com/fwlink/?LinkId=128045)