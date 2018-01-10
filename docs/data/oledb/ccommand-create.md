---
title: "Ccommand::create |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CCommand.Create
- CCommand::Create
dev_langs: C++
helpviewer_keywords: Create method [C++]
ms.assetid: e4bede7a-68bd-491a-97f4-89b03d45cd24
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f4bbd236c2ec7ae6857ede1ac64f738ca8600774
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ccommandcreate"></a>CCommand::Create
呼び出し[ccommand::createcommand](../../data/oledb/ccommand-createcommand.md)指定したセッションのコマンドを作成するを呼び出して[icommandtext::setcommandtext](https://msdn.microsoft.com/en-us/library/ms709825.aspx)コマンド テキストを指定します。  
  
## <a name="syntax"></a>構文  
  
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
  
#### <a name="parameters"></a>パラメーター  
 `session`  
 [in]コマンドを作成するセッションです。  
  
 `wszCommand`  
 [in]コマンド文字列の Unicode テキストへのポインター。  
  
 `szCommand`  
 [in]コマンド文字列の ANSI テキストへのポインター。  
  
 `guidCommand`  
 [in]コマンド テキストを解析中に、構文と使用するプロバイダーの一般的な規則を指定する GUID です。 言語仕様の説明は、次を参照してください。 [ICommandText::GetCommandText](https://msdn.microsoft.com/en-us/library/ms709825.aspx)で、 *OLE DB プログラマーズ リファレンス*です。  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
## <a name="remarks"></a>コメント  
 最初のフォーム**作成**Unicode コマンド文字列を使用します。 2 番目の形式の**作成**(既存の ANSI アプリケーションの旧バージョンと互換性のための指定) ANSI コマンド文字列を使用します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CCommand クラス](../../data/oledb/ccommand-class.md)