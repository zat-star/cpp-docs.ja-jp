---
title: "CTokenPrivileges クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CTokenPrivileges"
  - "CTokenPrivileges"
  - "ATL.CTokenPrivileges"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTokenPrivileges クラス"
ms.assetid: 89590105-f001-4014-870d-142926091231
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CTokenPrivileges クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、**TOKEN\_PRIVILEGES** 構造体のラッパー クラスです。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
class CTokenPrivileges  
  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CTokenPrivileges::CTokenPrivileges](../Topic/CTokenPrivileges::CTokenPrivileges.md)|コンストラクターです。|  
|[CTokenPrivileges::~CTokenPrivileges](../Topic/CTokenPrivileges::~CTokenPrivileges.md)|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CTokenPrivileges::Add](../Topic/CTokenPrivileges::Add.md)|`CTokenPrivileges` のオブジェクトに一つ以上の特権を追加します。|  
|[CTokenPrivileges::Delete](../Topic/CTokenPrivileges::Delete.md)|`CTokenPrivileges` のオブジェクトの特権を削除します。|  
|[CTokenPrivileges::DeleteAll](../Topic/CTokenPrivileges::DeleteAll.md)|`CTokenPrivileges` のオブジェクトからすべての特権を削除します。|  
|[CTokenPrivileges::GetCount](../Topic/CTokenPrivileges::GetCount.md)|`CTokenPrivileges` のオブジェクトの特権のエントリの数を返します。|  
|[CTokenPrivileges::GetDisplayNames](../Topic/CTokenPrivileges::GetDisplayNames.md)|`CTokenPrivileges` に含まれる特権の取得の表示名を追加します。|  
|[CTokenPrivileges::GetLength](../Topic/CTokenPrivileges::GetLength.md)|**TOKEN\_PRIVILEGES** の構造を `CTokenPrivileges` のオブジェクトによって表される保持するために必要なバイト バッファー サイズを返します。|  
|[CTokenPrivileges::GetLuidsAndAttributes](../Topic/CTokenPrivileges::GetLuidsAndAttributes.md)|`CTokenPrivileges` のオブジェクトから一意の識別子 \(LUIDs\) と属性フラグをローカルで取得します。|  
|[CTokenPrivileges::GetNamesAndAttributes](../Topic/CTokenPrivileges::GetNamesAndAttributes.md)|`CTokenPrivileges` のオブジェクトから特権の名前と属性フラグを取得します。|  
|[CTokenPrivileges::GetPTOKEN\_PRIVILEGES](../Topic/CTokenPrivileges::GetPTOKEN_PRIVILEGES.md)|**TOKEN\_PRIVILEGES** の構造体へのポインターを返します。|  
|[CTokenPrivileges::LookupPrivilege](../Topic/CTokenPrivileges::LookupPrivilege.md)|特定の特権の名前が付けられた属性を取得します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CTokenPrivileges::operator const TOKEN\_PRIVILEGES \*](../Topic/CTokenPrivileges::operator%20const%20TOKEN_PRIVILEGES%20*.md)|**TOKEN\_PRIVILEGES** の構造体へのポインターにキャスト。|  
|[CTokenPrivileges::operator \=](../Topic/CTokenPrivileges::operator%20=.md)|代入演算子。|  
  
## 解説  
 [アクセス トークン](http://msdn.microsoft.com/library/windows/desktop/aa374909) は、プロセスまたはスレッドのセキュリティ コンテキストを記述する場合は、Windows NT または Windows 2000 システムに記録される各ユーザー オブジェクトに割り当てられます。  
  
 アクセス トークンが各ユーザーに許可されているさまざまなセキュリティ権限を記述するために使用されます。  特権は一意の識別子ローカルに呼び出される 64 ビット数 \([LUID](http://msdn.microsoft.com/library/windows/desktop/aa379261)\) および記述子文字列で構成されます。  
  
 `CTokenPrivileges` のクラスは [TOKEN\_PRIVILEGES](http://msdn.microsoft.com/library/windows/desktop/aa379630) の構造体のラッパー クラスが含まれます 0、またはそれ以上の特権が。  特権は指定されたクラスのメソッドを使用して追加、削除、または照会できます。  
  
 Windows のアクセスの制御モデルの概要については、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の [アクセス制御](http://msdn.microsoft.com/library/windows/desktop/aa374860) を参照してください。  
  
## 必要条件  
 **ヘッダー :** atlsecurity.h  
  
## 参照  
 [セキュリティのサンプル](../../top/visual-cpp-samples.md)   
 [TOKEN\_PRIVILEGES](http://msdn.microsoft.com/library/windows/desktop/aa379630)   
 [LUID](http://msdn.microsoft.com/library/windows/desktop/aa379261)   
 [LUID\_AND\_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379263)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [セキュリティに関するグローバル関数](../../atl/reference/security-global-functions.md)