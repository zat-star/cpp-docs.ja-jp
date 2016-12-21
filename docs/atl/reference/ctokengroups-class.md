---
title: "CTokenGroups クラス | Microsoft Docs"
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
  - "ATL::CTokenGroups"
  - "ATL.CTokenGroups"
  - "CTokenGroups"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTokenGroups クラス"
ms.assetid: 2ab08076-4b08-4487-bc70-ec6dee304190
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CTokenGroups クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、**TOKEN\_GROUPS** 構造体のラッパー クラスです。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
class CTokenGroups  
  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CTokenGroups::CTokenGroups](../Topic/CTokenGroups::CTokenGroups.md)|コンストラクターです。|  
|[CTokenGroups::~CTokenGroups](../Topic/CTokenGroups::~CTokenGroups.md)|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CTokenGroups::Add](../Topic/CTokenGroups::Add.md)|`CTokenGroups` のオブジェクトに **TOKEN\_GROUPS** の `CSid` かの構造を追加します。|  
|[CTokenGroups::Delete](../Topic/CTokenGroups::Delete.md)|`CTokenGroups` のオブジェクトの `CSid` および関連の属性を削除します。|  
|[CTokenGroups::DeleteAll](../Topic/CTokenGroups::DeleteAll.md)|`CTokenGroups` のオブジェクトの `CSid` のすべてのオブジェクトと関連付けられた属性を削除します。|  
|[CTokenGroups::GetCount](../Topic/CTokenGroups::GetCount.md)|**CTokenGroups** のオブジェクトに含まれる `CSid` のオブジェクトと関連付けられた属性の数を返します。|  
|[CTokenGroups::GetLength](../Topic/CTokenGroups::GetLength.md)|`CTokenGroups` のオブジェクトのサイズを返します。|  
|[CTokenGroups::GetPTOKEN\_GROUPS](../Topic/CTokenGroups::GetPTOKEN_GROUPS.md)|**TOKEN\_GROUPS** の構造体へのポインターを取得します。|  
|[CTokenGroups::GetSidsAndAttributes](../Topic/CTokenGroups::GetSidsAndAttributes.md)|`CTokenGroups` のオブジェクトに属する `CSid` のオブジェクトと属性を取得します。|  
|[CTokenGroups::LookupSid](../Topic/CTokenGroups::LookupSid.md)|`CSid` のオブジェクトに関連付けられている属性を取得します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CTokenGroups::operator const TOKEN\_GROUPS \*](../Topic/CTokenGroups::operator%20const%20TOKEN_GROUPS%20*.md)|**TOKEN\_GROUPS** の構造体へのポインターへの `CTokenGroups` のオブジェクトをキャストします。|  
|[CTokenGroups::operator \=](../Topic/CTokenGroups::operator%20=.md)|代入演算子。|  
  
## 解説  
 [アクセス トークン](http://msdn.microsoft.com/library/windows/desktop/aa374909) は、プロセスまたはスレッドのセキュリティ コンテキストを記述する場合は、Windows NT または Windows 2000 システムに記録される各ユーザー オブジェクトに割り当てられます。  
  
 **CTokenGroups** のクラスは、アクセス トークンのグループ セキュリティ識別子 \(SIDs\) に関する情報を含む [TOKEN\_GROUPS](http://msdn.microsoft.com/library/windows/desktop/aa379624) の構造体のラッパー クラスです。  
  
 Windows のアクセスの制御モデルの概要については、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の [アクセス制御](http://msdn.microsoft.com/library/windows/desktop/aa374860) を参照してください。  
  
## 必要条件  
 **ヘッダー :** atlsecurity.h  
  
## 参照  
 [セキュリティのサンプル](../../top/visual-cpp-samples.md)   
 [CSid クラス](../../atl/reference/csid-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [セキュリティに関するグローバル関数](../../atl/reference/security-global-functions.md)