---
title: "CSecurityDesc クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CSecurityDesc"
  - "ATL.CSecurityDesc"
  - "CSecurityDesc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSecurityDesc クラス"
ms.assetid: 3767a327-378f-4690-ba40-4d9f6a1f5ee4
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 27
---
# CSecurityDesc クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、**SECURITY\_DESCRIPTOR** 構造体のラッパー クラスです。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
class CSecurityDesc  
  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CSecurityDesc::CSecurityDesc](../Topic/CSecurityDesc::CSecurityDesc.md)|コンストラクターです。|  
|[CSecurityDesc::~CSecurityDesc](../Topic/CSecurityDesc::~CSecurityDesc.md)|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CSecurityDesc::FromString](../Topic/CSecurityDesc::FromString.md)|文字列形式のセキュリティ記述子を、有効で実際に機能するセキュリティ記述子に変換します。|  
|[CSecurityDesc::GetControl](../Topic/CSecurityDesc::GetControl.md)|セキュリティ記述子からのコントロール情報を取得します。|  
|[CSecurityDesc::GetDacl](../Topic/CSecurityDesc::GetDacl.md)|セキュリティ記述子から随意アクセス制御リストを \(DACL\) の情報を取得します。|  
|[CSecurityDesc::GetGroup](../Topic/CSecurityDesc::GetGroup.md)|セキュリティ記述子からプライマリ グループの情報を取得します。|  
|[CSecurityDesc::GetOwner](../Topic/CSecurityDesc::GetOwner.md)|セキュリティ記述子から所有者の informaton を取得します。|  
|[CSecurityDesc::GetPSECURITY\_DESCRIPTOR](../Topic/CSecurityDesc::GetPSECURITY_DESCRIPTOR.md)|**SECURITY\_DESCRIPTOR** の構造体へのポインターを返します。|  
|[CSecurityDesc::GetSacl](../Topic/CSecurityDesc::GetSacl.md)|セキュリティ記述子からシステム アクセス制御リストを \(SACL\) の情報を取得します。|  
|[CSecurityDesc::IsDaclAutoInherited](../Topic/CSecurityDesc::IsDaclAutoInherited.md)|自動通信をサポートするために DACL が構成されているかどうかを判定します。|  
|[CSecurityDesc::IsDaclDefaulted](../Topic/CSecurityDesc::IsDaclDefaulted.md)|セキュリティ記述子が既定の DACL を構成するかを決定します。|  
|[CSecurityDesc::IsDaclPresent](../Topic/CSecurityDesc::IsDaclPresent.md)|セキュリティ記述子が DACL が含まれているかどうかを判定します。|  
|[CSecurityDesc::IsDaclProtected](../Topic/CSecurityDesc::IsDaclProtected.md)|変更されることを防ぐために DACL が構成されているかどうかを判定します。|  
|[CSecurityDesc::IsGroupDefaulted](../Topic/CSecurityDesc::IsGroupDefaulted.md)|セキュリティ記述子のグループ セキュリティ識別子 \(SID\) が既定で設定されているかどうかを判定します。|  
|[CSecurityDesc::IsOwnerDefaulted](../Topic/CSecurityDesc::IsOwnerDefaulted.md)|セキュリティ記述子の所有者の SID が既定で設定されているかどうかを判定します。|  
|[CSecurityDesc::IsSaclAutoInherited](../Topic/CSecurityDesc::IsSaclAutoInherited.md)|自動通信をサポートするために、SACL が構成されているかどうかを判定します。|  
|[CSecurityDesc::IsSaclDefaulted](../Topic/CSecurityDesc::IsSaclDefaulted.md)|セキュリティ記述子が既定の SACL に構成されているかどうかを判定します。|  
|[CSecurityDesc::IsSaclPresent](../Topic/CSecurityDesc::IsSaclPresent.md)|セキュリティ記述子が SACL を含めるかどうかを決定します。|  
|[CSecurityDesc::IsSaclProtected](../Topic/CSecurityDesc::IsSaclProtected.md)|変更されることを防ぐために SACL が構成されているかどうかを判定します。|  
|[CSecurityDesc::IsSelfRelative](../Topic/CSecurityDesc::IsSelfRelative.md)|セキュリティ記述子が自己相対的な形式であるかどうかを判定します。|  
|[CSecurityDesc::MakeAbsolute](../Topic/CSecurityDesc::MakeAbsolute.md)|絶対形式にセキュリティ記述子を変換するには、このメソッドを呼び出します。|  
|[CSecurityDesc::MakeSelfRelative](../Topic/CSecurityDesc::MakeSelfRelative.md)|自己相対的な形式にセキュリティ記述子を変換するには、このメソッドを呼び出します。|  
|[CSecurityDesc::SetControl](../Topic/CSecurityDesc::SetControl.md)|セキュリティ記述子のコントロールのビットを設定します。|  
|[CSecurityDesc::SetDacl](../Topic/CSecurityDesc::SetDacl.md)|DACL 情報を設定します。  DACL が既に存在する場合は、セキュリティ記述子に置き換えられます。|  
|[CSecurityDesc::SetGroup](../Topic/CSecurityDesc::SetGroup.md)|プライマリ グループの情報が既に存在する場合、置き換える絶対形式のセキュリティ記述子のプライマリ グループの情報を設定します。|  
|[CSecurityDesc::SetOwner](../Topic/CSecurityDesc::SetOwner.md)|オーナー情報が既に存在する場合、置き換える絶対形式のセキュリティ記述子のオーナー情報を設定します。|  
|[CSecurityDesc::SetSacl](../Topic/CSecurityDesc::SetSacl.md)|SACL 情報を設定します。  SACL が既に存在する場合は、セキュリティ記述子に置き換えられます。|  
|[CSecurityDesc::ToString](../Topic/CSecurityDesc::ToString.md)|文字列の書式にセキュリティ記述子を変換します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CSecurityDesc::operator const SECURITY\_DESCRIPTOR \*](../Topic/CSecurityDesc::operator%20const%20SECURITY_DESCRIPTOR%20*.md)|**SECURITY\_DESCRIPTOR** の構造体へのポインターを返します。|  
|[CSecurityDesc::operator \=](../Topic/CSecurityDesc::operator%20=.md)|代入演算子。|  
  
## 解説  
 **SECURITY\_DESCRIPTOR** の構造はオブジェクトに関連付けられたセキュリティ情報が含まれます。  アプリケーションは、オブジェクトのセキュリティの状態を設定し、クエリにこの構造体を使用します。  [AtlGetSecurityDescriptor](../Topic/AtlGetSecurityDescriptor.md)を参照してください。  
  
 アプリケーションは、代わりにを使用する必要が提供されるクラスのメソッドを使用する **SECURITY\_DESCRIPTOR** の構造を直接変更する。  
  
 Windows のアクセスの制御モデルの概要については、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の [アクセス制御](http://msdn.microsoft.com/library/windows/desktop/aa374860) を参照してください。  
  
## 必要条件  
 **ヘッダー :** atlsecurity.h  
  
## 参照  
 [セキュリティのサンプル](../../top/visual-cpp-samples.md)   
 [SECURITY\_DESCRIPTOR](http://msdn.microsoft.com/library/windows/desktop/aa379561)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [セキュリティに関するグローバル関数](../../atl/reference/security-global-functions.md)