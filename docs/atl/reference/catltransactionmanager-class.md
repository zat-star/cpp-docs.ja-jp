---
title: "CAtlTransactionManager クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CAtlTransactionManager"
  - "atltransactionmanager/ATL::CAtlTransactionManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlTransactionManager クラス"
ms.assetid: b01732dc-1d16-4b42-bfac-b137fca2b740
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 28
---
# CAtlTransactionManager クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

CAtlTransactionManager クラスは、カーネル トランザクション マネージャー \(KTM\) 関数のラッパーを提供します。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
class CAtlTransactionManager;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CAtlTransactionManager::~CAtlTransactionManager](../Topic/CAtlTransactionManager::~CAtlTransactionManager.md)|CAtlTransactionManager デストラクター。|  
|[CAtlTransactionManager::CAtlTransactionManager](../Topic/CAtlTransactionManager::CAtlTransactionManager.md)|CAtlTransactionManager コンストラクター。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CAtlTransactionManager::Close](../Topic/CAtlTransactionManager::Close.md)|トランザクション ハンドルを終了します。|  
|[CAtlTransactionManager::Commit](../Topic/CAtlTransactionManager::Commit.md)|トランザクションをコミットすることを要求します。|  
|[CAtlTransactionManager::Create](../Topic/CAtlTransactionManager::Create.md)|トランザクション ハンドルを作成します。|  
|[CAtlTransactionManager::CreateFile](../Topic/CAtlTransactionManager::CreateFile.md)|トランザクション操作として、ファイル、ファイル ストリーム、またはディレクトリを作成するか、開きます。|  
|[CAtlTransactionManager::DeleteFile](../Topic/CAtlTransactionManager::DeleteFile.md)|トランザクション操作として、既存のファイルを削除します。|  
|[CAtlTransactionManager::FindFirstFile](../Topic/CAtlTransactionManager::FindFirstFile.md)|トランザクション操作として、ディレクトリ内でファイルまたはサブディレクトリを検索します。|  
|[CAtlTransactionManager::GetFileAttributes](../Topic/CAtlTransactionManager::GetFileAttributes.md)|トランザクション操作として、指定したファイルまたはディレクトリのファイル システム属性を取得します。|  
|[CAtlTransactionManager::GetFileAttributesEx](../Topic/CAtlTransactionManager::GetFileAttributesEx.md)|トランザクション操作として、指定したファイルまたはディレクトリのファイル システム属性を取得します。|  
|[CAtlTransactionManager::GetHandle](../Topic/CAtlTransactionManager::GetHandle.md)|トランザクション ハンドルを返します。|  
|[CAtlTransactionManager::IsFallback](../Topic/CAtlTransactionManager::IsFallback.md)|フォールバック呼び出しが有効かどうかを決定します。|  
|[CAtlTransactionManager::MoveFile](../Topic/CAtlTransactionManager::MoveFile.md)|トランザクション操作として、既存のファイルまたはディレクトリおよび子を移動します。|  
|[CAtlTransactionManager::RegCreateKeyEx](../Topic/CAtlTransactionManager::RegCreateKeyEx.md)|指定したレジストリ キーを作成してトランザクションに関連付けます。  キーが既に存在する場合は、そのキーが開かれます。|  
|[CAtlTransactionManager::RegDeleteKey](../Topic/CAtlTransactionManager::RegDeleteKey.md)|トランザクション操作として、指定したプラットフォーム固有のレジストリのビューからサブキーおよびその値を削除します。|  
|[CAtlTransactionManager::RegOpenKeyEx](../Topic/CAtlTransactionManager::RegOpenKeyEx.md)|指定したレジストリ キーを開いてトランザクションに関連付けます。|  
|[CAtlTransactionManager::Rollback](../Topic/CAtlTransactionManager::Rollback.md)|トランザクションをロールバックすることを要求します。|  
|[CAtlTransactionManager::SetFileAttributes](../Topic/CAtlTransactionManager::SetFileAttributes.md)|トランザクション操作として、ファイルまたはディレクトリの属性を設定します。|  
  
### プロテクト データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CAtlTransactionManager::m\_bFallback](../Topic/CAtlTransactionManager::m_bFallback.md)|フォールバックがサポートされる場合は `TRUE`。それ以外の場合は `FALSE`。|  
|[CAtlTransactionManager::m\_hTransaction](../Topic/CAtlTransactionManager::m_hTransaction.md)|トランザクション ハンドル。|  
  
## 解説  
  
## 継承階層  
 [ATL::CAtlTransactionManager](../../atl/reference/catltransactionmanager-class.md)  
  
## 必要条件  
 **ヘッダー:** atltransactionmanager.h  
  
## 参照  
 [ATL COM デスクトップ コンポーネント](../../atl/atl-com-desktop-components.md)