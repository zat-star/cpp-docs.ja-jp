---
title: "CAcl クラス | Microsoft Docs"
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
  - "CAcl"
  - "ATL::CAcl"
  - "ATLSECURITY/CAcl"
  - "ATL.CAcl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAcl クラス"
ms.assetid: 20bcb9af-dc1c-4737-b923-3864776680d6
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAcl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは `ACL` アクセス制御リスト \(ACL\) 構造体のラッパー クラスです。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
class CAcl  
  
```  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|[CAcl::CAccessMaskArray](../Topic/CAcl::CAccessMaskArray.md)|`ACCESS_MASK`、.の配列。|  
|[CAcl::CAceFlagArray](../Topic/CAcl::CAceFlagArray.md)|`BYTE`、.の配列。|  
|[CAcl::CAceTypeArray](../Topic/CAcl::CAceTypeArray.md)|`BYTE`、.の配列。|  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CAcl::CAcl](../Topic/CAcl::CAcl.md)|コンストラクターです。|  
|[CAcl::~CAcl](../Topic/CAcl::~CAcl.md)|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CAcl::GetAceCount](../Topic/CAcl::GetAceCount.md)|アクセス制御エントリの \(ACE\) のオブジェクトの数を返します。|  
|[CAcl::GetAclEntries](../Topic/CAcl::GetAclEntries.md)|`CAcl` のオブジェクトから、アクセス制御リストの \(ACL\) のエントリを取得します。|  
|[CAcl::GetAclEntry](../Topic/CAcl::GetAclEntry.md)|`CAcl` のオブジェクトのエントリに関する情報をすべて取得します。|  
|[CAcl::GetLength](../Topic/CAcl::GetLength.md)|ACL の長さを返します。|  
|[CAcl::GetPACL](../Topic/CAcl::GetPACL.md)|PACL \(ACL\) へのポインターを返します。|  
|[CAcl::IsEmpty](../Topic/CAcl::IsEmpty.md)|エントリに `CAcl` のオブジェクトをテストします。|  
|[CAcl::IsNull](../Topic/CAcl::IsNull.md)|`CAcl` オブジェクトの状態を返します。|  
|[CAcl::RemoveAce](../Topic/CAcl::RemoveAce.md)|`CAcl` のオブジェクトから特定のアクセス制御エントリ \(ACE\) を削除します。|  
|[CAcl::RemoveAces](../Topic/CAcl::RemoveAces.md)|特定の `CSid`に適用する `CAcl` からすべてのアクセス制御エントリ \(ACE\) を削除します。|  
|[CAcl::SetEmpty](../Topic/CAcl::SetEmpty.md)|空のように `CAcl` オブジェクトをマークします。|  
|[CAcl::SetNull](../Topic/CAcl::SetNull.md)|`NULL`として `CAcl` のオブジェクトをマークします。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CAcl::operator const ACL \*](../Topic/CAcl::operator%20const%20ACL%20*.md)|`ACL` の構造体への `CAcl` のオブジェクトをキャストします。|  
|[CAcl::operator \=](../Topic/CAcl::operator%20=.md)|代入演算子。|  
  
## 解説  
 **ACL** の構造は ACL アクセス制御リスト \(ACL\) ヘッダーです。  ACL はです。は詳細に [ACE](http://msdn.microsoft.com/library/windows/desktop/aa374868) \(アクセス制御エントリ\) の順次リストが。  ACL の個々の ACE を 0 から *n は* ACL ACE の番号です。*n\-1*に行番号が表示されます。  ACL を編集すると、アプリケーションはインデックスで ACL 内のアクセス制御エントリ \(ACE\) を示します。  
  
 2 種類の ACL の型があります:  
  
-   オプション  
  
-   システム  
  
 任意の ACL は、オブジェクトの所有者によって制御されます。または、オブジェクトへの **WRITE\_DAC** のアクセスを許可する。  これは、アクセスの特定のユーザーを指定し、グループ オブジェクトを記述できます。  たとえば、ファイルの所有者は制御するには、ファイルへのアクセスを持ち、ユーザーとグループができない任意の ACL を使用できます。  
  
 オブジェクトは、システム管理者が制御するシステムの ACL の形式でそれに関連付けられたシステム レベルのセキュリティ情報を持つことができます。  システムの ACL は、システム管理者がオブジェクトにアクセスするときはを監査できるようにすることができます。  
  
 詳細については、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の [ACL](http://msdn.microsoft.com/library/windows/desktop/aa374872) の説明を参照してください。  
  
 Windows のアクセスの制御モデルの概要については、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の [アクセス制御](http://msdn.microsoft.com/library/windows/desktop/aa374860) を参照してください。  
  
## 必要条件  
 **ヘッダー :** atlsecurity.h  
  
## 参照  
 [クラスの概要](../../atl/atl-class-overview.md)   
 [セキュリティに関するグローバル関数](../../atl/reference/security-global-functions.md)