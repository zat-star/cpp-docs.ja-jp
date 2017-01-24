---
title: "CSid クラス | Microsoft Docs"
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
  - "CSid"
  - "ATL::CSid"
  - "ATL.CSid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSid クラス"
ms.assetid: be58b7ca-5958-49c3-a833-ca341aaaf753
caps.latest.revision: 24
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSid クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、`SID` \(セキュリティ識別子\) 構造体のラッパー クラスです。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
class CSid  
  
```  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|[CSid::CSidArray](../Topic/CSid::CSidArray.md)|`CSid` オブジェクトの配列。|  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CSid::CSid](../Topic/CSid::CSid.md)|コンストラクターです。|  
|[CSid::~CSid](../Topic/CSid::~CSid.md)|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CSid::AccountName](../Topic/CSid::AccountName.md)|`CSid` のオブジェクトに関連付けられているアカウントの名前を返します。|  
|[CSid::Domain](../Topic/CSid::Domain.md)|`CSid` のオブジェクトに関連付けられているドメインの名前を返します。|  
|[CSid::EqualPrefix](../Topic/CSid::EqualPrefix.md)|等価性 `SID` \(セキュリティ識別子\) プレフィックスをテストします。|  
|[CSid::GetLength](../Topic/CSid::GetLength.md)|`CSid` のオブジェクトの長さを返します。|  
|[CSid::GetPSID](../Topic/CSid::GetPSID.md)|`SID` の構造体へのポインターを返します。|  
|[CSid::GetPSID\_IDENTIFIER\_AUTHORITY](../Topic/CSid::GetPSID_IDENTIFIER_AUTHORITY.md)|**SID\_IDENTIFIER\_AUTHORITY** の構造体へのポインターを返します。|  
|[CSid::GetSubAuthority](../Topic/CSid::GetSubAuthority.md)|**SID** の構造の指定 subauthority を返します。|  
|[CSid::GetSubAuthorityCount](../Topic/CSid::GetSubAuthorityCount.md)|subauthority の数を返します。|  
|[CSid::IsValid](../Topic/CSid::IsValid.md)|有効性を `CSid` のオブジェクトをテストします。|  
|[CSid::LoadAccount](../Topic/CSid::LoadAccount.md)|アカウント名とドメインを含む `CSid` のオブジェクトまたは `SID` の既存の構造を更新します。|  
|[CSid::Sid](../Topic/CSid::Sid.md)|ID 文字列を返します。|  
|[CSid::SidNameUse](../Topic/CSid::SidNameUse.md)|`CSid` のオブジェクトの状態の説明を返します。|  
  
### 演算子  
  
|||  
|-|-|  
|[operator \=](../Topic/CSid::operator%20=.md)|代入演算子。|  
|[演算子の const SID \*](../Topic/CSid::operator%20const%20SID%20*.md)|`SID` の構造体へのポインターへの `CSid` のオブジェクトをキャストします。|  
  
### グローバル演算子  
  
|||  
|-|-|  
|[operator \=\=](../Topic/CSid::operator%20==.md)|等値テストの 2 種類のセキュリティ記述子オブジェクト|  
|[operator \!\=](../Topic/CSid::operator%20!=.md)|非等値テストの 2 種類のセキュリティ記述子オブジェクト|  
|[演算子 \<](../Topic/CSid::operator%20%3C.md)|2 種類のセキュリティ記述子オブジェクトの相対値を比較します。|  
|[演算子 \>](../Topic/CSid::operator%20%3E.md)|2 種類のセキュリティ記述子オブジェクトの相対値を比較します。|  
|[演算子 \<\=](../Topic/CSid::operator%20%3C=.md)|2 種類のセキュリティ記述子オブジェクトの相対値を比較します。|  
|[演算子 \>\=](../Topic/CSid::operator%20%3E=.md)|2 種類のセキュリティ記述子オブジェクトの相対値を比較します。|  
  
## 解説  
 `SID` の構造はユーザーまたはグループを識別するために使用される可変長構造です。  
  
 アプリケーションは `SID` の構造体を直接変更することはありませんが、このラッパー クラスに提供されるメソッドを使用します。  [AtlGetOwnerSid](../Topic/AtlGetOwnerSid.md)、[AtlSetGroupSid](../Topic/AtlSetGroupSid.md)、[AtlGetGroupSid](../Topic/AtlGetGroupSid.md)と [AtlSetOwnerSid](../Topic/AtlSetOwnerSid.md)を参照してください。  
  
 Windows のアクセスの制御モデルの概要については、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の [アクセス制御](http://msdn.microsoft.com/library/windows/desktop/aa374860) を参照してください。  
  
## 必要条件  
 **ヘッダー :** atlsecurity.h  
  
## 参照  
 [セキュリティのサンプル](../../top/visual-cpp-samples.md)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [セキュリティに関するグローバル関数](../../atl/reference/security-global-functions.md)   
 [演算子リファレンス \(アルファベット順\)](../../atl/reference/atl-operators.md)