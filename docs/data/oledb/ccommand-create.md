---
title: "CCommand::Create | Microsoft Docs"
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
  - "CCommand.Create"
  - "CCommand::Create"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Create メソッド [C++]"
ms.assetid: e4bede7a-68bd-491a-97f4-89b03d45cd24
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CCommand::Create
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[CCommand::CreateCommand](../Topic/CCommand::CreateCommand.md) を指定したセッションのコマンドを作成するには、And はコマンド テキストを指定するに [ICommandText::SetCommandText](https://msdn.microsoft.com/en-us/library/ms709825.aspx) を呼び出します。  
  
## 構文  
  
```  
  
      HRESULT CCommandBase::Create(  
   const CSession& session,   
   LPCWSTR wszCommand,   
   REFGUID guidCommand = DBGUID_DEFAULT  
) throw ( );  
HRESULT CCommandBase::Create(  
   const CSession& session,   
   LPCSTR szCommand,   
   REFGUID guidCommand = DBGUID_DEFAULT  
) throw ( );  
```  
  
#### パラメーター  
 `session`  
 \[\]コマンドを作成しているセッション。  
  
 `wszCommand`  
 \[\]コマンド文字列を Unicode テキストへのポインター。  
  
 `szCommand`  
 \[\]コマンド文字列を ANSI テキストへのポインター。  
  
 `guidCommand`  
 \[\]プロバイダーのコマンド テキストの解析に使用する構文、一般的な規則を指定する入力 GUID。  言語の詳細については、*OLE DB Programmer's Reference*の [ICommandText::GetCommandText](https://msdn.microsoft.com/en-us/library/ms709825.aspx) を参照してください。  
  
## 戻り値  
 標準の `HRESULT` を返します。  
  
## 解説  
 **作成** の最初のフォームは Unicode のコマンド文字列が使用されます。  **作成** の 2 番目のフォームは ANSI コマンド文字列を受け取ります \(ある ANSI アプリケーションを下位互換性に指定\)。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CCommand クラス](../../data/oledb/ccommand-class.md)