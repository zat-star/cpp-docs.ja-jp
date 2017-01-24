---
title: "CCommand::Open | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CCommand.Open"
  - "ATL::CCommand::Open"
  - "CCommand.Open"
  - "CCommand::Open"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Open メソッド"
ms.assetid: 4c9b8f31-faf3-452d-9a29-3d3e5f54d6f8
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CCommand::Open
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コマンドを実行し、必要に応じてバインドします。  
  
## 構文  
  
```  
  
      HRESULT Open(  
   const CSession& session,  
   LPCWSTR wszCommand,  
   DBPROPSET *pPropSet = NULL,  
   DBROWCOUNT* pRowsAffected = NULL,  
   REFGUID guidCommand = DBGUID_DEFAULT,  
   bool bBind = true,  
   ULONG ulPropSets = 0  
) throw( );  
HRESULT Open(  
   const CSession& session,  
   LPCSTR szCommand,  
   DBPROPSET *pPropSet = NULL,  
   DBROWCOUNT* pRowsAffected = NULL,  
   REFGUID guidCommand = DBGUID_DEFAULT,  
   bool bBind = true,  
   ULONG ulPropSets = 0  
) throw( );  
HRESULT Open(  
   const CSession& session,  
   INT szCommand = NULL,  
   DBPROPSET *pPropSet = NULL,  
   DBROWCOUNT* pRowsAffected = NULL,  
   REFGUID guidCommand = DBGUID_DEFAULT,  
   bool bBind = true,  
   ULONG ulPropSets = 0  
) throw( );  
HRESULT Open(  
   DBPROPSET *pPropSet = NULL,  
   DBROWCOUNT* pRowsAffected = NULL,  
   bool bBind = true,  
   ULONG ulPropSets = 0  
) throw( );  
```  
  
#### パラメーター  
 `session`  
 \[\]コマンドを実行するセッション。  
  
 `wszCommand`  
 \[\]実行するコマンド、Unicode 文字列として渡されます。  コマンドが [DEFINE\_COMMAND](../../data/oledb/define-command.md) マクロに渡された値から取得されれば `CAccessor`を使用すると **NULL** になることがあります。  詳細については、*OLE DB Programmer's Reference* の [ICommand::Execute](https://msdn.microsoft.com/en-us/library/ms718095.aspx) を参照してください。  
  
 `szCommand`  
 \[\] `wszCommand` が、このパラメーターと同様に ANSI のコマンド文字列が使用されます。  このメソッドの 4 番目のフォームは null 値を受け取ることができます。  詳細については、このトピックで後述する「解説」"を参照してください。  
  
 *pPropSet*  
 \[\]設定するプロパティと値を含む [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) 構造体の配列へのポインター。  [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の *OLE DB Programmer's Reference* の [プロパティ セットとプロパティ グループ](https://msdn.microsoft.com/en-us/library/ms713696.aspx) を参照してください。  
  
 `pRowsAffected`  
 \[\]そのコマンドの影響を受ける行の数を返すメモリへのポインター。  *\*pRowsAffected***NULL**は、行数が返されます。  それ以外の場合は **開く** は、次の基準に従って`pRowsAffected` を\*に設定する:  
  
|If|Then|  
|--------|----------|  
|`pParams` の **cParamSets** 要素は 1 より大きい|\*`pRowsAffected` は実行で指定されたパラメーター設定の影響を受けるすべての合計数を表します。|  
|影響を受ける行の数は使用できません|\*`pRowsAffected` は–1 に設定されます。|  
|コマンドは、行を更新しませんが、削除したり、挿入されません|\*`pRowsAffected` は未定義です。|  
  
 `guidCommand`  
 \[\]プロバイダーのコマンド テキストの解析に使用する構文、一般的な規則を指定する入力 GUID。  詳細については、*OLE DB Programmer's Reference* の [ICommandText::GetCommandText](https://msdn.microsoft.com/en-us/library/ms709825.aspx) と [ICommandText::SetCommandText](https://msdn.microsoft.com/en-us/library/ms709757.aspx) を参照してください。  
  
 `bBind`  
 \[\]の実行後にコマンドを自動的にバインドするかどうかを指定します。  自動的にバインドされるコマンドの原因は既定 **true**です。  手動でバインドできるように **false** に設定 `bBind` はコマンドの自動バインディングを防ぎます。\(手動バインドは、OLAP のユーザーに注目です\)。  
  
 `ulPropSets`  
 \[\] *pPropSet の* 引数に渡される [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) 構造体の数。  
  
## 戻り値  
 標準の `HRESULT` を返します。  
  
## 解説  
 **開く** の最初の 3 種類のフォームがセッションを受け取り、コマンドを作成し、必要に応じてパラメーターをバインドするコマンドを実行します。  
  
 **開く** の最初のフォームは Unicode のコマンド文字列を使用して、既定値はありません。  
  
 **開く** の 2 番目のフォームは ANSI コマンド文字列と既定値を返します \(ある ANSI アプリケーションを下位互換性に指定\)。  
  
 **開く** の 3 番目のフォームはコマンド文字列が null の既定値の型 `int` の場合は null、になるようにします。  これは `Open(session, NULL);` または `Open(session);` を呼び出す場合は、NULL が `int`型であるため、提供されます。  このバージョンが必要で、`int` パラメーターが NULL であることを表しています。  
  
 既にコマンドを作成して、単一の [準備します。](../../data/oledb/ccommand-prepare.md) および複数の実行を実行する **開く** の 4 番目のフォームを使用します。  
  
> [!NOTE]
>  **開く** は **実行**を呼び出して、`GetNextResult`を呼び出します。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CCommand クラス](../../data/oledb/ccommand-class.md)